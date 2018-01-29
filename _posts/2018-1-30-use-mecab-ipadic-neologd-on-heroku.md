---
layout: post
title: HerokuでMeCabとmecab-ipadic-NEologdを使う
categories:
  - technology
tags:
  - MeCab
  - Ruby
  - Tech
key:
  - mecab-ipadic-NEologd
  - heroku
---

mastodon上で俳句を検出するbotを作ったのでHerokuで動かしています（[@find575@theboss.tech](https://theboss.tech/@find575){:target="_blank"}、[GitHub](https://github.com/theoria24/FindHaiku4Mstdn){:target="_blank"}）。動かす際に[MeCab](http://taku910.github.io/mecab/){:target="_blank"}を使うので、[このあたり](https://qiita.com/shouta-dev/items/cd538a77f2b729333025){:target="_blank"}を参考にして入れました。

しかしどうも語彙が足りないようなので、いつもお世話になっている[mecab-ipadic-NEologd](https://github.com/neologd/mecab-ipadic-neologd){:target="_blank"}をなんとか入れたので覚え書きを。

ググってみると[knjcode/heroku-buildpack-mecab-ipadic-neologd](https://github.com/knjcode/heroku-buildpack-mecab-ipadic-neologd){:target="_blank"}というのが見つかったのでbuildpacksに追加してデプロイしました。が、どうもうまく入らなかったのでforkされたリポジトリのうちで最も新しかった[called-d/heroku-buildpack-mecab-ipadic-neologd](https://github.com/called-d/heroku-buildpack-mecab-ipadic-neologd){:target="_blank"}を使ってみたところ、表示がおかしかったりしましたがなぜかちゃんと入りました。

[mecab gem](https://github.com/markburns/mecab){:target="_blank"}とか使う場合は`-d /app/.linuxbrew/lib/mecab/dic/mecab-ipadic-neologd`とか渡してやれば良いのですが、今回使ったのは[natto](https://github.com/buruzaemon/natto){:target="_blank"}だったのでよく分からず、mecabrcを書き換えることにしましたが、Herokuではファイルを変更しても戻ってしまうのでdynosで実行する際に毎度変更することにしました。

Procfileは1行しか書けないですがbashを起動すれば複数のコマンドを実行できるようです。以下のように書きました。参考程度に

```Procfile
bot: bash start.sh
```

```start.sh
sed -i -e 's/ipadic/mecab-ipadic-neologd/g' .linuxbrew/etc/mecabrc
bundle exec ruby main.rb
```

以上でmecab-ipadic-NEologdが使えるようになりました。おかげでbotの語彙力が増えました。

しかし、「古池や蛙飛び込む水の音」が「フルイケ, ヤ, カエル, トビコミ, ムスイ, ノ, オト」になってしまったりで５７５と認識されなくなってしまったので、文字数を数えるにはどうかなぁ🤔という感じです。

うーん🤔何かいい方法をご存知の方は教えてください。
