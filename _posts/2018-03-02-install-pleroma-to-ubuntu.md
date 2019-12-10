---
layout: post
title: ubuntuにpleromaを入れてなんとなく動かす
categories:
  - technology
tags:
  - Tech
  - pleroma
  - ubuntu
redirect_from:
  - /install-pleroma-to-ubuntu/
---

動かします。

mastodon開発用にと思い、格安のVPSを勢いで借りたのですが、swapを設定できなかったりしてmastodonをインストールできず、かなしい思いをしました。そこで、軽量でmastodonと互換性のあるという[pleroma](https://git.pleroma.social/pleroma){:target="_blank"}を思い出し、建ててみることにしました。

## 環境とか
なんとなく親しみやすい**Ubuntu**です。**16.04.4 LTS**です。

<small>（以下は建ててみた時の状況を元にVirtualBoxで再現して確認したものです）</small>

## 手順
### 文字コードを確認
僕が借りたVPSはデフォルトの文字コードがUTF-8でなく後々めんどくさかったのであらかじめ`en_US.UTF-8`とかにしておくと良いでしょう。

以下は[pleromaのWiki](https://git.pleroma.social/pleroma/pleroma/wikis/Installing%20on%20debian%20based%20distributions){:target="_blank"}を参考に進めていきます。

### 準備
とりあえず色々更新しておきます

    apt update && apt dist-upgrade

続いて必要な諸々を入れていきますが、

    apt install git build-essential openssl ssh sudo postgresql-9.6 postgresql-contrib-9.6

`postgresql-9.6`なんかねえと怒られるので、ひとまず`apt install git build-essential openssl ssh sudo`します。

どうやらubuntuのリポジトリにはPostgreSQL **9.5**までしか登録されていないようなので、[このあたり](https://www.postgresql.org/download/linux/ubuntu/){:target="_blank"}を参考にリポジトリを追加し、キーリストに公開鍵を追加します。

    echo 'deb http://apt.postgresql.org/pub/repos/apt/ xenial-pgdg main' > /etc/apt/sources.list.d/pgdg.list
    wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | \
    apt-key add -

一応`apt-key list`で追加されているか確認します。`PostgreSQL Debian Repository`が追加されていればOKです。

改めてPostgreSQLをインストールします。

    apt update
    apt install postgresql-9.6 postgresql-contrib-9.6

これでPostgreSQL 9.6が入りました。

Elixir・Erlangを入れていきます。何も考えずに`apt install`すると**1.1.0**あたりのものが入るので気をつけましょう。1.5以降のものが必要です。

    wget https://packages.erlang-solutions.com/erlang-solutions_1.0_all.deb && dpkg -i erlang-solutions_1.0_all.deb

`apt-key list`で確認すると`Erlang Solutions Ltd.`が追加されています。<small>（`erlang-solutions_1.0_all.deb`が残るので`rm`しましょう）</small>

さて、Elixirとかを入れましょう。

    apt update
    apt install elixir erlang-dev erlang-parsetools erlang-xmerl

### pleromaバックエンドを入れていく
いよいよpleroma本体のインストール作業です。

まずpleroma用のユーザーを追加します

    adduser pleroma

パスワードを入れろと言われるので適切に入れます。それ以降はエンター連打で大丈夫でしょう。

`pleroma`を`sudo`グループに入れ、

    usermod -aG sudo pleroma

ユーザーを切り替えて`/home/pleroma`に入ります。

    su - pleroma

GitLabからソースコードを取ってきて、

    git clone https://git.pleroma.social/pleroma/pleroma

ソースコードのあるディレクトリに入ります。

    cd pleroma/

`mix`という便利なやつで依存関係を入れていきます。

    mix deps.get

`Hex`ないから入れるで？と言ってきたら`Y`と答えましょう。

次に、設定ファイルを作ったります。

    mix generate_config

`rebar3`ないから入れるで？と言われたら`Y`と答えましょう。

いろいろコンパイルするので少し時間がかかります。<small>（すごいWarning出るけど大丈夫なんかな…）</small>

しばらくすると

    What is your domain name? (e.g. pleroma.soykaf.com):

    What is the name of your instance? (e.g. Pleroma/Soykaf):

    What's your admin email address:

と連続して聞いてくるので、それぞれの質問に、公開するドメイン名、インスタンスの名前、管理者のメールアドレスを答えましょう。

続けて

    Do you want to activate the mediaproxy? (y/N):

と聞いてきます。メディアプロキシを有効にしない場合、ユーザーが外部のインスタンスから発信されたメディアを閲覧した際に、ユーザーのIPアドレスが発信元のインスタンスに見えてしまいますが、メディアを保存しないためにストレージの消費が少なくなります。

ここまでの質問に答えると、設定が書かれたファイル`generated_config.exs`が生成されます。

メディアプロキシを有効化する場合、もう一手間必要になります（[このへん](https://git.pleroma.social/pleroma/pleroma/wikis/How-to-activate-mediaproxy){:target="_blank"}を見るとよいです）。

設定ファイルにはデータベースのパスワードなどが生成されているので、確認しておきましょう。

その後、`generated_config.exs`を`prod.secret.exs`にリネームします。

    mv config/{generated_config.exs,prod.secret.exs}

続いて、データベースのセットアップを行います。

    sudo su postgres -c 'psql -f config/setup_db.psql'

生成されたパスワードでデータベースやテーブルが作成されます。

続けてデータベースのマイグレーションを行います。

    MIX_ENV=prod mix ecto.migrate

ここまで終われば、とりあえず動きます。次のコマンドを実行して動作を確認することができます。

    MIX_ENV=prod mix phx.server

`http://[ドメイン名]:4000`でアクセスできる（？）。ローカルなら`http://0.0.0.0:4000`？

終了は<kbd>ctrl</kbd>+<kbd>c</kbd>。

### nginxの設定
まずnginxを入れます。<small>（このあたりでrootに戻っておくとよい）</small>

    apt install nginx

続いてnginxの設定ファイルを作るのですが、pleromaは非常に親切なので、テンプレートを用意してくれていますので、コピーします。

    cp /home/pleroma/pleroma/installation/pleroma.nginx /etc/nginx/sites-enabled/pleroma.nginx

設定ファイルを開き、ドメイン名などを編集します。

    vi /etc/nginx/sites-enabled/pleroma.nginx

基本的には`example.tld`を自分のドメインに変えれば良いでしょう。SSL証明書にLet's Encryptを使わない場合は`ssl_certificate`も適切なものに変えましょう。

続いてLet's EncryptでSSL証明書を取得します。

    apt update && apt install software-properties-common
    add-apt-repository ppa:certbot/certbot
    apt update && apt install python-certbot-nginx
    certbot --nginx certonly

するとメールアドレスを聞かれるので、入力しましょう。証明書の期限が近づいたりすると連絡が来ます。次に規約のURLが表示されるので読みましょう。同意するなら`A`を打ち次に進みます。プロジェクトの非営利団体にメールアドレスを共有してもいいか？と聞いてくるのでYでもNでもお好きに。するとドメインを聞かれるのでドメインを入力しましょう。

成功すると`/etc/letsencrypt/live/[ドメイン名]/`に証明書が入るので、これをnginxに教えてやる必要があるのですが、先ほどコピーした設定ファイルに既に書いてあるので大丈夫です。

nginxを再起動して設定を反映します。

    systemctl restart nginx.service

### pleromaのサービス化
systemdの.serviceファイルを書く必要がありますが、pleromaは非常に親切なので、テンプレートを用意してくれていますので、コピーします。

    cp /home/pleroma/pleroma/installation/pleroma.service /etc/systemd/system/pleroma.service

コピーしたら、`vi /etc/systemd/system/pleroma.service`で開き、`[Service]`の節に`Environment="MIX_ENV=prod"`を追記します。

最後に、サービスを有効化します。

    systemctl enable --now pleroma.service

<small>（弊環境では`Failed to execute operation: Invalid argument`となり困ったが、`systemctl is-enabled pleroma.service`で確認すると`enabled`になっており、動いているのでまあ良いかとなった。）</small>

### その他の設定
mastodonにおける`/about`のようなページはないので、規約の類いを書く場所が難しい。最低限、登録の際に表示される"Terms of Service"は独自のものにしておきたい（デフォルトではこのファイルを編集しろみたいなのが書いてあるので見栄えが良くない）。場所が少しわかりにくく、`/home/pleroma/pleroma/priv/static/static/terms-of-service.html`にある。

また`/home/pleroma/pleroma/priv/static/static/config.json`を編集し、`"showInstanceSpecificPanel"`を`true`にすると、サイドメニューの下にパネルを表示できる。これは`/home/pleroma/pleroma/priv/static/instance/panel.html`を編集することで、内容を変更できる。

<!-- `mix set_moderator username [true|false]`でモデレーターを指定/解除できる。モデレーターは、あらゆる投稿を削除できる。

`mix generate_password_reset username`によってパスワードリセット用のリンクを作成できる。-->

## 感想
設定ファイルがあらかじめ用意されているのでとても簡単に建てられた感じがある。

mastodonより低スペックのサーバーで動作すると聞いていたが、実際にmastodonが動作しなかったサーバーで動作したのでほんとだ〜となった。

どの程度の規模まで耐えられるのか試してみたい気持ちもあるが、まともに運用していくつもりもないので積極的に宣伝してユーザーを増やす気にはならない<small>（[pleroma.raramagi.ga](https://pleroma.raramagi.ga/){:target="_blank"}）</small>。

`/web`にアクセスすれば、mastodonの皮を被ったpleromaができ、良い。~~ただし、そこにある公開範囲を指定するボタンは飾りだ。~~ （3/14追記）ActivityPubに対応した時点で公開範囲設定ができるようになったようです。

お一人様インスタンスには良いかもなぁと感じた。

Elixirへの興味が増した。RailsをやっていくかElixirをやっていくか…（余裕なし）
