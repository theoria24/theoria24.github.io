---
layout: post
title: RubyでGoogle SpreadSheetを扱うメモ
categories:
  - technology
tags:
  - Ruby
  - Google
  - GoogleDrive
  - Tech
---

[https://blog.cloudpack.jp/2014/10/28/input-data-to-google-spreadsheet-with-ruby](https://blog.cloudpack.jp/2014/10/28/input-data-to-google-spreadsheet-with-ruby){:target="_blank"}を参考にGoogle SpreadSheetに値を飛ばして保存するやつをRubyで作っていたのですがそのまま書いたらどうも上手く動かないので修正したやつ。

参考サイトのままアカウント名とアプリのパスワードを発行したものとスプレッドシートのIDを差し替えただけで（もちろん[gimite/google-drive-ruby](https://github.com/gimite/google-drive-ruby){:target="_blank"}は入れて）

##### test.rb

```ruby
#!/usr/bin/env ruby

require "rubygems"
require "google_drive"

# 初期化
# OAuth を利用して認証
session = GoogleDrive.login("#{Gmail アカウント}", "#{アプリのパスワード}")
# ws インスタンス生成
ws = session.spreadsheet_by_key("#{スプレッドシートの ID}").worksheets[0]

# レコードをハッシュで生成
hash = {"timestamp" => "100" , "record" => { "a" => "10", "d" => "11", "e" => "12", "x" => "13" }}

# ヘッダを生成
ws.update_cells(1, 1, [hash["record"].keys])
# 一旦 save
ws.save

begin
  timeout(5) do
    # これでぶっ込む
    ws.list.push(
      hash["record"].each do |k, v|
        ["#{k}" => "#{v}"]
      end
    )
    ws.save
  end
rescue Timeout::Error
  puts "Google SpreadSheet-- Timed out while attempting to send"
```

としたら

```bash
test.rb:31: syntax error, unexpected end-of-input, expecting keyword_end
  puts "Google SpreadSheet-- Timed out while attempting to send"
                                                                ^
```

と言われたので は～（°～°）？？？？？ って言って普通にend加えて実行。

今度は

```bash
test.rb:8:in `<main>': undefined method `login' for GoogleDrive:Module (NoMethodError)
```

…

[gimite/google-drive-ruby](https://github.com/gimite/google-drive-ruby){:target="_blank"}を確認。どうやらGoogle側のAPIが変更されておりGoogleDrive.loginはもう使えないよとのこと。

ひとまず[Google Developer Console](https://console.developers.google.com/){:target="_blank"}で適当にプロジェクトを作成、API Managerの概要タブからGoogle Apps APIのDrive APIを有効化、認証情報タブのCreate credentialからOAuth クライアント IDを発行。最初に発行するときは同意画面が云々と言われるので従ってください。  
後々使うので認証情報のJSONをダウンロードしてconfig.jsonと名前をつけてRubyファイルと同じフォルダに置きます。

さて、Ruby側の設定です。  
さっきエラーになった

```ruby
session = GoogleDrive.login("#{Gmail アカウント}", "#{アプリのパスワード}")
```

を

```ruby
session = GoogleDrive.saved_session("config.json")
```

に書き換えます。これでさっきダウンロードしてきたconfig.jsonからいい感じに情報を拾って認証してくれるはずです。

実行すると

```bash
1. Open this page:
https://accounts.google.com/なんちゃら
```

と言われるのでURLをブラウザで開く。

> google-drive-ruby が次の許可をリクエストしています:

というページが開くので良ければ許可。指示に従ってコードをコピーし、

```bash
2. Enter the authorization code shown in the page:
```

に貼り付けてEnter。

この後スプレッドシートを開くと…

![GoogleSpredSheet](http://theoria24.github.io/images/Ruby-GoogleSpredSheet-1.png){:target="_blank"}

[動作かくにん！よかった。](http://www.j-cast.com/tv/2014/05/08204104.html){:target="_blank"}

2回目以降は認証情報がconfig.jsonに保存されているのでブラウザを立ち上げたりしなくても実行できます。

あとのことは省略しますが、認証が通ったので読みこんだり書き込んだり色々できるはずです。頑張ってください。僕も頑張ります。
