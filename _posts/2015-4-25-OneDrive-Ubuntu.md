---
layout: post
title: UbuntuでOneDriveとの同期が可能な「onedrive-d」を導入してみた
---

かつてUbuntuに標準で(？)搭載されていたストレージサービスUbuntu Oneが昨年6月に終了したので、Ubuntuでなんか使えるのないかなーと思って探してみたところ見つけたのが[onedrive-d](https://github.com/xybu/onedrive-d)。

前置きどーでもいーからインストール方法はよって人は[こっち](#how)

とりあえず導入の仕方をググってみると普通に日本語記事がいっぱい出てきたのでこれは余裕だと思って導入に取り掛かりました。

最初に見たサイトが http://natto.usamimi.info/?p=695
書いてある通り

```
$ mkdir ~/OneDrive
$ git clone https://github.com/xybu92/onedrive-d.git
$ cd onedrive-d
$ ./inst install
```

したところなんかうまくいかない。

とりあえず別のサイトも見てみますが…

うーん、同じだ…

諦めて[公式github](https://github.com/xybu/onedrive-d)を見ます。

英語だ…(当然)

バージョンが変わってインストール方法も変わっていたようです。

以下README.mdをそれっぽく訳しただけのやつです。

<div id="how"><b>以下本文</b></div>

初めに

```
$ mkdir ~/OneDrive
```

して同期するディレクトリを作っておくと便利です。既存のディレクトリを指定することもできるので必須ではないですが。

### 1. 古いバージョンのonedrive-dのアンインストール

初めに既にonedrive-dをインストールしている人は古いバージョンのonedrive-dをアンインストールする必要があります。

onedrive-dのバージョンが1より前のとき

```
$ sudo pip uninstall onedrive-d
```

onedrive-dのバージョンが1以降のとき

```
$ sudo pip3 uninstall onedrive-d
```



それから、

```
$ rm -rfv ~/.onedrive
```

### 2. ソースコードの取得

gitを使います

```
$ git clone https://github.com/xybu/onedrive-d.git
$ cd onedrive-d
```

あるいは[https://github.com/xybu/onedrive-d](https://github.com/xybu/onedrive-d)からzipでダウンロードしてもいいはず

### 3. onedrive-dのインストール

onedrive-dの動作にはPython3が必要なのでない人はインストールしてください。Pythonのバージョンが3.4以前の人はpython3-pipも必要らしいのでapt-getするなりしてinstallしてください。

パッケージの登録

```
$ sudo python3 setup.py install
```

一時ファイルの削除


```
$ sudo python3 setup.py clean
```

設定ファイル用のディレクトリの作成

```
$ mkdir ~/.onedrive
$ cp ./onedrive_d/res/default_ignore.ini ~/.onedrive/ignore_v2.ini
```

ログファイルの作成

```
$ sudo touch /var/log/onedrive_d.log
```

‘whoami’をユーザー名にしたいとき

```
$ sudo chown `whoami` /var/log/onedrive_d.log
```

### 4. 設定

設定プログラムの起動

```
$ onedrive-pref
```

指示になんとなく従っていってください

#### Step1/4 OneDriveアカウントの認証

OneDrive認証用のURLが表示されるのでコピペするなりしてブラウザで開いてログインしてください。

ログインすると真っ白なページに飛びますが気にせずURLをコピー、端末にペーストしてEnter

認証成功っぽい英文が出たら成功、失敗したらもう一回やって下さい。

#### Step2/4 OneDriveと同期するディレクトリの指定

デフォルトでは/home/(ユーザー名)/OneDriveに指定されるので別なとこにしたい人はここで指定してください。

#### Step3/4 数値とかの設定(？)

タイムアウトになるまでの時間やファイルサイズによる同期制限とかができます。こだわりがある人はどうぞ。

#### Step4/4 同期しないファイルの指定

リストをvimとかで開くので頑張って指定してください。



GUIじゃないと嫌って人は

```
$ onedrive-pref --ui=gtk
```

してください。設定項目は同じなので割愛。

### 5. 起動

onedrive-dの起動（バックグラウンドプロセス）

```
$ onedrive-d start
```

通常プロセスとして実行したいときは

```
$ onedrive-d start --debug
```

これで連携したOneDriveと指定したローカルフォルダが同期されます

### 補足

ヘルプが必要な人は

```
$ onedrive-pref --help
$ onedrive-d --help
```

するとヘルプが出ます。英語で。

詳しいことは[https://github.com/xybu/onedrive-d](https://github.com/xybu/onedrive-d)を見てください。すいません。

インストールしないで実行とかもできるらしい。

おわり