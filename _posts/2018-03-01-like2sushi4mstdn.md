---
layout: post
title: mastodonのお気に入り登録ボタンを寿司に変える
categories:
  - technology
tags:
  - Tech
  - CSS
  - mastodon
redirect_from:
  - /like2sushi4mstdn/
---

こんにちは。mastodonをいじって楽しんでいるておりあです。タイトルのとおりです。

## like2sushi4mstdn.css
Gistで[公開しています](https://gist.github.com/theoria24/8ac3ac0f8167b109eb0724c4563ddf6d){:target="_blank"}。

### なにこれ？
mastodonのお気に入り登録ボタンを寿司に変えるユーザースタイルシートです。

### は？
<iframe src="https://theboss.tech/@theoria/99514232898753004/embed" class="mastodon-embed" style="max-width: 100%; border: 1px solid #e1e8ed; border-radius: 5px;" width="400"></iframe><script src="https://theboss.tech/embed.js" async="async"></script>
こんな感じです。

### 使い方
Stylish（[Chrome](https://chrome.google.com/webstore/detail/stylish-custom-themes-for/fjnbnpbmkenffdnngjfgmeleoegfcffe?hl=ja){:target="_blank"}, [Firefox](https://addons.mozilla.org/ja/firefox/addon/stylish/){:target="_blank"}）を想定しています。たぶんそれ以外のユーザースタイルシート指定アドオンでも動くと思います。

[userstyles.orgに上がっています](https://userstyles.org/styles/155700/like2sushi4mstdn){:target="_blank"}のでそこからインストールするといいと思います。デフォルトではmstdn.jpで動くようになっているのでStylishの設定でお使いのインスタンスを設定してあげてください。

[Gist](https://theboss.tech/@AnonymousPost){:target="_blank"}からコピペしてもいいでしょう（以下のカスタマイズが楽です）。

### カスタマイズ
人間生きていれば、お気に入り登録ボタンを🍣以外に変えたくなることもあるでしょう。

そういう場合、`https://twemoji.maxcdn.com/36x36/1f363.png`を目的の画像に置き換えると実現できます。

絵文字であれば、変えたい絵文字のUnicodeのコードポイントをなんとかして調べて`1f363`を置換すると良いでしょう。<small>（[Unicode コードポイント変換 - ちょびつーる](http://chobitool.com/unicodepoint/){:target="_blank"}というのを見つけました。）</small>小文字にしてください。

### 例
以下のような活用がされています
- https://pawoo.net/@pacochi/99520937732120818
- https://kurage.cc/@yi0713/99522560479408613
- https://gamelinks007.net/@S_H_/99523580722473183

### 作るに至ったあれこれ
かつて、Twitterの⭐️が❤️になってしまったときに、🍣にするChrome Extension（[mzyy94/like2sushi](https://github.com/mzyy94/like2sushi){:target="_blank"}）が存在し、フォークして遊んだりしていました。ふと懐かしくなって見に行ったらアーカイブ化されており、悲しくなったのでmastodonで似たようなもん作ろうと思いました。

### その他
分からなかったら[@theoria@theboss.tech](https://theboss.tech/@theoria){:target="_blank"}にリプライか何か投げてください。気付いたら対応します。
