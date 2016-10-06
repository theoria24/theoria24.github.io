---
layout: post
title: Sublime TextからWikipediaに投稿する
categories:
  - technology
tags:
  - Wikipedia
  - Sublime Text
  - Tech
---

最近プログラムをいじったりするのに[Sublime Text](https://www.sublimetext.com/){:target="_blank"}を使っています。色々なプラグインがあって便利。  
あと最近Wikipediaの編集をするようになりました。

Sublime TextはHTMLタグを閉じようとするとき<code>&lt;/</code>まで打つといい感じに閉じてくれたりして便利なので、Wikipediaを編集するときに<code>&lt;ref&gt;&lt;/ref&gt;</code>とか打つのめんどいな―、いい方法ないかなーと思って調べたら[Mediawiker](https://github.com/tosher/Mediawiker){:target="_blank"}というものを見つけたので使ってみた（解決しなかった）。

## インストール
Package Controlで入ります。Package Control使いたくない人は[GitHub](https://github.com/tosher/Mediawiker){:target="_blank"}からzipでダウンロードしてプラグインフォルダに入れればたぶん動きます。

## 設定
このままだとWikipediaに接続できない（en.wikipedia.orgに繋がる？）ので、ユーザー設定をいじります。

Preference &rarr; Package Setting &rarr; Mediawiker &rarr; Settings - User を開き、

#### Mediawiker.sublime-settings

```json
{
    "mediawiki_site":
    {
        "Japanese wikipedia":
        {
            "host": "ja.wikipedia.org",
            "path": "/w/",
            "pagepath": "/wiki/",
            "username": "ユーザー名",
            "password": "パスワード",
            "domain": "",
            "https": true,
            "force_login": true
            },
    },
    "mediawiki_site_active": "Japanese wikipedia"
}
```
としてやると [ja.wikipedia.org](https://ja.wikipedia.org){:target="_blank"} につながります。

<code>Japanese wikipedia</code>は別にこれでなくても構いません（Defaultの方見たら<code>English wikipedia</code>とかあったので合わせました）。

ここまで来たら<kbd>Alt</kbd>+<kbd>F1</kbd>で（他のキーバインドと競合してなければ）Edit panelが立ち上がるのでOpen pageを選択、編集したい項目名を入れるとページのソースが表示され編集できます。（できなかったときはメニューの Tools &rarr; Mediawiker &rarr; 辺りを使うとキーバインド編集をしなくても幸せになれます）

<span style="font-size: 12px;">（Mediawikerは日本語に対応していないらしく変換を決定するときに<kbd>Enter</kbd>を押すとキーバインドが発動してしまう問題があるようです（））</span>

問題はありますが、Wiki構文をハイライトしてくれるので多少便利です。<kbd>Enter</kbd>周りは多少頑張れば修正できそうなのでそのうち考えます。