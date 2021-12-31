---
layout: post
title: WUGメンバーのWikipedia記事を分析します
categories:
  - Anime
tags:
  - Anime
  - WUG
  - Wake Up Girls!
  - Wikipedia
key:
  - アドベントカレンダー
twimage: https://i.imgur.com/VoOshpA.png
---

## 目次

めちゃくちゃ長くなっちゃったのでいちばん上に目次を貼っておきます。Twitter の埋め込みがいっぱいあるので重いかもしれません。

- [こんにちは！](#こんにちは)
- [今回やること](#今回やること)
- [方法](#方法)
- [閲覧回数](#閲覧回数)
  - [吉岡茉祐さん](#吉岡茉祐さん)
  - [永野愛理さん](#永野愛理さん)
  - [田中美海さん](#田中美海さん)
  - [青山吉能さん](#青山吉能さん)
  - [山下七海さん](#山下七海さん)
  - [奥野香耶さん](#奥野香耶さん)
  - [高木美佑さん](#高木美佑さん)
- [考察](#考察)
- [感想](#感想)

---

この記事は **Wake Up, Girls！ Advent Calendar 2021** の 19 日目の記事です[^kyo]。よろしくお願いします！

[^kyo]: 今日は 12 月 19 日です！！！！！

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://adventar.org/calendars/6206" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-30x25.svg" style="background-image: url(https://adventar.org/og_image.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wake Up, Girls！ Advent Calendar 2021 - Adventar</q></span><span class="embed-html-box_description"><q>Wake Up, Girls！関連の記事ならなんでもOKです。愛のある記事をお願いします。お気軽にどうぞ。ハッシュタグ: [#WUG_ADVENT](https://twitter.com/hashtag/WUG_ADVENT)
枠が足りなくなった場合はどこかにリンクをまとめさせていただきますのでご連絡ください。

いくぞ！がんばっぺ！

**過去に開催されたもの**
[2020](https://adventar.org/calendars/4935) [2019](https://adventar.org/calendars/3985) [2018](https://adventar.org/calendars/3206) [2017](https://adventar.org/calendars/2232) [2014](https://adventar.org/calendars/678)
</q></span></span></a></p></div>

## こんにちは！

こんにちは！ておりあです！ Wake Up, Girls！ Advent Calendar 2021 主催です！はじめましての方ははじめまして！ご存じの方はいつもお世話になってます！

普段は Wugtodon（[wug.fun](https://wug.fun){:target="\_blank" rel="noopener"}）という mastodon サーバーの管理人をやったり高木美佑さんのオタクしてそのついでに [@myuunews](https://twitter.com/myuunews){:target="\_blank" rel="noopener"} という Twitter bot を動かしたりしています。

早いもので 2021 年もアドベントカレンダーの季節がやってまいりました！本当に早い！今年もよろしくお願いします！

[昨年のアドベントカレンダー](https://adventar.org/calendars/4935){:target="\_blank" rel="noopener"} も様々な記事を投稿していただき楽しく拝読させていただきました。 [わぐおんりーの話](https://hikolive.hatenablog.com/entry/2020/12/07/223641){:target="\_blank" rel="noopener"} や [解散後に WUG を知った人の叫び](https://klopppoke.hatenablog.com/entry/2020/12/07/000000){:target="\_blank" rel="noopener"} 、 [煮豆界隈](https://mlml777.hatenablog.com/entry/2020/12/09/000000){:target="\_blank" rel="noopener"} 、 [創作落語](https://sorobanya.hatenablog.com/entry/2020/12/13/000000){:target="\_blank" rel="noopener"} [^sosaku] に [500 日後に働く人](https://yamasif.hateblo.jp/entry/2020/12/19/152222){:target="\_blank" rel="noopener"} 、 [アニメのデビューライブの日に合わせて勾当台公園に集まるオタク](https://natorin2398.hateblo.jp/entry/2020/12/25/212415){:target="\_blank" rel="noopener"} … 個性豊かな、良い文章、表現ばかりでした……ありがとう……

[^sosaku]: 僕はこの企画を通して何らかの新しい創作が出てきてくれたらなと思っていたので創作落語とか出てきて感動しました。

## さて

[去年の僕の Advent Calendar](https://theoria24.github.io/article/2020/12/20/wug-advent-calendar-2020.html) を見た人は、こいつ訳わかんねえ情報をまとめてポエム書いてるぞ と思ったと思うのですが、今年もそうです。ごめんね。

## 今回やること

WUG メンバー[^mem]の Wikipedia 記事を分析します

[^mem]: この場合正確には元メンバーとかになるんですかね？　僕の中で WUG は永久に不滅なのでこの記事では WUG メンバーとします。

### どうして？

WUG メンバーが、いつ何がきっかけでどれくらい興味を持たれているのかを知りたいなと思いました。しかし我々は既に WUG を知ってしまっているので、WUG を知らなかった頃の状態には戻れません。

そこで、現代人がなにか気になったらまず見る場所、そう、 **Wikipedia** の閲覧数を調査してみることにしました（まずは公式サイトを見ようね）。

## 方法

Wikimedia のプロジェクトには REST API があり、 Pageviews data 等を取ってくることができます。

[Wikimedia REST API](https://wikimedia.org/api/rest_v1/){:target="\_blank" rel="noopener"}

と思ったら閲覧数は 2015 年 7 月以降のものしか取れませんでした。すみませんが、今回はこれで行きます。

これで取ってきたデータをいい感じにグラフにして特徴ある点を解釈していきたいと思います。今回は **R** を使ってみたいと思います（前から使ってみたかったので）。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.r-project.org/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-30x25.svg" style="background-image: url(https://www.r-project.org/logo/Rlogo.svg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>R: The R Project for Statistical Computing</q></span><span class="embed-html-box_description"><q>R is a free software environment for statistical computing and graphics. It compiles and runs on a wide variety of UNIX platforms, Windows and MacOS.</q></span></span></a></p></div>

## 閲覧回数

閲覧回数は例えば

```
curl https://wikimedia.org/api/rest_v1/metrics/pageviews/per-article/ja.wikipedia.org/all-access/user/高木美佑/daily/20210101/20211201
```

のようにして取ってくることができます。[^wra]

[^wra]: 詳しくは [Wikimedia REST API](https://wikimedia.org/api/rest_v1/){:target="\_blank" rel="noopener"} を見てください。今回は ja.wikipedia.org の『高木美佑』の 2021 年 1 月 1 日から 2021 年 12 月 1 日までのユーザー（クローラや自動アクセスを除く）のアクセス数を取得しています。

これを全員分 2015 年 7 月から 2021 年 11 月まで取ってきて R でいい感じのグラフにします。

全体はこのようになりました。

<figure>
  <center>
    <a href="https://i.imgur.com/VoOshpA.png"><img src="https://i.imgur.com/VoOshpA.png"></a>
    <figcaption>全体</figcaption>
  </center>
</figure>

重なっていてよく分かりませんが、ところどころ急激に増えているところがありますね。1 人ずつ見ていきたいと思います。

## 吉岡茉祐さん

<figure>
  <center>
    <a href="https://i.imgur.com/Uaye5iJ.png"><img src="https://i.imgur.com/Uaye5iJ.png"></a>
    <figcaption>Wikipedia: 吉岡茉祐 のアクセス数</figcaption>
  </center>
</figure>

何か所か、アクセス数が増えている時期がありますね。

### 2016 年 4 月 〜 6 月頃

やや増えていますね。この時期は、TV アニメ **ハンドレッド** や **あんハピ ♪** が放送されていました。吉岡さんはそれぞれ **霧島サクラ**（ハンドレッド）、 **江古田蓮**（あんハピ ♪）とメインキャラクターの 1 人を務めました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://hundred-anime.jp/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://hundred-anime.jp/assets/img/ogimage_160306.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「ハンドレッド」公式サイト</q></span><span class="embed-html-box_description"><q>アニメ「ハンドレッド」テレビ東京ほかにて絶賛放映中！</q></span></span></a></p></div>

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://anne-happy.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-30x25.svg" style="background-image: url(https://anne-happy.com/wp-content/themes/annehappy/base/img/logo.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「あんハピ♪」公式サイト</q></span><span class="embed-html-box_description"><q>芳文社「まんがタイムきららフォワード」にて原作漫画が好評連載中!不憫にもほどがある5人の少女たちが繰り広げる励まし系学園コメディ</q></span></span></a></p></div>

また、ハンドレッドの OP テーマを務めた、DIVE II entertainment のボーカルユニット **D-selections** としても活動していました。

### 2018 年 6 月 15 日 〜

2018 年 6 月 15 日にアクセス数が大きく増え、そこから 1 週間程度、普段よりアクセスが多い状態になっています。

この日何があったのでしょうか…… そう… **Wake Up, Girls！ の解散** が発表された日です。吉岡さんは Wake Up, Girls！ のセンターなどを務めました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://wug-portal.jp/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://wug-portal.jp/assets/img/ogp_180615.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wake Up, Girls！ 総合公式サイト｜WUGポータル</q></span><span class="embed-html-box_description"><q>TVアニメ「Wake Up, Girls！」シリーズ及び声優ユニット「Wake Up, Girls！」の総合情報サイト！</q></span></span></a></p></div>

### 2018 年 6 月 29 日

WUG の解散に隠れてあまり目立ちませんが、この日もアクセスが増えています。

この日、声優の**今村彩夏さんが引退を発表**しました。これを受けて、今村さんが声優を務めていた 温泉むすめ **飯坂真尋**役を吉岡さんが引き継ぐことが発表されています。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【お知らせ】<br>今村彩夏さんの引退を受けまして、新たな飯坂真尋役を吉岡茉祐さんにご担当いただくことになりました。<a href="https://t.co/sRRShjt4LA">https://t.co/sRRShjt4LA</a><br>皆様の変わらぬご支援並びにご声援を頂戴できますと幸いです。<a href="https://twitter.com/hashtag/%E6%B8%A9%E6%B3%89%E3%82%80%E3%81%99%E3%82%81?src=hash&amp;ref_src=twsrc%5Etfw">#温泉むすめ</a> <a href="https://twitter.com/hashtag/%E6%B8%A9%E3%82%80%E3%81%99?src=hash&amp;ref_src=twsrc%5Etfw">#温むす</a></p>&mdash; 「温泉むすめ」公式 (@onsen_musume_jp) <a href="https://twitter.com/onsen_musume_jp/status/1012543719742963712?ref_src=twsrc%5Etfw">June 29, 2018</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### 2019 年 3 月 8 日

吉岡さんがセンターを務めた 声優ユニット **Wake Up, Girls！ のファイナルライブ** が行われた日、アクセスが増えています。

### 2019 年 7 月 8 日 〜 9 月頃

7 月 8 日は TV アニメ **コップクラフト** 第 1 話の放送日です。吉岡さんは、メインヒロイン **ティラナ・エクセディリカ**役を務めました。また、キャラクター名義で同作の ED 主題歌も担当しています。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="http://copcraft.tv/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://copcraft.tv/wp/wp-content/themes/copcraft/images/common/ogimage.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「コップクラフト」公式サイト</q></span><span class="embed-html-box_description"><q>ガガガ文庫にて1巻～6巻まで発売。累計発行部数は20万部を突破。巨匠・賀東招二＆村田蓮爾が描くバディポリスアクション、待望のTVアニメ化決定！</q></span></span></a></p></div>

ここからしばらく 1 週間毎に若干アクセスが増えています。放送の度に検索されるもんなんだ。

### 2019 年 7 月 13 日, 14 日

コップクラフトかと思ったんですが、ここだけ傾向が若干違います。

この日は **Tokyo 7th シスターズ 5th Anniversary Live -SEASON OF LOVE- in Makuhari Messe** の開催日です。吉岡さんは**鰐淵エモコ**役で出演されています。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="http://t7s.jp/live/5thlive/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://t7s.jp/image/visual/banner/top48_pc.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Tokyo 7th シスターズ 5th Anniversary Live -SEASON OF LOVE- in Makuhari Messe - 特設サイト</q></span><span class="embed-html-box_description"><q>Tokyo 7th シスターズ 5th Anniversary Live -SEASON OF LOVE- in Makuhari Messe - 特設サイト</q></span></span></a></p></div>

### 2021 年 3 月 7 日, 14 日

アクセス数が増えています。これマジで何？

7 日間隔なのでテレビ・ラジオかなと思ったのですが、それっぽい番組が **かのおが便利軒** しか思い浮かばず。本当？ ちなみに 3 月 7 日、14 日は吉岡さんが実写で出演されています（普段は声のみ）。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.ox-tv.co.jp/kanooga/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://www.ox-tv.co.jp/kanooga/ogp/ogp.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>かのおが便利軒</q></span><span class="embed-html-box_description"><q>仙台市青葉区「かのおが便利軒」 仙台放送　毎週日曜 ひる1時25分より絶賛放送中</q></span></span></a></p></div>

## 永野愛理さん

<figure>
  <center>
    <a href="https://i.imgur.com/bWRu0Df.png"><img src="https://i.imgur.com/bWRu0Df.png"></a>
    <figcaption>Wikipedia: 永野愛理 のアクセス数</figcaption>
  </center>
</figure>

### 2017 年 5 月 2 日

2017 年 5 月 2 日、アクセス数が増えています。何があったのでしょう。

**松井恵理子・松嵜麗の声優アニ雑団** #55 の放送日でした。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://abema.tv/channels/abema-special/slots/9JUxWEEM8cwKXm" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://hayabusa.io/abema/programs/90-90cnftfzficw_s0_p55/thumb001.w800.v1627677474.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>松井恵理子・松嵜麗の声優アニ雑団♯55〜ゲスト：永野愛理 | 新しい未来のテレビ | ABEMA</q></span><span class="embed-html-box_description"><q>人気声優の2人がゆるーくお届けする1時間。ゲーム、アニメ、趣味などを熱く語る。 ご意見・ご感想・お悩み・イラストはこちらまで! anizatsu@abema.tv 出演者は、松井恵理子、松嵜麗、永野愛理です。</q></span></span></a></p></div>

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">永野愛理は面白いw<a href="https://twitter.com/hashtag/AbemaTV1%E5%91%A8%E5%B9%B4?src=hash&amp;ref_src=twsrc%5Etfw">#AbemaTV1周年</a><a href="https://twitter.com/hashtag/%E3%82%A2%E3%83%8B%E9%9B%91%E5%9B%A3?src=hash&amp;ref_src=twsrc%5Etfw">#アニ雑団</a><a href="https://t.co/NtOEhRXfZm">https://t.co/NtOEhRXfZm</a> <a href="https://t.co/YBQqYy2lWH">pic.twitter.com/YBQqYy2lWH</a></p>&mdash; 鳳モナハ (@ootorimonaha) <a href="https://twitter.com/ootorimonaha/status/859405208027226112?ref_src=twsrc%5Etfw">May 2, 2017</a></blockquote>

松嵜麗に指差して面白いよって言われてるの草。おもしれー女だ。

### 2017 年 8 月 15 日

5 月 2 日よりもアクセスが増えています。何があったのでしょう？

**松井恵理子・松嵜麗の声優アニ雑団〜カラオケ女子会 2 時間 SP！！** ！！！！！

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://abema.tv/channels/abema-special/slots/CDxD2Uvzv18JCf" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://hayabusa.io/abema/programs/90-90cnftfzficw_s0_p68/thumb001.w800.v1627680769.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>松井恵理子・松嵜麗の声優アニ雑団〜カラオケ女子会2時間SP！！ | 新しい未来のテレビ | ABEMA</q></span><span class="embed-html-box_description"><q>今夜はスタジオを飛び出して2時間、
アニソン歌いまくりカラオケボックスからお送りするスペシャル回！
スペシャルな夜に永野愛理さん、遠藤ゆりかさんをお迎えします！ご意見・ご感想・お悩み・イラストはこち… 出演者は、松井恵理子、松嵜麗、永野愛理、遠藤ゆりかです。</q></span></span></a></p></div>

またでした。この組み合わせにパワーがある。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">ツアー中なのにフリ完コピの永野愛理さんがガチすぎる<a href="https://twitter.com/hashtag/AbemaTV?src=hash&amp;ref_src=twsrc%5Etfw">#AbemaTV</a><a href="https://twitter.com/hashtag/%E3%82%A2%E3%83%8B%E9%9B%91%E5%9B%A3?src=hash&amp;ref_src=twsrc%5Etfw">#アニ雑団</a><a href="https://t.co/lwyil6Y3Z8">https://t.co/lwyil6Y3Z8</a> <a href="https://t.co/ujI1z8KYjT">pic.twitter.com/ujI1z8KYjT</a></p>&mdash; ことぶき (@kotobuki96) <a href="https://twitter.com/kotobuki96/status/897456742409224193?ref_src=twsrc%5Etfw">August 15, 2017</a></blockquote>

デレマス（松井恵理子）とデレマス（松嵜麗）と WUG（永野愛理）とバンドリ（遠藤ゆりか）でラブライブ！（Snow halation）歌った回でした。どうして？

### 2018 年 6 月 15 日

声優ユニット **Wake Up, Girls！ の解散** が発表された 2018 年 6 月 15 日にアクセス数が大きく増えています。

### 2019 年 3 月 8 日

声優ユニット **Wake Up, Girls！ のファイナルライブ** が行われた日、アクセスが増えています。

### 2019 年 9 月 20 日

控えめですがアクセスが増えています。

この日、TV アニメ **球詠** のキャスト情報が公開され、永野さんは **藤原理沙**役で出演が発表されました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://tamayomi.com" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://tamayomi.com/ogp2.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「球詠」公式サイト</q></span><span class="embed-html-box_description"><q>原作まんがタイムきららフォワードにて好評連載中！待望のTVアニメ、2020年春放送開始!!</q></span></span></a></p></div>

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【発表！】<a href="https://twitter.com/hashtag/%E7%90%83%E8%A9%A0?src=hash&amp;ref_src=twsrc%5Etfw">#球詠</a> 新越谷ナイン11名のキャスト&amp;キャラ設定解禁！<br><br>武田詠深 <a href="https://twitter.com/hashtag/%E5%89%8D%E7%94%B0%E4%BD%B3%E7%B9%94%E9%87%8C?src=hash&amp;ref_src=twsrc%5Etfw">#前田佳織里</a><br>山崎珠姫 <a href="https://twitter.com/hashtag/%E5%A4%A9%E9%87%8E%E8%81%A1%E7%BE%8E?src=hash&amp;ref_src=twsrc%5Etfw">#天野聡美</a><br>中村希 <a href="https://twitter.com/hashtag/%E9%87%8E%E5%8F%A3%E7%91%A0%E7%92%83%E5%AD%90?src=hash&amp;ref_src=twsrc%5Etfw">#野口瑠璃子</a><br>藤田菫 <a href="https://twitter.com/hashtag/%E6%A9%8B%E6%9C%AC%E9%9E%A0%E8%A1%A3?src=hash&amp;ref_src=twsrc%5Etfw">#橋本鞠衣</a><br>藤原理沙 <a href="https://twitter.com/hashtag/%E6%B0%B8%E9%87%8E%E6%84%9B%E7%90%86?src=hash&amp;ref_src=twsrc%5Etfw">#永野愛理</a><br>川﨑稜 <a href="https://twitter.com/hashtag/%E5%8C%97%E5%B7%9D%E9%87%8C%E5%A5%88?src=hash&amp;ref_src=twsrc%5Etfw">#北川里奈</a><br>川口息吹 <a href="https://twitter.com/hashtag/%E5%AF%8C%E7%94%B0%E7%BE%8E%E6%86%82?src=hash&amp;ref_src=twsrc%5Etfw">#富田美憂</a><br>岡田怜 <a href="https://twitter.com/hashtag/%E5%AE%AE%E6%9C%AC%E4%BE%91%E8%8A%BD?src=hash&amp;ref_src=twsrc%5Etfw">#宮本侑芽</a><br>大村白菊 <a href="https://twitter.com/hashtag/%E6%9C%AC%E6%B3%89%E8%8E%89%E5%A5%88?src=hash&amp;ref_src=twsrc%5Etfw">#本泉莉奈</a><br>川口芳乃 <a href="https://twitter.com/hashtag/%E7%99%BD%E5%9F%8E%E3%81%AA%E3%81%8A?src=hash&amp;ref_src=twsrc%5Etfw">#白城なお</a><br>藤井杏夏 <a href="https://twitter.com/hashtag/%E4%BD%B3%E6%9D%91%E3%81%AF%E3%82%8B%E3%81%8B?src=hash&amp;ref_src=twsrc%5Etfw">#佳村はるか</a><a href="https://twitter.com/hashtag/tamayomi?src=hash&amp;ref_src=twsrc%5Etfw">#tamayomi</a> <a href="https://t.co/Wt72HmNojx">pic.twitter.com/Wt72HmNojx</a></p>&mdash; TVアニメ『球詠』(たまよみ)公式 (@tamayomi_PR) <a href="https://twitter.com/tamayomi_PR/status/1175001660172767233?ref_src=twsrc%5Etfw">September 20, 2019</a></blockquote>

### 2020 年 6 月 21 日

水ヨナの仙台チャリティイベント「ヤゴサッハ」配信に合わせてアクセス数が増えているようです。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">／<a href="https://twitter.com/hashtag/%E3%83%A8%E3%83%AB%E3%83%8A%E3%82%A4%E3%83%88?src=hash&amp;ref_src=twsrc%5Etfw">#ヨルナイト</a> 水曜日 仙台チャリティーイベント「ヤゴサッハ」無料生配信<br>ご覧いただきありがとうございました😊💕<br>＼<br><br>笑いっぱなしの2時間30分‼️✨<a href="https://twitter.com/hashtag/%E4%BB%99%E5%8F%B0?src=hash&amp;ref_src=twsrc%5Etfw">#仙台</a> の魅力を存分に語らせていただにました🌍<br>仙台からのお取寄せ商品が美味しいものばかり！是非皆さんもお試しあれ🙆‍♀️<a href="https://twitter.com/hashtag/%E6%B0%B8%E9%87%8E%E6%84%9B%E7%90%86?src=hash&amp;ref_src=twsrc%5Etfw">#永野愛理</a>　<a href="https://twitter.com/hashtag/%E3%83%A4%E3%82%B4%E3%82%B5%E3%83%83%E3%83%8F?src=hash&amp;ref_src=twsrc%5Etfw">#ヤゴサッハ</a> <a href="https://t.co/TMc6VscNzc">pic.twitter.com/TMc6VscNzc</a></p>&mdash; 永野愛理 (@AiriEino) <a href="https://twitter.com/AiriEino/status/1274632480327208960?ref_src=twsrc%5Etfw">June 21, 2020</a></blockquote>

### 2020 年 7 月 30 日

**Rakuten.FM TOHOKU** で放送された EAGLES BASEBALL GAME SHOW のゲストに永野さんが出演した日のようです。趣味を仕事にしている声優を見ると羨ましくなっちゃう。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【楽天チケットpresents EAGLES BASEBALL GAME SHOW】<br><br>楽天イーグルスvs千葉ロッテ<br><br>ゲスト: <a href="https://twitter.com/hashtag/%E6%B0%B8%E9%87%8E%E6%84%9B%E7%90%86?src=hash&amp;ref_src=twsrc%5Etfw">#永野愛理</a>（イーグルス大好き声優）　<br>実況:河内一朗<br><br>先発ピッチャーは <a href="https://twitter.com/hashtag/%E5%BC%93%E5%89%8A%E9%9A%BC%E4%BA%BA?src=hash&amp;ref_src=twsrc%5Etfw">#弓削隼人</a> 選手<br>行け！掴め！3勝目🔥☕<br><br>声援メッセージはTwitterから <a href="https://twitter.com/hashtag/r891?src=hash&amp;ref_src=twsrc%5Etfw">#r891</a> をつけて投稿又はラジオHPのメッセージフォームまで📩 <a href="https://t.co/5P2vbZPVej">pic.twitter.com/5P2vbZPVej</a></p>&mdash; Rakuten.FM TOHOKU (@rakutenfmtohoku) <a href="https://twitter.com/rakutenfmtohoku/status/1288758421357867009?ref_src=twsrc%5Etfw">July 30, 2020</a></blockquote>

### 2020 年 10 月 14 日

7 月 30 日と同様に Rakuten.FM TOHOKU EAGLES BASEBALL GAME SHOW のゲスト出演のようです。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【楽天チケットpresents EAGLES BASEBALL GAME SHOW!!】<br><br>10/14(水)17:50〜<br>千葉ロッテvs楽天イーグルス<br><br>応援ゲスト:<a href="https://twitter.com/hashtag/%E6%B0%B8%E9%87%8E%E6%84%9B%E7%90%86?src=hash&amp;ref_src=twsrc%5Etfw">#永野愛理</a> さん<br>実況:河内一朗<br><br>先発は、<a href="https://twitter.com/hashtag/%E6%B6%8C%E4%BA%95%E7%A7%80%E7%AB%A0?src=hash&amp;ref_src=twsrc%5Etfw">#涌井秀章</a> 選手⚾️<br><br>チーム・選手への応援メッセージ大募集📩<br><br>📻<a href="https://t.co/FQm2a5YlH0">https://t.co/FQm2a5YlH0</a><a href="https://twitter.com/hashtag/r891?src=hash&amp;ref_src=twsrc%5Etfw">#r891</a> <a href="https://t.co/pmVQTMKDzd">pic.twitter.com/pmVQTMKDzd</a></p>&mdash; Rakuten.FM TOHOKU (@rakutenfmtohoku) <a href="https://twitter.com/rakutenfmtohoku/status/1316300251314163713?ref_src=twsrc%5Etfw">October 14, 2020</a></blockquote>

### 2021 年 4 月 18 日

アズールレーンに出演することが発表された日のようです。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【艦船紹介】<br>駆逐艦　リベッチオ<br>サディア帝国所属の駆逐艦<br>明るく元気で素直な性格で、感情に忠実なはっきりと言うタイプ。<br>口下手な姉妹艦・マエストラーレとは仲良しで、友達を作らせたりするなど何かと心配りしている。<br><br>期間限定建造にて登場予定！<a href="https://twitter.com/hashtag/%E3%82%A2%E3%82%BA%E3%83%BC%E3%83%AB%E3%83%AC%E3%83%BC%E3%83%B3?src=hash&amp;ref_src=twsrc%5Etfw">#アズールレーン</a> <a href="https://t.co/XiMCBegqMK">pic.twitter.com/XiMCBegqMK</a></p>&mdash; アズールレーン公式 (@azurlane_staff) <a href="https://twitter.com/azurlane_staff/status/1383691771218124800?ref_src=twsrc%5Etfw">April 18, 2021</a></blockquote>

## 田中美海さん

<figure>
  <center>
    <a href="https://i.imgur.com/yo7X3C1.png"><img src="https://i.imgur.com/yo7X3C1.png"></a>
    <figcaption>Wikipedia: 田中美海 のアクセス数</figcaption>
  </center>
</figure>

### 2016 年 1 月 10 日 - 13 日

2016 年 1 月、アクセス数が増えています。何があったのでしょう。

1 月 10 日は、TV アニメ『**シュヴァルツェスマーケン**』『**魔法少女なんてもういいですから。**』の第 1 話放送日でした。ほぼシュヴァケンっぽいです。

シュヴァケンではメインヒロインの **カティア・ヴァルトハイム**役 を務めており、大活躍でしたね。ちなみにまほいいではアニメオリジナルキャラクターの金髪ツインテール女子小学生 **だいや**役でした。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://schwarzesmarken-anime.jp/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://schwarzesmarken-anime.jp//ogp.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>アニメ『シュヴァルツェス マーケン』オフィシャルサイト</q></span><span class="embed-html-box_description"><q>アニメ『シュヴァルツェス マーケン』オフィシャルサイト 2016年1月より放送開始!</q></span></span></a></p></div>
<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.smiral-label.com/mahoii/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://www.smiral-label.com/mahoii/img/mahoshoujo_logo.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>アニメ『魔法少女なんてもういいですから。』公式サイト</q></span><span class="embed-html-box_description"><q>はいはい、いま変身しますから…。 双見酔が描く新感覚魔法少女コミック、2016年1月アニメ化決定！！</q></span></span></a></p></div>

### 2016 年 2 月 29 日頃

**グランブルーファンタジー**において、2 月 29 日より、期間限定イベント「舞い歌う五花」が開催されました。田中さんはイベントキャラクター **リナリア**役で出演していました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【グランブルーファンタジー】新召喚石「リナリア」登場！（CV.田中美海）<br>『可愛い』と褒められることが大好きで、可愛さでナンバー１になるためならばどんな努力も惜しまない。卒業間近の巫女・ディアンサをライバル視している。 <a href="https://twitter.com/hashtag/%E3%82%B0%E3%83%A9%E3%83%96%E3%83%AB?src=hash&amp;ref_src=twsrc%5Etfw">#グラブル</a> <a href="https://t.co/Ekh0u4xUAJ">pic.twitter.com/Ekh0u4xUAJ</a></p>&mdash; グランブルーファンタジー (@granbluefantasy) <a href="https://twitter.com/granbluefantasy/status/704260679545413632?ref_src=twsrc%5Etfw">February 29, 2016</a></blockquote>

この日は他にも『まほいい』にだいやがまともに出てきた回が放送されたりしています。

### 2016 年 7 月 25 日

スマートフォンゲーム **Fate/Grand Order** に **ニトクリス** が登場し、CV が田中美海と判明した日です。はぇ〜〜〜。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">「Fate/Grand Order」新CAST<br>ニトクリス：田中美海<br>静謐のハサン：千本木彩花<br>ランスロット：置鮎龍太郎<br>オジマンディアス：子安武人<br>俵藤太：鈴村健一 <a href="https://t.co/jmeoopZond">pic.twitter.com/jmeoopZond</a></p>&mdash; ANIME SEIYU (@animeseiyu) <a href="https://twitter.com/animeseiyu/status/757691441384595456?ref_src=twsrc%5Etfw">July 25, 2016</a></blockquote>

### 2016 年 10 月 4 日

TV アニメ『**灼熱の卓球娘**』第 1 話の放送日です。田中さんは準主人公 **上矢あがり**役で出演しています。OP とかも歌ってます。ED は **Wake Up, Girls！**。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://syakunetsu.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://syakunetsu.com/assets/images/ogimage2.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「灼熱の卓球娘」公式サイト</q></span><span class="embed-html-box_description"><q>「灼熱の卓球娘」TVアニメ化決定！集英社「となりのヤングジャンプ」にて連載中。原作：朝野やぐら、アニメーション制作：キネマシトラス</q></span></span></a></p></div>

### 2016 年 12 月 6 日

『**Fate/Grand Order**』のラジオ番組『**カルデア・ラジオ局**』
が 2017 年 1 月に放送開始し、パーソナリティに田中美海さんが発表されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">高橋李依さん、田中美海さんがパーソナリティを務めるラジオ番組『Fate／Grand Order カルデア・ラジオ局』が文化放送（地上波）、文化放送「超！A&amp;G＋」で放送開始！<a href="https://t.co/1ok2UP04UU">https://t.co/1ok2UP04UU</a> <a href="https://twitter.com/hashtag/joqr?src=hash&amp;ref_src=twsrc%5Etfw">#joqr</a> <a href="https://twitter.com/hashtag/agqr?src=hash&amp;ref_src=twsrc%5Etfw">#agqr</a> <a href="https://twitter.com/hashtag/FateGO?src=hash&amp;ref_src=twsrc%5Etfw">#FateGO</a></p>&mdash; FGO カルデア・ラジオ局 Plus (@fgojoqr) <a href="https://twitter.com/fgojoqr/status/806116720477802497?ref_src=twsrc%5Etfw">December 6, 2016</a></blockquote>

### 2016 月 12 月 21 日

この日、 **『Fate/Grand Order カルデア・ラジオ局』 事前特番スペシャル** が放送されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【カルデア広報局より】<br>明日、12月21日(水)21時より「Fate/Grand Order カルデア・ラジオ局　事前特番スペシャル」を放送！詳しくは番組Twitter(<a href="https://twitter.com/fgojoqr?ref_src=twsrc%5Etfw">@fgojoqr</a>)や公式サイトをご覧ください⇒<a href="https://t.co/uR3boyn0Wi">https://t.co/uR3boyn0Wi</a> <a href="https://twitter.com/hashtag/FateGO?src=hash&amp;ref_src=twsrc%5Etfw">#FateGO</a></p>&mdash; 【公式】Fate/Grand Order (@fgoproject) <a href="https://twitter.com/fgoproject/status/811149777471553536?ref_src=twsrc%5Etfw">December 20, 2016</a></blockquote>

### 2017 年 1 月 7 日 〜 10 日

ここらへんの期間でアクセスが多めです。

1 月 7 日は **Fate/Grand Order カルデア・ラジオ局** 第 1 回の **文化放送** での放送日のようです。 10 日は **A&G+** での放送日。 間もアクセス多いのはなんでなんですかね？リピート放送とかあるんでしたっけ。

この後もしばらく 1 週間毎に若干アクセス数が増えてます。

### 2017 年 3 月 18 日

数日にわたってすごいアクセスがあります。なんだこれ。

**第 11 回声優アワード** が発表され、田中さんが **新人賞** を受賞しました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">■新人賞<br>小澤 亜李（おざわ・あり） / 所属：アイムエンタープライズ<br>千本木 彩花（せんぼんぎ・さやか） / 所属：アイムエンタープライズ<br>田中 美海（たなか・みなみ） / 所属：81プロデュース<a href="https://twitter.com/hashtag/%E5%A3%B0%E5%84%AA%E3%82%A2%E3%83%AF%E3%83%BC%E3%83%89?src=hash&amp;ref_src=twsrc%5Etfw">#声優アワード</a></p>&mdash; 声優アワード実行委員会 (@seiyuawards) <a href="https://twitter.com/seiyuawards/status/843026769275895808?ref_src=twsrc%5Etfw">March 18, 2017</a></blockquote>
<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【声優アワード 田中美海さんが新人賞を受賞しました！】<br>本日開催の声優アワードにて、<br>田中美海さんが新人賞を受賞しました！<br>本当におめでとうございます！<a href="https://twitter.com/hashtag/WUG_JP?src=hash&amp;ref_src=twsrc%5Etfw">#WUG_JP</a> <a href="https://twitter.com/hashtag/%E7%94%B0%E4%B8%AD%E7%BE%8E%E6%B5%B7?src=hash&amp;ref_src=twsrc%5Etfw">#田中美海</a> <a href="https://t.co/cUahJcgTpu">pic.twitter.com/cUahJcgTpu</a></p>&mdash; Wake Up, Girls！公式 (@wakeupgirls_PR) <a href="https://twitter.com/wakeupgirls_PR/status/843094642010808320?ref_src=twsrc%5Etfw">March 18, 2017</a></blockquote>

おめでとうございます。

### 2017 年 7 月 1 日 〜 10 月くらいまで

7 月 1 日より、TV アニメ『**賭ケグルイ**』（第 1 シーズン）が放送されました。田中さんは、ライバル？の **早乙女芽亜里**役 で出演されています。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://kakegurui-anime.com/1st/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://kakegurui-anime.com/1st/images/first_catch_k.gif);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「賭ケグルイ」公式サイト</q></span><span class="embed-html-box_description"><q>2017年7月よりTOKYO MX、MBSほかにて放送開始。原作：河本ほむら・尚村 透（月刊「ガンガンJOKER」にて連載中）監督：林 祐一郎、シリーズ構成：小林靖子、キャラクターデザイン：秋田 学、音楽：TECHNOBOYS PULCRAFT GREEN-FUND、制作：MAPPA、キャスト：早見沙織、田中美海、徳武竜也、若井友希、奈波果林、伊瀬茉莉也、芹澤 優、杉田智和、鵜殿麻由、福原綾香、沢城みゆき</q></span></span></a></p></div>

ちなみに 2022 年 8 月 からは、芽亜里が主人公のスピンオフ（前日譚） **賭ケグルイ双** が配信されるらしいのでお楽しみに[^twin]！

[^twin]: 賭ケグルイの原作持ってないのに賭ケグルイ双は全巻持ってるのでおすすめですよ！

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://kakegurui-twin-anime.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://kakegurui-twin-anime.com/assets/og/og.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>NETFLIXシリーズ「賭ケグルイ双」公式サイト</q></span><span class="embed-html-box_description"><q>2022年8月 NETFLIX全世界独占配信。原作：河本ほむら・斎木桂「賭ケグルイ双」、原作 ：河本ほむら・尚村透「賭ケグルイ」（掲載　月刊「ガンガンJOKER」スクウェア・エニックス刊）、制作：MAPPA、キャスト：田中美海　ほか</q></span></span></a></p></div>

### 2017 年 7 月 30 日

賭ケグルイの影にいますが、この日は他よりアクセスが多めです。

この日、『**Fate/Grand Order Fes. 2017 ～ 2nd Anniversary ～**』が開催されており、その中で行われた『**Fate/Grand Order カルデア放送局 2 周年 SP**』にゲスト出演しました。ニトクリスを意識した衣装で話題になっていましたね。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【カルデア広報局より】<br>本日の「Fate/Grand Order」カルデア放送局 2周年SPをご覧頂き、ありがとうございました！番組終了後に撮影させていただいた出演キャスト皆様の記念写真をお届け！ <a href="https://twitter.com/hashtag/FateGO?src=hash&amp;ref_src=twsrc%5Etfw">#FateGO</a> <a href="https://t.co/0EPn2lGo43">pic.twitter.com/0EPn2lGo43</a></p>&mdash; 【公式】Fate/Grand Order (@fgoproject) <a href="https://twitter.com/fgoproject/status/891527534528966657?ref_src=twsrc%5Etfw">July 30, 2017</a></blockquote>

また『**Fate/Grand Order カルデア・ラジオ局**』公開生放送も行われました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【FGO Fes. 2017】 <br>『カルデア・ラジオ局 公開生放送』をご覧下さった皆さん、ありがとうございました！明日のゲストは島崎信長さんです！こちらもお楽しみに！<br><br>最後に川澄綾子さんと一枚！<a href="https://twitter.com/hashtag/FateGo?src=hash&amp;ref_src=twsrc%5Etfw">#FateGo</a> <a href="https://twitter.com/hashtag/FGO%E3%83%A9%E3%82%B8%E3%82%AA?src=hash&amp;ref_src=twsrc%5Etfw">#FGOラジオ</a> <a href="https://t.co/wUJYhcPM22">pic.twitter.com/wUJYhcPM22</a></p>&mdash; FGO カルデア・ラジオ局 Plus (@fgojoqr) <a href="https://twitter.com/fgojoqr/status/891111770684768256?ref_src=twsrc%5Etfw">July 29, 2017</a></blockquote>
<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【FGO Fes. 2017】 <br>『カルデア・ラジオ局 公開生放送』をご覧頂きありがとうございました！<br>イベントやステージの感想はfgo@joqr.netでお待ちしています！<br><br>最後に島﨑信長さんとの一枚！<a href="https://twitter.com/hashtag/FateGo?src=hash&amp;ref_src=twsrc%5Etfw">#FateGo</a> <a href="https://twitter.com/hashtag/FGO%E3%83%A9%E3%82%B8%E3%82%AA?src=hash&amp;ref_src=twsrc%5Etfw">#FGOラジオ</a> <a href="https://t.co/gU9A6Ti2qY">pic.twitter.com/gU9A6Ti2qY</a></p>&mdash; FGO カルデア・ラジオ局 Plus (@fgojoqr) <a href="https://twitter.com/fgojoqr/status/891473072967962626?ref_src=twsrc%5Etfw">July 30, 2017</a></blockquote>

### 2017 年 11 月 28 日

『**Fate/Grand Order カルデア放送局 Vol.8 異端なるセイレム 配信直前 SP**』が放送され、ゲストで田中さんも出演しました。Fate 力すごいな。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【カルデア広報局より】<br>「Fate/Grand Order カルデア放送局Vol.8 異端なるセイレム 配信直前SP」をご覧頂きました皆様ありがとうございました！ご出演頂いた皆様の記念写真をお届けいたします！ <a href="https://twitter.com/hashtag/FateGO?src=hash&amp;ref_src=twsrc%5Etfw">#FateGO</a> <a href="https://t.co/kQCE6A8vJF">pic.twitter.com/kQCE6A8vJF</a></p>&mdash; 【公式】Fate/Grand Order (@fgoproject) <a href="https://twitter.com/fgoproject/status/935507958795943936?ref_src=twsrc%5Etfw">November 28, 2017</a></blockquote>

### 2018 年 5 月 27 日, 28 日, 29 日

え…？ 何だっけこれ……

**第 34 回 鹿島ガタリンピック** でした。27 日に開催され、現場の人が報告したツイートが伸び、

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">ガタリンピックに出てた声優さん、田中美海さんと言うらしい。<br>ツィート全部がハネ上がった！すごすぎ <a href="https://t.co/xo6FGB4C0M">pic.twitter.com/xo6FGB4C0M</a></p>&mdash; ヤツえもん (@AdustayUz) <a href="https://twitter.com/AdustayUz/status/1000739185198682113?ref_src=twsrc%5Etfw">May 27, 2018</a></blockquote>

28 日の朝日新聞デジタルにも写っていたことでも話題になり、

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.asahi.com/articles/ASL5W5W38L5WTTHB00C.html" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://www.asahicom.jp/articles/images/c_AS20180527001884_comm.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>佐賀）鹿島市で「ガタリンピック」１５００人が泥まみれ：朝日新聞デジタル</q></span><span class="embed-html-box_description"><q>　「干潟のオリンピック」とも言われる鹿島ガタリンピックが２７日、佐賀県鹿島市の有明海干潟であった。今年で３４回目で、大人から子どもまで、国内外から延べ約１５００人が泥まみれになりながら楽しんだ。　競技…</q></span></span></a></p></div>

ハフポスト日本版[^huff]にも取り上げられて検索数が伸びたようですね。

[^huff]: ハフポスト、朝日新聞と提携してるのでその関連かと思ったんですが、記事的にインターネットでバズってるの取り上げただけっぽいですね。これ権利的にどうなんや。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.huffingtonpost.jp/2018/05/28/tanaka-minami_a_23444906/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://img.huffingtonpost.com/asset/5c638ffc20000001016e56ee.jpeg?ops=1200_630);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>声優の田中美海さん、ドロンコになった姿が「可愛い」と話題に（動画・写真）</q></span><span class="embed-html-box_description"><q>「Wake Up, Girls!」など出演の人気声優が有明海の「ガタリンピック」に出場した。</q></span></span></a></p></div>

### 2018 年 6 月 15 日

声優ユニット **Wake Up, Girls！ の解散** が発表された 2018 年 6 月 15 日にアクセス数が大きく増えています。

### 2018 年 10 月 頃 〜

かなり増えてますね。

TV アニメ『**ゾンビランドサガ**』です。田中さんは ゾンビィ６号 **星川リリィ**役 で出演しています。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://zombielandsaga.com/1st/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://zombielandsaga.com/1st/images/ogp3.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「ゾンビランドサガ」公式サイト</q></span><span class="embed-html-box_description"><q>TVアニメ2期「ゾンビランドサガ リベンジ」制作決定！復讐という名の続篇の幕が上がってしまった。</q></span></span></a></p></div>

特にアクセスが多い 11 月 22 日, 23 日 はリリィが中心になった回 **第八話 GOGO ネバーランド SAGA** の放送日です。この回マジで良いのでみんな何回も見て何回も泣いてください。

### 2018 年 12 月 15 日

この日も特に増えています。ゾンビランドサガの放送日ではないので何かあるはずです。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://cygamesfes.jp/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://cygamesfes.jp/assets/images/ogp.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>CygamesFes2018特設サイト【サイゲフェス】 | Cygames</q></span><span class="embed-html-box_description"><q>CygamesFes2018【サイゲフェス】12月15日｜16日に幕張メッセ1～6ホールで開催！</q></span></span></a></p></div>

**CygamesFes2018**でした。ゾンビランドサガのトークや**フランシュシュ**初のライブなどが行われました。abemaTV でも配信されていました。

### 2019 年 3 月 8 日

声優ユニット **Wake Up, Girls！ のファイナルライブ** が行われた日、アクセスが増えています。

### 2019 年 3 月 17 日

**ゾンビランドサガ LIVE ～フランシュシュみんなでおらぼう！～** の開催日です。ライブビューイングもありました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://zombielandsaga.com/1st/event/detail.php?id=1070824" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://zombielandsaga.com/1st/images/ogp3.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>EVENT｜TVアニメ「ゾンビランドサガ」公式サイト</q></span><span class="embed-html-box_description"><q>2019年3月17日『ゾンビランドサガLIVE～フランシュシュみんなでおらぼう！～』</q></span></span></a></p></div>

**邪神ちゃんドロップキック** 2 期の新キャストとして発表されたのもこの日ですがこっちの影響は軽微そう

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="http://jashinchan.com/news/239" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://jashinchan.com/wp-content/uploads/2019/03/2-300x169.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>キョンシー姉妹役に山下七海さんと田中美海さんが決定！ | 邪神ちゃんドロップキック DROPKICK ON MY DEVIL!!</q></span><span class="embed-html-box_description"><q>2期の新キャスト「キョンキョン」と「キョンキョンの姉」のキャスト発表を行いました！新たなメンバー山下七海さんと田中美海さ…</q></span></span></a></p></div>

### 2019 年 4 月 6 日 〜 6 月頃

TV アニメ『**ひとりぼっちの ○○ 生活**』第 1 話の放送日です。田中さんは **砂尾なこ**役 で出演しています。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="http://hitoribocchi.jp/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_metano-image"><span class="embed-html-box_title"><q>TVアニメ「ひとりぼっちの○○生活」公式サイト</q></span><span class="embed-html-box_description"><q>「コミック電撃だいおうじ」にて大好評連載中の『ひとりぼっちの○○生活』がアニメ化！ぼっち少女による“脱”ぼっちコメディー。2019年4月、TVアニメ放送開始！</q></span></span></a></p></div>

### 2019 年 7 月 27 日

『**ゾンビランドサガ LIVE ～フランシュシュみんなでおらぼう！～ in SAGA**』 の開催日です。佐賀凱旋ライブ。【特別協力】佐賀県、【後援】唐津市 で草。今回もライブビューイングがありました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://zombielandsaga.com/1st/event/detail.php?id=1073953" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://zombielandsaga.com/1st/images/ogp3.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>EVENT｜TVアニメ「ゾンビランドサガ」公式サイト</q></span><span class="embed-html-box_description"><q>2019年7月27日「ゾンビランドサガLIVE～フランシュシュみんなでおらぼう！～in SAGA」</q></span></span></a></p></div>

### 2019 年 8 月 3 日, 4 日

『**Fate/Grand Order Fes. 2019 ～カルデアパーク～**』が開催されていました。両日とも『**「Fate/Grand Order カルデア・ラジオ局 Plus」 Fes 出張版**』が行われ、『**FGO バラエティトークステージ　 Day1**』や『**「Fate/Grand Order Arcade」 カルデア・アーケード放送局 ～ FGO Fes. 2019 特番～**』、『**「Fate/Grand Order」カルデア放送局 4 周年 SP**』などにゲストとして登場しました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://fes.fate-go.jp/2019/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://fes.fate-go.jp/2019/og_fgofes2019.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Fate/Grand Order Fes. 2019 ～カルデアパーク～</q></span><span class="embed-html-box_description"><q>8月3日(土)・4日(日)　幕張メッセ国際展示場4～7ホール</q></span></span></a></p></div>

普通に会場内を歩く田中氏

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">田中氏、普通に会場内歩きます。ステージとステージの合間の配信で登場しますよ〜！！カルデアパークの雰囲気が伝わるはず…！✨現地にいる方はあたたけえ目でみてくれよな…。<a href="https://twitter.com/hashtag/FGO4%E5%91%A8%E5%B9%B4?src=hash&amp;ref_src=twsrc%5Etfw">#FGO4周年</a> <a href="https://twitter.com/hashtag/FGO%E3%83%95%E3%82%A7%E3%82%B9?src=hash&amp;ref_src=twsrc%5Etfw">#FGOフェス</a> <a href="https://t.co/A9ong7zMsn">pic.twitter.com/A9ong7zMsn</a></p>&mdash; 田中美海 (@minazou_373) <a href="https://twitter.com/minazou_373/status/1157502066199162880?ref_src=twsrc%5Etfw">August 3, 2019</a></blockquote>

### 2019 年 12 月 18 日

『**「Fate/Grand Order カルデア放送局 Vol.12 神を撃ち落とす日 配信直前 SP」**』にゲスト出演しました。カルデア放送局すごいな。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【カルデア広報局より】<br>「Fate/Grand Order カルデア放送局 Vol.12 神を撃ち落とす日 配信直前SP」をご覧いただき、ありがとうございました！番組にご出演いただいた川澄綾子さん、河西健吾さん、田中美海さん、マフィア梶田さんの写真をお届け！ <a href="https://twitter.com/hashtag/FGO?src=hash&amp;ref_src=twsrc%5Etfw">#FGO</a> <a href="https://t.co/QAbZiN63el">pic.twitter.com/QAbZiN63el</a></p>&mdash; 【公式】Fate/Grand Order (@fgoproject) <a href="https://twitter.com/fgoproject/status/1207276170321915905?ref_src=twsrc%5Etfw">December 18, 2019</a></blockquote>

### 2019 年 12 月 31 日

『**Fate Project 大晦日 TV スペシャル 2019**』が TOKYO MX、群馬テレビ、とちぎテレビ、BS11、ニコニコ生放送、AbemaTV で放送・配信されました[^fa]。Fate パワーすご。田中さんは赤羽根健治さんと一緒に MC を務めました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://prtimes.jp/main/html/rd/p/000002061.000016356.html" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://prtimes.jp/i/16356/2061/ogp/d16356-2061-174398-0.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>『Fate Project 大晦日TVスペシャル2019』が12月31日放送・配信決定！</q></span><span class="embed-html-box_description"><q>株式会社アニプレックスのプレスリリース（2019年12月18日 20時05分）『Fate Project 大晦日TVスペシャル2019』が12月31日放送・配信決定！</q></span></span></a></p></div>

[^fa]: 公式サイトが同じ URL で 2020 年版になっててどうしようもなかったので PR TIMES へのリンクです。

### 2020 年 8 月 10 日

『**Fate/Grand Order カルデア放送局 5 周年 SP ～ under the same sky ～**』が配信されました。このときの全国の新聞に全面広告出すやつかなり好き。Fate パワーエグ。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://5th.fate-go.jp/broadcast/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://5th.fate-go.jp/broadcast/assets/siteinfo/og_image.png?0807);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>カルデア放送局5周年SP</q></span><span class="embed-html-box_description"><q>カルデア放送局5周年SP 2020/8/10（月）15:30～（※事前配信 15:15～）より各配信サイトにて配信</q></span></span></a></p></div>

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【カルデア広報局より】<br>「Fate/Grand Order カルデア放送局 5周年SP ～under the same sky～」の配信をご視聴いただきありがとうございました。出演者のみなさまのお写真をお届け！ <a href="https://twitter.com/hashtag/FGO?src=hash&amp;ref_src=twsrc%5Etfw">#FGO</a> <a href="https://twitter.com/hashtag/FGO5%E5%91%A8%E5%B9%B4?src=hash&amp;ref_src=twsrc%5Etfw">#FGO5周年</a> <a href="https://t.co/eYMJOhbAn0">pic.twitter.com/eYMJOhbAn0</a></p>&mdash; 【公式】Fate/Grand Order (@fgoproject) <a href="https://twitter.com/fgoproject/status/1292754282886737920?ref_src=twsrc%5Etfw">August 10, 2020</a></blockquote>

### 2020 年 12 月 12 日

『**グラブルフェス 2020**』内で行われた『**グラブルナイトパーティー**』に**リナリア**役で出演しました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://fes.granbluefantasy.jp/2020/nightparty/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://fes.granbluefantasy.jp/2020/assets2020/images/share/ogp.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>グラブルフェス2020公式サイト | グランブルーファンタジー</q></span><span class="embed-html-box_description"><q>グランブルーファンタジー『グラブルフェス2020』12月12日（土）、13日（日）にオンライン開催！ #グラブル #グラブルフェス2020</q></span></span></a></p></div>

### 2021 年 4 月 5 日 〜 7 月頃

4 月 5 日は TV アニメ『**やくならマグカップも**』の放送日（TOKYO MX, BS11）でした。田中さんは主人公 **豊川姫乃**役 を務めています。また、実写パート『**やくならマグカップも-やくもの放課後-**』にも実写で出演しています。田中美海父の話題でざわついてました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://yakumo-project.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://yakumo-project.com/assets/img/ogp3.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ＆実写『やくならマグカップも 二番窯』</q></span><span class="embed-html-box_description"><q>2021年10月より第2期テレビ放送開始！最高気温40.9度、陶芸の町、多治見を舞台に繰り広げられる、ほんわか青春ろくろアニメ！</q></span></span></a></p></div>

また 2020 年 4 月クールはやくもの他にも『**ゾンビランドサガ リベンジ**』（星川リリィ役）、『**スライム倒して 300 年、知らないうちにレベル MAX になってました**』（シャルシャ役）に出演しており、常にアクセスが多い状況になっています。解析不能。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://zombielandsaga.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://zombielandsaga.com/assets/img/ogp2.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「ゾンビランドサガ リベンジ」公式サイト</q></span><span class="embed-html-box_description"><q>TVアニメ「ゾンビランドサガ リベンジ」2021年4月8日よりTOKYO MX、AT-Xほかにて放送開始！Amazon Prime Video、ABEMAにて地上波先行独占配信！運命への“リベンジ”が始まる...</q></span></span></a></p></div>
<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://slime300-anime.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://slime300-anime.com/static/adec698e0e86d4ed2e1b0a1a8676a8cb/ogp.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「スライム倒して300年、知らないうちにレベルMAXになってました」公式サイト</q></span><span class="embed-html-box_description"><q>TOKYO MX・BS11・AT-Xほかにて2021年4月10日より放送開始！高原の魔女・アズサと仲間たちが繰り広げるのんびりドタバタスローライフコメディ、始まります！</q></span></span></a></p></div>

5 月 7 日のアクセス数の多さはゾンビランドサガ リベンジがリリィ回だったからだと思います。

### 2021 年 6 月 10 日

**月姫** リメイクの情報が解禁され、**弓塚さつき**役で田中美海さんが出演することが明らかになりました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">“TYPE-MOON TIMES”Vol.2　レポート③<br><br>『月姫 -A piece of blue glass moon-』第2弾PVも公開！<br><br>新たに、乾有彦（CV.古川慎さん）・弓塚さつき（CV.田中美海さん）・蒼崎青子（CV.戸松遥さん）のキャラクターボイスも解禁しております。<br><br>ぜひご覧ください⇓<a href="https://t.co/83NMJvHSZH">https://t.co/83NMJvHSZH</a><a href="https://twitter.com/hashtag/%E6%9C%88%E5%A7%AB?src=hash&amp;ref_src=twsrc%5Etfw">#月姫</a></p>&mdash; 【公式】月姫 (@TM_TSUKIHIME) <a href="https://twitter.com/TM_TSUKIHIME/status/1402982483143000070?ref_src=twsrc%5Etfw">June 10, 2021</a></blockquote>

### 2021 年 7 月 30 日

**Fate/Grand Order カルデアラジオ局プラス 終局特異点 冠位時間神殿ソロモン公開記念スペシャル** が 文化放送超!A&G+、ニコニコ生放送、ABEMA、YouTube Live、Twitter Live で配信されました。Fate 力すごい。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://prtimes.jp/main/html/rd/p/000003114.000016356.html" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://prtimes.jp/i/16356/3114/ogp/d16356-3114-86d251244fe23e8abce7-0.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>『Fate/Grand Order -終局特異点 冠位時間神殿ソロモン-』コラボ配信「FGOカルデアラジオ局プラス 冠位時間神殿ソロモン公開記念スペシャル」７月３０日（金）実施決定！</q></span><span class="embed-html-box_description"><q>株式会社アニプレックスのプレスリリース（2021年7月14日 19時40分）『Fate/Grand Order -終局特異点 冠位時間神殿ソロモン-』コラボ配信[FGOカルデアラジオ局プラス 冠位時間神殿ソロモン公開記念スペシャル]７月３０日（金）実施決定！</q></span></span></a></p></div>

### 2021 年 10 月 16 日, 17 日

**ゾンビランドサガ LIVE ～フランシュシュ 佐賀よ共にわいてくれ～**が開催され、ミクチャでのライブビューイングも行われました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://zombielandsaga.com/event/detail.php?id=1089446&c=media" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://zombielandsaga.com/assets/img/ogp2.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>ゾンビランドサガLIVE～フランシュシュ 佐賀よ共にわいてくれ～ - TVアニメ「ゾンビランドサガ リベンジ」公式サイト</q></span><span class="embed-html-box_description"><q>TVアニメ「ゾンビランドサガ リベンジ」2021年4月8日よりTOKYO MX、AT-Xほかにて放送開始！Amazon Prime Video、ABEMAにて地上波先行独占配信！運命への“リベンジ”が始まる...</q></span></span></a></p></div>

## 青山吉能さん

<figure>
  <center>
    <a href="https://i.imgur.com/jrkAaE2.png"><img src="https://i.imgur.com/jrkAaE2.png"></a>
    <figcaption>Wikipedia: 青山吉能 のアクセス数</figcaption>
  </center>
</figure>

細かくてあれなので拡大したやつも載せときます。

<figure>
  <center>
    <a href="https://i.imgur.com/BBkKRiw.png"><img src="https://i.imgur.com/BBkKRiw.png"></a>
    <figcaption>Wikipedia: 青山吉能 のアクセス数 拡大版</figcaption>
  </center>
</figure>

### 2015 年 12 月 11 日 - 14 日

12 月 11 日は **ハッカドール THE あにめ〜しょん** 第 11 話の放送日でした。青山吉能さんは **ゆっぴー** 役で出演されていました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://hackadoll-anime.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://hackadoll-anime.com/assets/img/hacka_ogp.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「ハッカドール THE あにめ～しょん」公式サイト</q></span><span class="embed-html-box_description"><q>「ハッカドール THE あにめ～しょん」TOKYO/MX、BS11にて放送開始！</q></span></span></a></p></div>

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【第⑪話　ご覧頂いた皆さま、ありがとうございました】最後は…今回のゲストですよっ！ゆっぴー役のよっぴー・*・:≡( ε:)こと青山吉能さんでしたっ！　<a href="https://twitter.com/hashtag/%E3%83%8F%E3%83%83%E3%82%AB%E3%83%89%E3%83%BC%E3%83%AB?src=hash&amp;ref_src=twsrc%5Etfw">#ハッカドール</a>　<a href="https://twitter.com/hashtag/%E3%83%8F%E3%83%83%E3%82%AB%E3%82%A2%E3%83%8B%E3%83%A1?src=hash&amp;ref_src=twsrc%5Etfw">#ハッカアニメ</a>　<a href="https://twitter.com/hashtag/%E9%9D%92%E5%B1%B1%E5%90%89%E8%83%BD?src=hash&amp;ref_src=twsrc%5Etfw">#青山吉能</a> <a href="https://t.co/gUuAmLk9mV">pic.twitter.com/gUuAmLk9mV</a></p>&mdash; 公式ハッカドール THE あにめ～しょん (@Hackadoll_anime) <a href="https://twitter.com/Hackadoll_anime/status/675318970031804416?ref_src=twsrc%5Etfw">December 11, 2015</a></blockquote>

14 日に配信が始まったりしてるんですが、あいだずっと多いの分からないです。なんで？

13 日には **アニメ JAM 2015** が開催され、WUG が出演していますが、他の WUG メンバーは増えてないのでなあ

### 2016 年 1 月 27 日

FIVE STARS チャンネル・超!A&G+で放送された『**A&G NEXT BREAKS 田中美海の FIVE STARS**』 #43 に飛び入りゲストで参加しています。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">というわけで飛び入りゲストの青山吉能さんです！ <a href="https://twitter.com/hashtag/ag_5stars?src=hash&amp;ref_src=twsrc%5Etfw">#ag_5stars</a> <a href="https://twitter.com/hashtag/agqr?src=hash&amp;ref_src=twsrc%5Etfw">#agqr</a></p>&mdash; FIVE STARS (@ag_five_stars) <a href="https://twitter.com/ag_five_stars/status/692309937599320064?ref_src=twsrc%5Etfw">January 27, 2016</a></blockquote>

### 2016 年 5 月 16 日 - 17 日

5 月 16 日、 **白猫プロジェクト** への出演が発表されました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://colopl.co.jp/shironekoproject/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://colopl.co.jp/shironekoproject/assets/ogp.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>白猫プロジェクト 公式サイト｜株式会社コロプラ【スマートフォンゲーム＆位置ゲー】</q></span><span class="embed-html-box_description"><q>誰でも片手で簡単プレイ！爽快アクションRPG！豪華声優陣が彩るストーリーも、スタミナ制限無しで楽しもう！</q></span></span></a></p></div>

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">明日フォースター19thの投票が始まります！(ฅ`･ω･´)っ<br>エントリー冒険家はこちらだにゃ(ฅ&#39;ω&#39;ฅ)<br>バーガーの存在感がすごいにゃ…<a href="https://twitter.com/hashtag/%E7%99%BD%E7%8C%AB?src=hash&amp;ref_src=twsrc%5Etfw">#白猫</a> <a href="https://t.co/2qjz0McJd6">pic.twitter.com/2qjz0McJd6</a></p>&mdash; 【公式】白猫プロジェクト NEW WORLD&#39;S (@wcat_project) <a href="https://twitter.com/wcat_project/status/732136487861391360?ref_src=twsrc%5Etfw">May 16, 2016</a></blockquote>

### 2017 年 2 月 14 日

アニメ『**恋愛暴君**』のキャストが発表され、メインヒロイン **グリ** 役を務めることが発表されました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://renaiboukun.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://renaiboukun.com/assets/images/ogimage2.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「恋愛暴君」公式サイト</q></span><span class="embed-html-box_description"><q>TVアニメ「恋愛暴君」2017年４月からテレビ東京・BSジャパン他にて放送開始！</q></span></span></a></p></div>

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【恋愛暴君　キャスト発表！】<br>続きまして、メインキャラクター5名のキャストのみなさんはこちら！<br>グリ： 青山吉能<br>藍野 青司：小野賢章<br>緋山 茜： 沼倉愛美<br>黄蝶ヶ崎 柚：長野佑紀<br>白峰 樒： 原 由実<br>コメントも到着！<a href="https://t.co/yxzekqni1j">https://t.co/yxzekqni1j</a><a href="https://twitter.com/hashtag/%E6%81%8B%E6%84%9B%E6%9A%B4%E5%90%9B?src=hash&amp;ref_src=twsrc%5Etfw">#恋愛暴君</a> <a href="https://t.co/B9pRHfjgEC">pic.twitter.com/B9pRHfjgEC</a></p>&mdash; アニメ｢恋愛暴君｣公式 (@boukun_PR) <a href="https://twitter.com/boukun_PR/status/831429568758099970?ref_src=twsrc%5Etfw">February 14, 2017</a></blockquote>

### 2017 年 4 月 6 日 - 6 月 くらい

『**恋愛暴君**』の放送時期です。多いですね。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://renaiboukun.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://renaiboukun.com/assets/images/ogimage2.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「恋愛暴君」公式サイト</q></span><span class="embed-html-box_description"><q>TVアニメ「恋愛暴君」2017年４月からテレビ東京・BSジャパン他にて放送開始！</q></span></span></a></p></div>

### 2017 年 7 月 - 9 月 くらい

なんですかねこれ……？

### 2017 年 9 月 5 日

特に多いこの日は TV アニメ『**異世界食堂**』 第 10 話 「menu 19 クレープ」が放送された日です。青山さんは、花の国の女王でフェアリーの **ティアナ・シルバリオ 16 世 （クレープ）** の声を務めています。この回は他の WUG メンバーも出ていますが、名前のついた役はティアナだけでしたね（他は魔術師・魔術師団長）。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://isekai-shokudo.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://isekai-shokudo.com/assets/img/og.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「異世界食堂」公式サイト</q></span><span class="embed-html-box_description"><q>ＴＶアニメ「異世界食堂」2017年夏、放送開始決定！</q></span></span></a></p></div>

### 2018 年 6 月 15 日

声優ユニット **Wake Up, Girls！ の解散** が発表された 2018 年 6 月 15 日にアクセス数が大きく増えています。青山さんは Wake Up, Girls！ のリーダーを務めました。

### 2019 年 3 月 8 日

吉岡さんがセンターを務めた 声優ユニット **Wake Up, Girls！ のファイナルライブ** が行われた日、アクセスが増えています。

### 2019 年 5 月 14 日

青山吉能の新番組（仮）（現: **青山吉能の可能性に挑戦！**）の初回放送日でした。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">初回特番は本日 5 月 14 日！<br><br>『青山吉能の新番組（仮）バースデーカウントダウンスペシャル』<a href="https://twitter.com/hashtag/%E9%9D%92%E5%B1%B1%E5%90%89%E8%83%BD?src=hash&amp;ref_src=twsrc%5Etfw">#青山吉能</a> <a href="https://twitter.com/hashtag/%E9%9D%92%E5%B1%B1%E5%90%89%E8%83%BD%E7%94%9F%E8%AA%95%E7%A5%AD?src=hash&amp;ref_src=twsrc%5Etfw">#青山吉能生誕祭</a><br><br>【ニコニコ公式】23:00 ～<a href="https://t.co/2nw2ja7gnq">https://t.co/2nw2ja7gnq</a><br>【チャンネル放送】23:30 ～<a href="https://t.co/jHQzbKzQk9">https://t.co/jHQzbKzQk9</a><br>【メール募集】<a href="https://t.co/0dBEBvXl5a">https://t.co/0dBEBvXl5a</a> <a href="https://t.co/v6u4SwNohi">pic.twitter.com/v6u4SwNohi</a></p>&mdash; 青山吉能の可能性に挑戦！ (@tryeverything23) <a href="https://twitter.com/tryeverything23/status/1128143942711533568?ref_src=twsrc%5Etfw">May 14, 2019</a></blockquote>

また、この日、青山さん本人の Twitter アカウントが開設されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">はじめまして🎂<br>声優の青山吉能です！🎂🎂<br>現在、生放送中です🎂🎂🎂<a href="https://twitter.com/hashtag/%E9%9D%92%E5%B1%B1%E5%90%89%E8%83%BD%E3%81%AE%E5%8F%AF%E8%83%BD%E6%80%A7%E3%81%AB%E6%8C%91%E6%88%A6?src=hash&amp;ref_src=twsrc%5Etfw">#青山吉能の可能性に挑戦</a><a href="https://twitter.com/hashtag/%E9%9D%92%E5%B1%B1%E5%90%89%E8%83%BD%E7%94%9F%E8%AA%95%E7%A5%AD?src=hash&amp;ref_src=twsrc%5Etfw">#青山吉能生誕祭</a></p>&mdash; 青山吉能 (@Yopipi555) <a href="https://twitter.com/Yopipi555/status/1128304941833998336?ref_src=twsrc%5Etfw">May 14, 2019</a></blockquote>

このちょっと前に偽アカウントが出てきてざわざわしてましたね……

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【ご報告】<br>Twitter上に弊社所属俳優・青山吉能を名乗るアカウントが存在しておりますが、2019年3月30日現在そのような公式アカウントは存在しておりません。<br>なりすましアカウントにご注意下さい。</p>&mdash; 【公式】81プロデュース (@81pro_official) <a href="https://twitter.com/81pro_official/status/1111831910194438145?ref_src=twsrc%5Etfw">March 30, 2019</a></blockquote>

### 2019 年 7 月 13 日

**白猫プロジェクト 5 周年記念スペシャル生放送！** が放送され、青山さんも出演されています。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">明日はいよいよ5周年生放送！<br>7/13（土）21:00から、YouTubeLiveとニコニコ生放送で行うにゃ (ฅ&#39;ω&#39;ฅ)<br>本日は、キャスト情報第2弾が到着！<br>青山吉能さん、黒澤剛史さん、手塚ヒロミチさんにもご出演いただきます☆<a href="https://t.co/Z6pibYrtUg">https://t.co/Z6pibYrtUg</a><a href="https://t.co/5kVt1DCCGI">https://t.co/5kVt1DCCGI</a><a href="https://twitter.com/hashtag/%E7%99%BD%E7%8C%AB?src=hash&amp;ref_src=twsrc%5Etfw">#白猫</a> <a href="https://twitter.com/hashtag/%E7%99%BD%E7%8C%AB5%E5%91%A8%E5%B9%B4?src=hash&amp;ref_src=twsrc%5Etfw">#白猫5周年</a> <a href="https://t.co/a3rdmlchl0">pic.twitter.com/a3rdmlchl0</a></p>&mdash; 【公式】白猫プロジェクト NEW WORLD&#39;S (@wcat_project) <a href="https://twitter.com/wcat_project/status/1149590823303929869?ref_src=twsrc%5Etfw">July 12, 2019</a></blockquote>

### 2019 年 11 月 18 日

熊本県製作のアニメ『**なつなぐ！**』に青山さんが出演されることが発表されました。スタッフ・キャストを熊本県出身者で固めた作品ということで、熊本出身の青山さんも出演されています。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">アニメ『なつなぐ！』千葉いずみ役を <a href="https://twitter.com/hashtag/%E9%9D%92%E5%B1%B1%E5%90%89%E8%83%BD?src=hash&amp;ref_src=twsrc%5Etfw">#青山吉能</a> が担当させていただく事が先程制作発表会にて発表されました！ 熊本地震の復興プロジェクトとしてスタッフ・メインキャストを熊本県出身で集結させたオール熊本アニメとなります！ 来年1月より放送予定です。お楽しみに！ <a href="https://twitter.com/hashtag/%E3%81%AA%E3%81%A4%E3%81%AA%E3%81%90?src=hash&amp;ref_src=twsrc%5Etfw">#なつなぐ</a> <a href="https://twitter.com/hashtag/%E3%82%AA%E3%83%BC%E3%83%AB%E7%86%8A%E6%9C%AC%E3%82%A2%E3%83%8B%E3%83%A1?src=hash&amp;ref_src=twsrc%5Etfw">#オール熊本アニメ</a> <a href="https://t.co/24XCvo7oYj">pic.twitter.com/24XCvo7oYj</a></p>&mdash; 【公式】81プロデュース (@81pro_official) <a href="https://twitter.com/81pro_official/status/1196272386250641409?ref_src=twsrc%5Etfw">November 18, 2019</a></blockquote>

### 2020 年 1 月 7 日

**なつなぐ！** 第 1 話の TOKYO MX での放送日です。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr"><a href="https://twitter.com/hashtag/%E3%81%AA%E3%81%A4%E3%81%AA%E3%81%90?src=hash&amp;ref_src=twsrc%5Etfw">#なつなぐ</a><br><br>第1話はTOKYO MXで今日の25:35～<br>だよー<br><br>見れなくてもGANMA！で見れるよー<br><br>仕事始めでねむねむな皆さんも、歯磨きしながら、明日の準備しながら、見てくれると嬉しい👀 <a href="https://t.co/UFGhzWxaux">pic.twitter.com/UFGhzWxaux</a></p>&mdash; noroanna (@noroanna) <a href="https://twitter.com/noroanna/status/1214176315756048384?ref_src=twsrc%5Etfw">January 6, 2020</a></blockquote>

また、この日は『**群れなせ！シートン学園**』第 1 話の放送日でもあります。青山さんは、グレビーシマウマのメス、**馬縞クロエ**役 で出演しています。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【🦓キャストコメント🐾】<br>馬縞クロエ役　<a href="https://twitter.com/hashtag/%E9%9D%92%E5%B1%B1%E5%90%89%E8%83%BD?src=hash&amp;ref_src=twsrc%5Etfw">#青山吉能</a> のコメントをお届け✍<a href="https://twitter.com/hashtag/%E3%82%B7%E3%83%BC%E3%83%88%E3%83%B3?src=hash&amp;ref_src=twsrc%5Etfw">#シートン</a> <a href="https://t.co/OaC27CmNqt">pic.twitter.com/OaC27CmNqt</a></p>&mdash; 「群れなせ！シートン学園」TVアニメ公式 (@anime_seton) <a href="https://twitter.com/anime_seton/status/1203600115631394816?ref_src=twsrc%5Etfw">December 8, 2019</a></blockquote>

### 2020 年 3 月 5 日

桁違いのアクセスがあります。何があったのでしょう。

この日、青山さんが体調不良のため当分の間休業することが発表されました。同時に複数コンテンツで降板が発表されたりしています。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【青山吉能についてのお知らせ】<br>弊社所属の青山吉能ですが、この度、しばらくの間休業および一部活動に制限を設けさせていただくことになりました。<br>詳しくは公式サイトにてご確認ください。 <a href="https://t.co/poB9SBR0NA">https://t.co/poB9SBR0NA</a></p>&mdash; 【公式】81プロデュース (@81pro_official) <a href="https://twitter.com/81pro_official/status/1235475905109037058?ref_src=twsrc%5Etfw">March 5, 2020</a></blockquote>

### 2020 年 4 月 4 日

この日、休業中の青山さんが徐々に復帰していくことが発表されました。思っていたより早くて良かったですね。健康が一番。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【お知らせ】<br>しばらくお休みさせていただいておりました青山吉能ですが、一人もしくは少人数の収録案件から徐々に現場復帰させていただいております。<br>尚、青山のSNSについてもこれから少しずつ運用を再開して参ります。<br>引き続きのご声援、何卒宜しくお願い致します！<br>先日の現場での写真もどーぞ♪ <a href="https://t.co/LfPLnbxLz0">pic.twitter.com/LfPLnbxLz0</a></p>&mdash; 【公式】81プロデュース (@81pro_official) <a href="https://twitter.com/81pro_official/status/1246369426728861696?ref_src=twsrc%5Etfw">April 4, 2020</a></blockquote>

### 2020 年 5 月 16 日

5 月 15 日がお誕生日でしたが、16 日は何があったのでしょうか？

合同会社 TOKYO6 ENTERTAINMENT の第一弾企画として『**小春六花**』が発表され、VOICEROID 制作を目指したクラウドファンディングを行うことが発表されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">TOKYO6 ENTERTAINMENTの1人目のキャラクター「小春六花（こはるりっか）」を発表致します。<br><br>まずは「VOICEROID」の制作に向けて5月28日よりクラウドファンディングを実施致します。<br>詳細はこちらに纏めていますので是非ご覧下さい：<a href="https://t.co/QHwotSiVoF">https://t.co/QHwotSiVoF</a><br><br>応援・RT頂けたら嬉しいです。<a href="https://twitter.com/hashtag/%E5%B0%8F%E6%98%A5%E5%85%AD%E8%8A%B1?src=hash&amp;ref_src=twsrc%5Etfw">#小春六花</a> <a href="https://t.co/KBhpmPlWQM">pic.twitter.com/KBhpmPlWQM</a></p>&mdash; TOKYO6 Information (@tokyo6info) <a href="https://twitter.com/tokyo6info/status/1261522155663065088?ref_src=twsrc%5Etfw">May 16, 2020</a></blockquote>

### 2020 年 8 月 29 日

この日、NHK E テレにて、青山さんが出演された『**映画 きかんしゃトーマス Ｇｏ！Ｇｏ！地球まるごとアドベンチャー**』が放送されました。DA PUMP の ISSA さんとかも出ててざわざわしてた。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">NHK Eテレ 08/29 15:35 映画　きかんしゃトーマス　Ｇｏ！Ｇｏ！地球まるごとアドベンチャー <a href="https://twitter.com/hashtag/nhketv?src=hash&amp;ref_src=twsrc%5Etfw">#nhketv</a> <a href="https://twitter.com/hashtag/%E3%81%8D%E3%81%8B%E3%82%93%E3%81%97%E3%82%83%E3%83%88%E3%83%BC%E3%83%9E%E3%82%B9%E3%81%A8%E3%81%AA%E3%81%8B%E3%81%BE%E3%81%9F%E3%81%A1?src=hash&amp;ref_src=twsrc%5Etfw">#きかんしゃトーマスとなかまたち</a> <a href="https://t.co/mPgsimwaxD">https://t.co/mPgsimwaxD</a></p>&mdash; NHK Eテレ(教育テレビ) (@NHK_ETV) <a href="https://twitter.com/NHK_ETV/status/1299595644399624192?ref_src=twsrc%5Etfw">August 29, 2020</a></blockquote>

### 2021 年 5 月 15 日

この日 25 歳の誕生日を迎えた青山さん。バースデーオンラインイベント『**25 才のこと、アラサーって言ったやつ全員ふっ飛ばすの会**』が開催されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">さあ、本日5月15日は青山吉能さんバースデーオンラインイベント『25才のこと、アラサーって言ったやつ全員ふっ飛ばすの会』開催です👊<br><br>２部には広川恵一さんもゲスト出演してくださいます！<br><br>１部 17:00〜 → <a href="https://t.co/dlsgpkwehU">https://t.co/dlsgpkwehU</a><br>２部 20:30〜 → <a href="https://t.co/kH9nTwecF9">https://t.co/kH9nTwecF9</a><a href="https://twitter.com/hashtag/%E3%82%88%E3%81%B4%E3%81%A1%E3%82%83%E3%82%8C?src=hash&amp;ref_src=twsrc%5Etfw">#よぴちゃれ</a> <a href="https://t.co/WbLl3SiBV9">pic.twitter.com/WbLl3SiBV9</a></p>&mdash; 青山吉能の可能性に挑戦！ (@tryeverything23) <a href="https://twitter.com/tryeverything23/status/1393346261378498562?ref_src=twsrc%5Etfw">May 14, 2021</a></blockquote>

## 山下七海さん

<figure>
  <center>
    <a href="https://i.imgur.com/jlBicWl.png"><img src="https://i.imgur.com/jlBicWl.png"></a>
    <figcaption>Wikipedia: 山下七海 のアクセス数</figcaption>
  </center>
</figure>

### 2015 年 10 月 11 日

ノーコメントでいいですか？ だめな人は Twitter で聴いてください。

### 2016 年 1 月 12 日

ノーコメントでいいですか？ だめな人は Twitter で聴いてください。

### 2016 年 3 月 10 日

**この素晴らしい世界に祝福を！**（ 1 期）第 9 話 の放送日です。山下さんは **新人サキュバス**役 で出演されました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="http://konosuba.com/1st/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(http://konosuba.com/img/ogp.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>アニメ「この素晴らしい世界に祝福を！」公式サイト</q></span><span class="embed-html-box_description"><q>アニメ「この素晴らしい世界に祝福を！」公式サイト</q></span></span></a></p></div>

### 2016 年 3 月 22 日

**おそ松さん**（ 1 期）第 24 話の放送日です。山下さんは **橋本にゃー**役 で出演されました。この後 2 期, 3 期にも出演されます。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://osomatsusan.com/1st/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://osomatsusan.com/1st/ogp.jpg?d=170406);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「おそ松さん」公式サイト</q></span><span class="embed-html-box_description"><q>赤塚不二夫生誕80周年記念作品、TVアニメ「おそ松さん」公式サイト。2期放送決定！あの6つ子たちが帰ってくる！いよいよ支度開始！監督：藤田陽一、キャラクターデザイン：浅野直之、シリーズ構成：松原 秀、アニメーション制作：studioぴえろ、キャスト：櫻井孝宏、中村悠一、神谷浩史、福山 潤、小野大輔、入野自由、遠藤 綾、鈴村健一、國立 幸、上田燿司、飛田展男、斎藤桃子ほか</q></span></span></a></p></div>

### 2016 年 4 月 28 日

この日 文化放送 超！Ａ＆Ｇ＋で放送された『**アニゲラ！ディドゥーーン！！！**』のゲストに山下さんがゲスト出演されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">アニゲラ！ディドゥーーン！！！　お聴きいただきありがとうございました。新コーナーへの投稿よろしくお願いします！　そして、来週のゲストはアニメ『影鰐』の高嶋友也監督と『ハッカドール』3号役の山下七海さんです。お楽しみに！ <a href="https://twitter.com/hashtag/anigera?src=hash&amp;ref_src=twsrc%5Etfw">#anigera</a></p>&mdash; アニゲラ！ディドゥーーン！！！ (@anigera_staff) <a href="https://twitter.com/anigera_staff/status/723128541777256452?ref_src=twsrc%5Etfw">April 21, 2016</a></blockquote>

### 2016 年 10 月 15 日

この日、**[THE IDOLM@STER CINDERELLA GIRLS 4thLIVE TriCastle Story](https://idolmaster.jp/event/cinderella4th.php){:target="\_blank" rel="noopener"} さいたまスーパーアリーナ公演: DAY1 Brand new Castle** が開催され、山下七海さんは **大槻唯**役 で出演されました。大槻唯がライブに初登場ということで話題になってました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://togetter.com/li/1037292" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://pimg.togetter.com/74cae91cfd5b7b4e17aeb46736d7552733940867/687474703a2f2f696d6775722e636f6d2f7a7a446f7632572e6a7067?w=1200&h=630&t=c);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>2016年10月15日 大槻唯ちゃん、デレマスライブへようこそ!! THE IDOLM@STER CINDERELLA GIRLS 4thLIVE TriCastle Story Brand new Castle inさいたまスーパーアリーナ 山下七海（大槻唯役）関連まとめ</q></span><span class="embed-html-box_description"><q>デレマスライブに大槻唯ちゃんが初登場。「ゆい、たくさん頑張ったよ！だからプロデューサーちゃん！あまーいのいっぱいちょうだい♥」あと腋。</q></span></span></a></p></div>

その日の山下さんのブログを貼っておきますね。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://ameblo.jp/wakeupgirls/entry-12211958561.html" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://stat.ameba.jp/user_images/20161021/22/wakeupgirls/75/2a/j/o0480064013778658295.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wake Up, Girls！『ナナナナナ？Nanaminn』</q></span><span class="embed-html-box_description"><q>みなさま平日おつかれ様でしたっ山下七海です!この間、１日中WUGのロケがありました〜っ何をしたかはまだ秘密ですが、久しぶりにあの場所へ☆その時のロケでは、夜ぶ…</q></span></span></a></p></div>

### 2017 年 7 月 8 日, 9 日

この日、**[THE IDOLM@STER CINDERELLA GIRLS 5thLIVE TOUR Serendipity Parade!!!](https://idolmaster.jp/event/cinderella5th.php){:target="\_blank" rel="noopener"} 幕張公演 （2DAYS）** が開催され、山下七海さんは **大槻唯**役 で出演されました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://ameblo.jp/wakeupgirls/entry-12292655362.html" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://stat.ameba.jp/user_images/20170714/21/wakeupgirls/b6/7b/j/o0480064113982442182.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wake Up, Girls！『成長★Ｎanaminn』</q></span><span class="embed-html-box_description"><q>みなさま、平日おつかれ様でしたっ山下七海です◎♪最近、姪っ子が初めてひとり立ちした瞬間の動画を見せてもらいました。。(๑°⌓°๑)よろよろと何度コケても諦めず…</q></span></span></a></p></div>

<small>これ見てましたが、山下さんが私の夏はまだまだこれから！みたいなこと言ってたの WUG ツアー行かなきゃなあになりました。</small>

### 2018 年 6 月 6 日

TV アニメ『**二度目の人生を異世界で**』に**創造主**役で出演することが発表されていましたが、この日、81 プロデュースより降板の決定が発表されました。メインキャラクター 4 人の声優が同時に降板を発表、アニメ化の中止が発表されるなど、悲しい事件だったね……

### 2018 年 6 月 15 日

山下さんが所属していた 声優ユニット **Wake Up, Girls！ の解散** が発表された 2018 年 6 月 15 日にアクセス数が大きく増えています。

### 2019 年 3 月 8 日

声優ユニット **Wake Up, Girls！ のファイナルライブ** が行われた日、アクセスが増えています。

### 2019 年 5 月 13 日

山下七海さんととエイベックスの偽 Twitter アカウントが生えてきてザワザワした日です。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">この垢、偽物だから気を付けてな。山下七海さんも関係ないから騙されないように <a href="https://t.co/s7908d0LVQ">pic.twitter.com/s7908d0LVQ</a></p>&mdash; あんでぃくんさん (@aPnKdMyN) <a href="https://twitter.com/aPnKdMyN/status/1127932690244591620?ref_src=twsrc%5Etfw">May 13, 2019</a></blockquote>

### 2019 年 6 月 22 日

フジテレビ系列で放送された『**超逆境クイズバトル！！99 人の壁**』に壁役で出演しました。回答権獲得して見せ場があったので良かったですね。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.fujitv.co.jp/99wall/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://www.fujitv.co.jp/99wall/img/ogp.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>99人の壁 - フジテレビ</q></span><span class="embed-html-box_description"><q>99人の壁 - オフィシャルサイト。レギュラー化決定!1人vs99人の超逆境早押しクイズバトル！自分の得意なジャンルのクイズで賞金100万円を?み取れ！</q></span></span></a></p></div>

<blockquote class="instagram-media" data-instgrm-captioned data-instgrm-permalink="https://www.instagram.com/p/BzAwgfKl2uT/?utm_source=ig_embed&amp;utm_campaign=loading" data-instgrm-version="14" style=" background:#FFF; border:0; border-radius:3px; box-shadow:0 0 1px 0 rgba(0,0,0,0.5),0 1px 10px 0 rgba(0,0,0,0.15); margin: 1px; max-width:540px; min-width:326px; padding:0; width:99.375%; width:-webkit-calc(100% - 2px); width:calc(100% - 2px);"><div style="padding:16px;"> <a href="https://www.instagram.com/p/BzAwgfKl2uT/?utm_source=ig_embed&amp;utm_campaign=loading" style=" background:#FFFFFF; line-height:0; padding:0 0; text-align:center; text-decoration:none; width:100%;" target="_blank"> <div style=" display: flex; flex-direction: row; align-items: center;"> <div style="background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 40px; margin-right: 14px; width: 40px;"></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 100px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 60px;"></div></div></div><div style="padding: 19% 0;"></div> <div style="display:block; height:50px; margin:0 auto 12px; width:50px;"><svg width="50px" height="50px" viewBox="0 0 60 60" version="1.1" xmlns="https://www.w3.org/2000/svg" xmlns:xlink="https://www.w3.org/1999/xlink"><g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd"><g transform="translate(-511.000000, -20.000000)" fill="#000000"><g><path d="M556.869,30.41 C554.814,30.41 553.148,32.076 553.148,34.131 C553.148,36.186 554.814,37.852 556.869,37.852 C558.924,37.852 560.59,36.186 560.59,34.131 C560.59,32.076 558.924,30.41 556.869,30.41 M541,60.657 C535.114,60.657 530.342,55.887 530.342,50 C530.342,44.114 535.114,39.342 541,39.342 C546.887,39.342 551.658,44.114 551.658,50 C551.658,55.887 546.887,60.657 541,60.657 M541,33.886 C532.1,33.886 524.886,41.1 524.886,50 C524.886,58.899 532.1,66.113 541,66.113 C549.9,66.113 557.115,58.899 557.115,50 C557.115,41.1 549.9,33.886 541,33.886 M565.378,62.101 C565.244,65.022 564.756,66.606 564.346,67.663 C563.803,69.06 563.154,70.057 562.106,71.106 C561.058,72.155 560.06,72.803 558.662,73.347 C557.607,73.757 556.021,74.244 553.102,74.378 C549.944,74.521 548.997,74.552 541,74.552 C533.003,74.552 532.056,74.521 528.898,74.378 C525.979,74.244 524.393,73.757 523.338,73.347 C521.94,72.803 520.942,72.155 519.894,71.106 C518.846,70.057 518.197,69.06 517.654,67.663 C517.244,66.606 516.755,65.022 516.623,62.101 C516.479,58.943 516.448,57.996 516.448,50 C516.448,42.003 516.479,41.056 516.623,37.899 C516.755,34.978 517.244,33.391 517.654,32.338 C518.197,30.938 518.846,29.942 519.894,28.894 C520.942,27.846 521.94,27.196 523.338,26.654 C524.393,26.244 525.979,25.756 528.898,25.623 C532.057,25.479 533.004,25.448 541,25.448 C548.997,25.448 549.943,25.479 553.102,25.623 C556.021,25.756 557.607,26.244 558.662,26.654 C560.06,27.196 561.058,27.846 562.106,28.894 C563.154,29.942 563.803,30.938 564.346,32.338 C564.756,33.391 565.244,34.978 565.378,37.899 C565.522,41.056 565.552,42.003 565.552,50 C565.552,57.996 565.522,58.943 565.378,62.101 M570.82,37.631 C570.674,34.438 570.167,32.258 569.425,30.349 C568.659,28.377 567.633,26.702 565.965,25.035 C564.297,23.368 562.623,22.342 560.652,21.575 C558.743,20.834 556.562,20.326 553.369,20.18 C550.169,20.033 549.148,20 541,20 C532.853,20 531.831,20.033 528.631,20.18 C525.438,20.326 523.257,20.834 521.349,21.575 C519.376,22.342 517.703,23.368 516.035,25.035 C514.368,26.702 513.342,28.377 512.574,30.349 C511.834,32.258 511.326,34.438 511.181,37.631 C511.035,40.831 511,41.851 511,50 C511,58.147 511.035,59.17 511.181,62.369 C511.326,65.562 511.834,67.743 512.574,69.651 C513.342,71.625 514.368,73.296 516.035,74.965 C517.703,76.634 519.376,77.658 521.349,78.425 C523.257,79.167 525.438,79.673 528.631,79.82 C531.831,79.965 532.853,80.001 541,80.001 C549.148,80.001 550.169,79.965 553.369,79.82 C556.562,79.673 558.743,79.167 560.652,78.425 C562.623,77.658 564.297,76.634 565.965,74.965 C567.633,73.296 568.659,71.625 569.425,69.651 C570.167,67.743 570.674,65.562 570.82,62.369 C570.966,59.17 571,58.147 571,50 C571,41.851 570.966,40.831 570.82,37.631"></path></g></g></g></svg></div><div style="padding-top: 8px;"> <div style=" color:#3897f0; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:550; line-height:18px;">この投稿をInstagramで見る</div></div><div style="padding: 12.5% 0;"></div> <div style="display: flex; flex-direction: row; margin-bottom: 14px; align-items: center;"><div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(0px) translateY(7px);"></div> <div style="background-color: #F4F4F4; height: 12.5px; transform: rotate(-45deg) translateX(3px) translateY(1px); width: 12.5px; flex-grow: 0; margin-right: 14px; margin-left: 2px;"></div> <div style="background-color: #F4F4F4; border-radius: 50%; height: 12.5px; width: 12.5px; transform: translateX(9px) translateY(-18px);"></div></div><div style="margin-left: 8px;"> <div style=" background-color: #F4F4F4; border-radius: 50%; flex-grow: 0; height: 20px; width: 20px;"></div> <div style=" width: 0; height: 0; border-top: 2px solid transparent; border-left: 6px solid #f4f4f4; border-bottom: 2px solid transparent; transform: translateX(16px) translateY(-4px) rotate(30deg)"></div></div><div style="margin-left: auto;"> <div style=" width: 0px; border-top: 8px solid #F4F4F4; border-right: 8px solid transparent; transform: translateY(16px);"></div> <div style=" background-color: #F4F4F4; flex-grow: 0; height: 12px; width: 16px; transform: translateY(-4px);"></div> <div style=" width: 0; height: 0; border-top: 8px solid #F4F4F4; border-left: 8px solid transparent; transform: translateY(-4px) translateX(8px);"></div></div></div> <div style="display: flex; flex-direction: column; flex-grow: 1; justify-content: center; margin-bottom: 24px;"> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; margin-bottom: 6px; width: 224px;"></div> <div style=" background-color: #F4F4F4; border-radius: 4px; flex-grow: 0; height: 14px; width: 144px;"></div></div></a><p style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; line-height:17px; margin-bottom:0; margin-top:8px; overflow:hidden; padding:8px 0 7px; text-align:center; text-overflow:ellipsis; white-space:nowrap;"><a href="https://www.instagram.com/p/BzAwgfKl2uT/?utm_source=ig_embed&amp;utm_campaign=loading" style=" color:#c9c8cd; font-family:Arial,sans-serif; font-size:14px; font-style:normal; font-weight:normal; line-height:17px; text-decoration:none;" target="_blank">山下七海(@aishite773)がシェアした投稿</a></p></div></blockquote> <script async src="//www.instagram.com/embed.js"></script>

### 2020 年 3 月 10 日

この日、TV アニメ『**キラッとプリ ☆ チャン**』シーズン 3 に登場するマスコットのキャストが発表され、山下さんは**キラッ CHU**役を務めることが発表されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">4月スタート『キラッとプリ☆チャン』シーズン３から新情報が到着♪<br>3人のマスコットのキャストが解禁になりました！<br>「キラッCHU」役・山下七海さん、「メルパン」役・大森日雅さん、「ラビリィ」役・田中美海さんです！<br>4月からのオンエアーをお楽しみに♡<a href="https://twitter.com/hashtag/prichan?src=hash&amp;ref_src=twsrc%5Etfw">#prichan</a> <a href="https://t.co/wdsxvSmqN8">pic.twitter.com/wdsxvSmqN8</a></p>&mdash; アニメ『ワッチャプリマジ！』公式 (@PrettySeriesPR) <a href="https://twitter.com/PrettySeriesPR/status/1237181376790769665?ref_src=twsrc%5Etfw">March 10, 2020</a></blockquote>

### 2020 年 9 月 5 日

9 月 5 日から 6 日にかけて **THE IDOLM@STER CINDERELLA GIRLS LIVE Broadcast 24magic** が放送され、山下七海さんは 1 日目のオープニング〜出演されました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://idolmaster-official.jp/live_event/cg24magic/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://idolmaster-official.jp/live_event/cg24magic/ogp.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>THE IDOLM@STER CINDERELLA GIRLS LIVE Broadcast 24magic │ THE IDOLM@STER OFFICIAL WEB | バンダイナムコエンターテインメント公式サイト</q></span><span class="embed-html-box_description"><q>シンデレラガールズLIVE Broadcast 24magicの情報はこちらから！</q></span></span></a></p></div>

あとどれだけ影響したかわかりませんが、イヤモニブランド AAW と山下七海さんのコラボイヤホンの発売が発表されたのもこの日でした。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【本日予約開始】山下七海さんとのコラボイヤホン『AXH 773 Edition』がe☆イヤホン限定で登場！<br><br>山下七海さんのためのオリジナルチューニングが施されているスペシャルなイヤホンです！【<a href="https://twitter.com/hashtag/AAW?src=hash&amp;ref_src=twsrc%5Etfw">#AAW</a>】<a href="https://t.co/iFYBt6IbCC">https://t.co/iFYBt6IbCC</a> <a href="https://t.co/KenUVkMM5v">pic.twitter.com/KenUVkMM5v</a></p>&mdash; イヤホン・ヘッドホン専門店「e☆イヤホン」 (@e_earphone) <a href="https://twitter.com/e_earphone/status/1302069039884247040?ref_src=twsrc%5Etfw">September 5, 2020</a></blockquote>

> 本モデルの開発にあたっては、AAW の創設者であり音響エンジニアである Kevin Wang 氏が山下七海さんの楽曲を聴き込み、本モデルのためのオリジナルチューニングを施しました！

これ好き。推しと音響ブランドのコラボを実現すると音響エンジニアに推しの曲を聴きこませることができるんですね。

### 2021 年 8 月 25 日

これが本当に理由かわからないのですが、**NonSugar** 初のアルバム『**Tasting NonSugar**』の発売日です。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">NonSugarの初アルバム「Tasting NonSugar」はいよいよ明日発売❣<br><br>のん役 <a href="https://twitter.com/hashtag/%E7%94%B0%E4%B8%AD%E7%BE%8E%E6%B5%B7?src=hash&amp;ref_src=twsrc%5Etfw">#田中美海</a> さん、ちり役 <a href="https://twitter.com/hashtag/%E5%A4%A7%E6%A3%AE%E6%97%A5%E9%9B%85?src=hash&amp;ref_src=twsrc%5Etfw">#大森日雅</a> さん、ペッパー役 <a href="https://twitter.com/hashtag/%E5%B1%B1%E4%B8%8B%E4%B8%83%E6%B5%B7?src=hash&amp;ref_src=twsrc%5Etfw">#山下七海</a> さんからのコメント動画が到着しました✨<br><br>CDの商品情報はこちら💛<a href="https://t.co/i1R6N9DlJ9">https://t.co/i1R6N9DlJ9</a><a href="https://twitter.com/hashtag/pripara?src=hash&amp;ref_src=twsrc%5Etfw">#pripara</a> <a href="https://t.co/4XIcF6JCyA">pic.twitter.com/4XIcF6JCyA</a></p>&mdash; アニメ『ワッチャプリマジ！』公式 (@PrettySeriesPR) <a href="https://twitter.com/PrettySeriesPR/status/1430092515626135562?ref_src=twsrc%5Etfw">August 24, 2021</a></blockquote>

また、『**超!A&G ＋マンスリースペシャル 山下七海のななつやすみ**』最終回の放送日でした。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【山下七海の ななつやすみ】<br>今回引かれたオラクルカードはこちらです。<br>自分へのご褒美、参考になりましたか？<br><br>ななつやすみは今回が最終回。<br>８月を一緒に楽しんでくれたみなさん、ありがとうございました！<a href="https://twitter.com/hashtag/%E3%81%AA%E3%81%AA%E3%81%A4%E3%82%84%E3%81%99%E3%81%BF?src=hash&amp;ref_src=twsrc%5Etfw">#ななつやすみ</a><a href="https://twitter.com/hashtag/agqr?src=hash&amp;ref_src=twsrc%5Etfw">#agqr</a> <a href="https://t.co/jtSsjHbHqd">pic.twitter.com/jtSsjHbHqd</a></p>&mdash; 稗田寧々の地に&quot;ね&quot;を張って生きたい【超！A＆G＋マンスリースペシャル 】 (@msp_agqr) <a href="https://twitter.com/msp_agqr/status/1430537953755815937?ref_src=twsrc%5Etfw">August 25, 2021</a></blockquote>

### 2021 年 9 月 23 日

この日、**『鬼滅の刃』柱合会議・蝶屋敷編** が放送され、山下さんは **寺内きよ**役で出演していました。遊郭編にも出てるらしいですね。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://kimetsu.com/anime/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://kimetsu.com/anime/ogp.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>アニメ「鬼滅の刃」公式ポータルサイト</q></span><span class="embed-html-box_description"><q>アニメ「鬼滅の刃」公式ポータルサイト。テレビアニメ「無限列車編」放送中。</q></span></span></a></p></div>

## 奥野香耶さん

<figure>
  <center>
    <a href="https://i.imgur.com/cTggSGc.png"><img src="https://i.imgur.com/cTggSGc.png"></a>
    <figcaption>Wikipedia: 奥野香耶 のアクセス数</figcaption>
  </center>
</figure>

### 2015 年 12 月 2 日

TV アニメ『**俺がお嬢様学校に「庶民サンプル」としてゲッツ ♥ された件**』 9 話の放送日で、奥野さんは **メイド**役で出演されていました。

### 2016 年 4 月 5 日

TV アニメ『**ハンドレッド**』第 1 話 の放送日です。奥野さんはヒロインの 1 人で主人公の妹の **如月カレン**役で出演されています。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://hundred-anime.jp/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://hundred-anime.jp/assets/img/ogimage_160306.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「ハンドレッド」公式サイト</q></span><span class="embed-html-box_description"><q>アニメ「ハンドレッド」テレビ東京ほかにて絶賛放映中！</q></span></span></a></p></div>

### 2018 年 6 月 15 日

奥野さんが所属していた 声優ユニット **Wake Up, Girls！ の解散** が発表された 2018 年 6 月 15 日にアクセス数が大きく増えています。

### 2019 年 3 月 8 日

声優ユニット **Wake Up, Girls！ のファイナルライブ** が行われた日、アクセスが増えています。

### 2019 年 4 月 30 日

この日、ファミ通チャンネル（ニコニコ生放送、YouTube Live）にて **奥野香耶さん SNS 開設記念特番！** が放送され、奥野さんの Twitter、Instagram アカウントが開設されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">かやたんがTwitterとインスタグラムを始める！　気になる内容は生放送で！<br><br>【ニコ生配信中】奥野香耶さんSNS開設記念特番！ かやたんがファミ通チャンネルに再びやってくる！ <a href="https://t.co/YOIW2w1dAI">https://t.co/YOIW2w1dAI</a> <a href="https://t.co/VCgWGKUWrh">pic.twitter.com/VCgWGKUWrh</a></p>&mdash; ファミ通.com (@famitsu) <a href="https://twitter.com/famitsu/status/1123183374540001282?ref_src=twsrc%5Etfw">April 30, 2019</a></blockquote>

ちなみに初投稿はこちら。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">さてと。</p>&mdash; 奥野香耶 (@kaayaataaaan) <a href="https://twitter.com/kaayaataaaan/status/1123185765301739521?ref_src=twsrc%5Etfw">April 30, 2019</a></blockquote>

SNS 開設特番って何？

### 2019 年 5 月 15 日

これ何の日なんだ…？ Twitter アカウント作った青山吉能さんに絡みに行って個性的な受け答えをしたらリプ欄で WUG 同窓会が始まったやつしか心当たりがない。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">笑<br>またね〜😊</p>&mdash; 奥野香耶 (@kaayaataaaan) <a href="https://twitter.com/kaayaataaaan/status/1128547539949539328?ref_src=twsrc%5Etfw">May 15, 2019</a></blockquote>

これ好きすぎ

わかりました。

ニュースアプリ『**ハッカドール**』のサービス終了が発表されていました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【大切なお知らせ】<br>君にシンクロするニュースアプリ「ハッカドール」は、2019年8月15日(木)にサービスを終了することになりましたっ！<br>ふええん、わたしたち無職ってことですかっ！？<br>詳しくはこちらっ！<a href="https://t.co/hAct5AFANV">https://t.co/hAct5AFANV</a> <a href="https://t.co/8n9sZbG0XO">pic.twitter.com/8n9sZbG0XO</a></p>&mdash; ハッカドール☘8/15サ終 (@Hackadoll) <a href="https://twitter.com/Hackadoll/status/1128495471972929536?ref_src=twsrc%5Etfw">May 15, 2019</a></blockquote>

### 2019 年 8 月 15 日

ニュースアプリ『**ハッカドール**』がこの日サービス終了を迎えました。奥野さんは **ハッカドール 2 号**役を務めていました。この日は **ハッカドール THE あにめ～しょん 全話一挙放送**なども行われました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">君にシンクロするニュースアプリ「ハッカドール」<br>５年間応援してくれてありがとうございましたっ！<br>以上、ハッカドールでしたっ！ <a href="https://t.co/BmWqpKAwmp">pic.twitter.com/BmWqpKAwmp</a></p>&mdash; ハッカドール☘8/15サ終 (@Hackadoll) <a href="https://twitter.com/Hackadoll/status/1161949741854314496?ref_src=twsrc%5Etfw">August 15, 2019</a></blockquote>

### 2019 年 12 月 2 日

『**鷲崎健のヨルナイト × ヨルナイト 月曜日**』の 12 月マンスリーアシスタントを奥野さんが担当されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【鷲崎健のヨルナイト×ヨルナイト 月曜日】<br>１２月は奥野香耶さんがアシスタントを担当！<br>みなさんからは『ふつおた』『２人にやって欲しいこと』を大募集！！<br>yonayona@joqr.netまでドンドン送ってきてくださいね！<a href="https://twitter.com/hashtag/%E3%83%A8%E3%83%AB%E3%83%8A%E3%82%A4%E3%83%88?src=hash&amp;ref_src=twsrc%5Etfw">#ヨルナイト</a> <a href="https://twitter.com/hashtag/agqr?src=hash&amp;ref_src=twsrc%5Etfw">#agqr</a></p>&mdash; 鷲崎健のヨルナイト×ヨルナイト (@yonayona_ag) <a href="https://twitter.com/yonayona_ag/status/1201492884194594817?ref_src=twsrc%5Etfw">December 2, 2019</a></blockquote>

### 2020 年 2 月 9 日

TV アニメ『**異種族レビュアーズ**』第 5 話 の放送日で、奥野さんは マイコニドの森のサキュバス嬢 **ホーシィ**役を務めました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【新キャラクター発表】<br><br>第5話に登場したマイコニドの森のサキュバス嬢！<br><br>ホーシィを担当するのは、奥野香耶さんです！<a href="https://twitter.com/hashtag/isyuzoku?src=hash&amp;ref_src=twsrc%5Etfw">#isyuzoku</a> <a href="https://t.co/mvne7LfvxV">pic.twitter.com/mvne7LfvxV</a></p>&mdash; ＴＶアニメ「異種族レビュアーズ」公式 (@isyuzoku) <a href="https://twitter.com/isyuzoku/status/1226189446913155073?ref_src=twsrc%5Etfw">February 8, 2020</a></blockquote>

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://isyuzoku.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_metano-image"><span class="embed-html-box_title"><q>TVアニメ「異種族レビュアーズ」公式サイト</q></span><span class="embed-html-box_description"><q>色んな意味で超危険な最先端ファンタスティックコメディ「異種族レビュアーズ」が2020年1月TVアニメ放送開始！多種多様な種族が暮らす世界を舞台に、異種族娘たちが営むムフフなお店に通い、そのサービスの全てを余すことなくクロスレビュー！</q></span></span></a></p></div>

### 2021 年 3 月 12 日

この日、 BS11 で放送された『**アニゲー ☆ イレブン！**』に奥野さんがゲスト出演しました。ヤバキャラエピソードを披露してざわついてましたね。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【本日のOAメモ⑦】<br>今夜10:30～はアニゲー☆イレブン！<br><br>ゲストは <a href="https://twitter.com/hashtag/%E5%A5%A5%E9%87%8E%E9%A6%99%E8%80%B6?src=hash&amp;ref_src=twsrc%5Etfw">#奥野香耶</a> さん🌟<br><br>▼オンラインイベント「国際マンガ・アニメ祭 Reiwa Toshima 2021」に潜入！<br>▼3/17(水)放送のスペシャル番組「Hello！ガンプラワールド」の情報も！<a href="https://twitter.com/hashtag/IMART2021?src=hash&amp;ref_src=twsrc%5Etfw">#IMART2021</a> <a href="https://twitter.com/hashtag/%E3%82%AC%E3%83%B3%E3%83%80%E3%83%A0?src=hash&amp;ref_src=twsrc%5Etfw">#ガンダム</a> <a href="https://twitter.com/hashtag/%E3%82%AC%E3%83%B3%E3%83%97%E3%83%A9?src=hash&amp;ref_src=twsrc%5Etfw">#ガンプラ</a> <a href="https://twitter.com/hashtag/%E5%92%8C%E6%B0%A3%E3%81%82%E3%81%9A%E6%9C%AA?src=hash&amp;ref_src=twsrc%5Etfw">#和氣あず未</a> <a href="https://twitter.com/hashtag/anige_11?src=hash&amp;ref_src=twsrc%5Etfw">#anige_11</a> <a href="https://twitter.com/hashtag/bs11?src=hash&amp;ref_src=twsrc%5Etfw">#bs11</a> <a href="https://t.co/WYe30Jjcb9">pic.twitter.com/WYe30Jjcb9</a></p>&mdash; BS11 アニメ全国無料放送テレビ局【公式】 (@BS11_Anime) <a href="https://twitter.com/BS11_Anime/status/1370285437676257283?ref_src=twsrc%5Etfw">March 12, 2021</a></blockquote>

## 高木美佑さん

<figure>
  <center>
    <a href="https://i.imgur.com/kBufXVr.png"><img src="https://i.imgur.com/kBufXVr.png"></a>
    <figcaption>Wikipedia: 高木美佑 のアクセス数</figcaption>
  </center>
</figure>

### 2015 年 10 月 2, 3 日, 5 日 〜 12 月

2 日に TV アニメ『**ハッカドール THE あにめ〜しょん**』第 1 話が放送され、高木さんは **ハッカドール 1 号**役で出演しています。 5 日は BS11 での放送日、ニコニコでの配信日です。この感じで 12 月までアクセスが多めです。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://hackadoll-anime.com/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://hackadoll-anime.com/assets/img/hacka_ogp.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「ハッカドール THE あにめ～しょん」公式サイト</q></span><span class="embed-html-box_description"><q>「ハッカドール THE あにめ～しょん」TOKYO/MX、BS11にて放送開始！</q></span></span></a></p></div>

### 2016 年 9 月 3 日

なんですかねこれ……

**英美里・美佑のブラエミリ　ヴァナ・ディール編** …？

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.famitsu.com/news/201608/31114548.html" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://www.famitsu.com/images/000/114/548/l_57c6a400390dd.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>【ファミ通ニコ生】声優の加藤英美里さんが『FF11』のヴァナ・ディールに帰還!?　2016年9月3日（土）19時より特別番組が配信決定!! - ファミ通.com</q></span><span class="embed-html-box_description"><q>2016年9月3日（土）19時より、ファミ通のニコニコ公式生放送にて、『『FF11』英美里・美佑のブラエミリ　ヴァナ・ディール編』を配信。声優の加藤英美里さん、高木美佑さんが『ファイナルファンタジーXI』の舞台であるヴァナ・ディールをお散歩します。
</q></span></span></a></p></div>

### 2016 年 11 月 6 日

なんですかねこれ……

**高木美佑・加藤英美里がゲームをし続ける生放送** …？

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.famitsu.com/news/201611/05119943.html" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-30x25.svg" style="background-image: url(https://www.famitsu.com/images/000/119/943/l_581def92adb40.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>ひたすらゲームをしたりたこ焼きパーティーをしたり！ “高木美佑・加藤英美里がゲームをし続ける生放送”をチェック！ - ファミ通.com</q></span><span class="embed-html-box_description"><q>声優の高木美佑さん、加藤英美里さん、永野愛理さんがゲームをし続ける生放送を配信！</q></span></span></a></p></div>

### 2016 年 12 月 11 日

この日、 『**アニメ JAM 2016**』 が開催され、 Wake Up, Girls！ がゲスト出演しました。また、『**Wake Up, Girls！ Festa. 2016 SUPER LIVE**』が開催され、アニメ新章の制作が発表されました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://anime-jam.com/2016/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(http://anime-jam.com/2016/common/images/og.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>アニメJAM 2016 オフィシャルサイト</q></span><span class="embed-html-box_description"><q>TOPページです。「アニメJAM2016」テレビ東京で放送されている注目アニメ作品のライブ＆豪華キャストによるトークショー等！2016年12月10日(土)&11日(日)幕張メッセで開催！</q></span></span></a></p></div>
<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://wug-portal.jp/event/detail.php?id=1000934" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://wug-portal.jp/assets/img/ogp_180615.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wake Up, Girls！Festa. 2016 SUPER LIVE｜WUGポータル</q></span><span class="embed-html-box_description"><q>TVアニメ「Wake Up, Girls！」シリーズ及び声優ユニット「Wake Up, Girls！」の総合情報サイト！</q></span></span></a></p></div>
<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://wakeupgirls3.jp/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://wakeupgirls3.jp/assets/ogp.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>TVアニメ「Wake Up, Girls！新章」公式サイト</q></span><span class="embed-html-box_description"><q>「Wake Up, Girls！新章」開幕！2017年TVアニメ放送決定！！
[STAFF]原作・脚本：Green Leaves／監督：板垣伸／キャラクター原案：近岡直／キャラクターデザイン：菅原美幸／音楽：神前暁 MONACA／音楽制作：DIVEIIentertainment／アニメーション制作：ミルパンセ　［CAST］吉岡茉祐／永野愛理／田中美海／青山吉能／山下七海／奥野香耶／高木美佑</q></span></span></a></p></div>

### 2017 年 3 月 17 日

アプリゲーム『**白猫プロジェクト**』にてイベント『**さされ！バンブーフォース**』が開催され、高木さんは**ミンミン**役を務めました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">今日は四神の武器ガチャと、ヴァリアントを仲間にできるイベント「さされ！ バンブーフォース」が始まるにゃฅ(●´ω｀●)ฅ<br>ミンミンのCVは、高木美佑さんにご担当いただいています(◍•ᴗ•◍)<a href="https://twitter.com/hashtag/%E7%99%BD%E7%8C%AB?src=hash&amp;ref_src=twsrc%5Etfw">#白猫</a> <a href="https://t.co/RQC95cY2Sh">pic.twitter.com/RQC95cY2Sh</a></p>&mdash; 【公式】白猫プロジェクト NEW WORLD&#39;S (@wcat_project) <a href="https://twitter.com/wcat_project/status/842591886468505600?ref_src=twsrc%5Etfw">March 17, 2017</a></blockquote>

### 2017 年 11 月 9 日

この日 ニコニコ生放送、YouTube Live などにて放送された「**英美里・美佑といっしょに『グラブル』！**」にて高木さんが CV を担当するグランブルーファンタジーの新キャラクター **ミリン** が発表されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">高木美佑さんが演じるキャラクター、ミリン初公開!! 【ニコ生視聴中】 【無料】英美里・美佑といっしょに『グラブル』！ <a href="https://t.co/BprgH7AHYM">https://t.co/BprgH7AHYM</a> <a href="https://twitter.com/hashtag/nicoch2596352?src=hash&amp;ref_src=twsrc%5Etfw">#nicoch2596352</a> <a href="https://twitter.com/hashtag/%E3%83%95%E3%82%A1%E3%83%9F%E9%80%9A%E3%83%81%E3%83%A3%E3%83%B3%E3%83%8D%E3%83%AB?src=hash&amp;ref_src=twsrc%5Etfw">#ファミ通チャンネル</a> <a href="https://twitter.com/hashtag/%E3%82%B0%E3%83%A9%E3%83%96%E3%83%AB?src=hash&amp;ref_src=twsrc%5Etfw">#グラブル</a> <a href="https://t.co/SQyBG5vRys">pic.twitter.com/SQyBG5vRys</a></p>&mdash; ファミ通.com (@famitsu) <a href="https://twitter.com/famitsu/status/928602216977506304?ref_src=twsrc%5Etfw">November 9, 2017</a></blockquote>

### 2017 年 11 月 17 日

**グランブルーファンタジー**にて、 **ミリン** が登場する **グランデフェス** の開催が発表されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【グランブルーファンタジー】グランデフェス開催のお知らせを公式サイトにて公開いたしました。詳しくはグランブルーファンタジー公式サイトをご確認ください。 ⇒ <a href="https://t.co/oNk7Gkfpdy">https://t.co/oNk7Gkfpdy</a> <a href="https://twitter.com/hashtag/%E3%82%B0%E3%83%A9%E3%83%96%E3%83%AB?src=hash&amp;ref_src=twsrc%5Etfw">#グラブル</a> <a href="https://t.co/EVV2xANFaP">pic.twitter.com/EVV2xANFaP</a></p>&mdash; グランブルーファンタジー (@granbluefantasy) <a href="https://twitter.com/granbluefantasy/status/931376600930643969?ref_src=twsrc%5Etfw">November 17, 2017</a></blockquote>

また、新キャラクター **ミリン** の紹介が公式サイトにて公開されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【グランブルーファンタジー】新キャラクター「ヴィーラ」「ミリン」の紹介を公式サイトにて公開いたしました。詳しくはグランブルーファンタジー公式サイトをご確認ください。 ⇒ <a href="https://t.co/8mAmb47sHm">https://t.co/8mAmb47sHm</a> <a href="https://twitter.com/hashtag/%E3%82%B0%E3%83%A9%E3%83%96%E3%83%AB?src=hash&amp;ref_src=twsrc%5Etfw">#グラブル</a> <a href="https://t.co/rH9AwvAizT">pic.twitter.com/rH9AwvAizT</a></p>&mdash; グランブルーファンタジー (@granbluefantasy) <a href="https://twitter.com/granbluefantasy/status/931403751587397632?ref_src=twsrc%5Etfw">November 17, 2017</a></blockquote>

### 2017 年 11 月 25 日

『**ぐらぶるちゃんねるっ！**』 #80 「お誕生日を祝おう」編 が公開され、高木さんがゲスト出演しました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【グランブルーファンタジー】「ぐらぶるちゃんねるっ！」#80 「お誕生日を祝おう」編を公開いたしました！「ぐらぶるちゃんねるっ！」の詳細は、グランブルーファンタジー公式サイトよりご確認ください。 ⇒ <a href="https://t.co/1P7Ja6MXru">https://t.co/1P7Ja6MXru</a> <a href="https://twitter.com/hashtag/%E3%82%B0%E3%83%A9%E3%83%96%E3%83%AB?src=hash&amp;ref_src=twsrc%5Etfw">#グラブル</a> <a href="https://t.co/WTevx7gCbf">pic.twitter.com/WTevx7gCbf</a></p>&mdash; グランブルーファンタジー (@granbluefantasy) <a href="https://twitter.com/granbluefantasy/status/934362290312306689?ref_src=twsrc%5Etfw">November 25, 2017</a></blockquote>

<iframe width="312" height="176" src="https://ext.nicovideo.jp/thumb/1511514042" scrolling="no" style="border:solid 1px #ccc;" frameborder="0"><a href="https://www.nicovideo.jp/watch/1511514042">「ぐらぶるちゃんねるっ!」 #80 お誕生日を祝おう編</a></iframe>

### 2018 年 3 月 10 日

なんですかねこれ……

**英美里・美佑といっしょに『モンハン：ワールド』** …？

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">18時からスタート！ 加藤英美里さんと高木美佑さんが『MH：W』をプレイ!! 【ニコ生視聴中】【ファミ通】英美里・美佑といっしょに『モンハン：ワールド』 <a href="https://t.co/y4tAanc2sF">https://t.co/y4tAanc2sF</a> <a href="https://twitter.com/hashtag/%E3%83%95%E3%82%A1%E3%83%9F%E9%80%9A%E3%83%81%E3%83%A3%E3%83%B3%E3%83%8D%E3%83%AB?src=hash&amp;ref_src=twsrc%5Etfw">#ファミ通チャンネル</a></p>&mdash; ファミ通.com (@famitsu) <a href="https://twitter.com/famitsu/status/972394996304261120?ref_src=twsrc%5Etfw">March 10, 2018</a></blockquote>

### 2018 年 6 月 15 日

高木さんが所属していた 声優ユニット **Wake Up, Girls！ の解散** が発表された 2018 年 6 月 15 日にアクセス数が大きく増えています。

### 2019 年 1 月 18 日

高木美佑みたいな声の VTuber **ハッカドール 1 号**さん が雑談生配信してました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">今晩、本気のわたしをお見せしましょうっ！（どやぁ）<br>【生放送】Vtuber１号ちゃんとたくさん雑談する <a href="https://twitter.com/hashtag/%E7%94%9F%E3%83%8F%E3%83%83%E3%82%AB?src=hash&amp;ref_src=twsrc%5Etfw">#生ハッカ</a> <a href="https://t.co/62aD7RFyvE">https://t.co/62aD7RFyvE</a> <a href="https://twitter.com/YouTube?ref_src=twsrc%5Etfw">@YouTube</a>さんから<a href="https://twitter.com/hashtag/HackaChan?src=hash&amp;ref_src=twsrc%5Etfw">#HackaChan</a></p>&mdash; ハッカドール☘8/15サ終 (@Hackadoll) <a href="https://twitter.com/Hackadoll/status/1086213774770528256?ref_src=twsrc%5Etfw">January 18, 2019</a></blockquote>

### 2019 年 2 月 13 日

VTuber **ハッカドール 1 号**さん が **にじさんじ**所属の VTuber **社築**さんとコラボ生配信をしていました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">もう無理　マジで無理　もうまじで　まじで震えが止まらない　無理 <a href="https://t.co/REFL0oQjTh">https://t.co/REFL0oQjTh</a></p>&mdash; 社築🖥 (@846kizuQ) <a href="https://twitter.com/846kizuQ/status/1095255473777831936?ref_src=twsrc%5Etfw">February 12, 2019</a></blockquote>

### 2019 年 3 月 8 日

声優ユニット **Wake Up, Girls！ のファイナルライブ** が行われた日、アクセスが増えています。

### 2019 年 4 月 1 日

この日、高木美佑さんが **Twitter アカウントを開設** しました。 え？ かわいい。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">高木美佑です。Twitterはじめました🔰<br>こちらでは、私のお知らせや独り言などを自由に垂れ流していきたいと思っております！<br>どうぞ、よろしくお願いします😇 <a href="https://t.co/LlqboMEXZ1">pic.twitter.com/LlqboMEXZ1</a></p>&mdash; 高木美佑 (@Yukgaejang98) <a href="https://twitter.com/Yukgaejang98/status/1112376297433358341?ref_src=twsrc%5Etfw">March 31, 2019</a></blockquote>

広川恵一さんのこのツイート好き。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">あん？高木美佑ちゃんツイッター始めたんか？</p>&mdash; 広川恵一 / ひろかわ けいいち (@HirokawaKeiichi) <a href="https://twitter.com/HirokawaKeiichi/status/1112717921145372677?ref_src=twsrc%5Etfw">April 1, 2019</a></blockquote>

### 2019 年 5 月 15 日

この日、ニュースアプリ『**ハッカドール**』のサービス終了が発表されました。高木美佑さんは **ハッカドール 1 号**役を務めていました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【大切なお知らせ】<br>君にシンクロするニュースアプリ「ハッカドール」は、2019年8月15日(木)にサービスを終了することになりましたっ！<br>ふええん、わたしたち無職ってことですかっ！？<br>詳しくはこちらっ！<a href="https://t.co/hAct5AFANV">https://t.co/hAct5AFANV</a> <a href="https://t.co/8n9sZbG0XO">pic.twitter.com/8n9sZbG0XO</a></p>&mdash; ハッカドール☘8/15サ終 (@Hackadoll) <a href="https://twitter.com/Hackadoll/status/1128495471972929536?ref_src=twsrc%5Etfw">May 15, 2019</a></blockquote>

### 2019 年 8 月 15 日

ニュースアプリ『**ハッカドール**』がこの日サービス終了を迎えました。この日は **ハッカドール THE あにめ～しょん 全話一挙放送**なども行われました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">君にシンクロするニュースアプリ「ハッカドール」<br>５年間応援してくれてありがとうございましたっ！<br>以上、ハッカドールでしたっ！ <a href="https://t.co/BmWqpKAwmp">pic.twitter.com/BmWqpKAwmp</a></p>&mdash; ハッカドール☘8/15サ終 (@Hackadoll) <a href="https://twitter.com/Hackadoll/status/1161949741854314496?ref_src=twsrc%5Etfw">August 15, 2019</a></blockquote>

### 2020 年 5 月 6 日

この日、高木さんの個人 **YouTube チャンネルが開設**され、テスト配信が行われました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">🌟お知らせ🌟<br>この度、わたくし高木美佑の<br>個人YouTubeチャンネルを開設しましたっ▶️<br><br>無事に準備が終わったら<br>本日23時頃からテスト配信をやる予定🥳<br><br>生放送なので、みなさまのコメントとお話出来たらと思います！<br>良かったらチャンネル登録してみてね💓<a href="https://twitter.com/hashtag/%E3%81%BF%E3%82%85%E3%83%BC%E3%81%A1%E3%82%85%E3%83%BC%E3%81%B6?src=hash&amp;ref_src=twsrc%5Etfw">#みゅーちゅーぶ</a><a href="https://t.co/FLQlWZj8pE">https://t.co/FLQlWZj8pE</a></p>&mdash; 高木美佑 (@Yukgaejang98) <a href="https://twitter.com/Yukgaejang98/status/1257868266338279424?ref_src=twsrc%5Etfw">May 6, 2020</a></blockquote>

### 2020 年 6 月 28 日

この日、 [**ゆるっと！ぐらぶる TV ちゃんねるっ！**](https://granbluefantasy.jp/pages/?p=31087){:target="\_blank" rel="noopener"} が放送され、ミリン役の高木さんも出演されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr"><a href="https://twitter.com/hashtag/%E3%82%86%E3%82%8B%E3%82%B0%E3%83%A9?src=hash&amp;ref_src=twsrc%5Etfw">#ゆるグラ</a> ありがとうございました！✨<br>ミリン役の高木美佑です！🔪<br><br>ルシファーHL、1ターン1ターン忘れてる事がないか心配で確認しながら汗かいてました😅<br>12の試練の所まで行けて楽しかったけど、やっぱり悔しいのでいつかリベンジしたいなぁ💪<br><br>放送では行けなかったバーカウンターも凄かったです🍸 <a href="https://t.co/vYsnnwhAbA">pic.twitter.com/vYsnnwhAbA</a></p>&mdash; 高木美佑 (@Yukgaejang98) <a href="https://twitter.com/Yukgaejang98/status/1277236105218146304?ref_src=twsrc%5Etfw">June 28, 2020</a></blockquote>

### 2020 年 7 月 26 日

この日、『**MixChannel Presents D4DJ CONNECT LIVE**』が開催され、**犬寄しのぶ**役の高木さんも出演されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">全部終わったので改めて！<br><br>無観客でしたが、4ヶ月ぶりに！<br>しかもみんな揃って！！！！<br>ライブができてとてもとても幸せでした☺️<br><br>ぜひみなさま感想教えてほしい〜！！！！<br><br>写真も少しずつアップするねっ📷<br>響子＆しのぶ 🤜\エモ/🤛<a href="https://twitter.com/hashtag/D4DJ%E3%82%B3%E3%83%8D%E3%82%AF%E3%83%88%E3%83%A9%E3%82%A4%E3%83%96?src=hash&amp;ref_src=twsrc%5Etfw">#D4DJコネクトライブ</a> <a href="https://t.co/MsxG6TMc1n">pic.twitter.com/MsxG6TMc1n</a></p>&mdash; 高木美佑 (@Yukgaejang98) <a href="https://twitter.com/Yukgaejang98/status/1287394459525685248?ref_src=twsrc%5Etfw">July 26, 2020</a></blockquote>

### 2020 年 10 月 28 日

この日、TBS 系列で『**D4DJ presents CDTV 特別編 みんな歌える！神プレイリスト音楽祭**』が放送され、高木さんも出演されました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.tbs.co.jp/program/cdtv-ongakusai_20201028/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(http://www.tbs.co.jp/program/um/v8/img/ogp/ogp_facebook_variety.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>D4DJ presents CDTV特別編<br</q></span><span class="embed-html-box_description"><q>TBS「D4DJ presents CDTV特別編<br</q></span></span></a></p></div>

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr"><a href="https://twitter.com/hashtag/D4DJ_CDTV?src=hash&amp;ref_src=twsrc%5Etfw">#D4DJ_CDTV</a> とんでもなく貴重な経験をさせていただきました🙏🥺<br><br>相川七瀬さんとコラボさせていただけたの、未だに信じられないですが、本当に素敵な方でした…♡幸せ！<br>ひな壇も楽しかった☺️<a href="https://twitter.com/hashtag/D4DJ?src=hash&amp;ref_src=twsrc%5Etfw">#D4DJ</a> <a href="https://twitter.com/hashtag/%E3%82%B0%E3%83%AB%E3%83%9F%E3%82%AF?src=hash&amp;ref_src=twsrc%5Etfw">#グルミク</a> 今後もキャストとして盛り上げていけるように頑張りますので、応援よろしくお願いします✨ <a href="https://t.co/Je9uUjyY0K">pic.twitter.com/Je9uUjyY0K</a></p>&mdash; 高木美佑 (@Yukgaejang98) <a href="https://twitter.com/Yukgaejang98/status/1321436988961026048?ref_src=twsrc%5Etfw">October 28, 2020</a></blockquote>

ゴールデンタイム地上波全国ネット何？ ブシロードすごい。

### 2020 年 12 月 6 日

この日、TOKYO MX にて『**ぐらぶる TV ちゃんねるっ！**』第 87 回 が放送され、高木さんがゲストで出演されました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://s.mxtv.jp/variety/grablue_tv/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://s.mxtv.jp/mcas_banner/mcas_l_grablue_tv.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>ぐらぶるTVちゃんねるっ！｜バラエティ｜TOKYO MX</q></span><span class="embed-html-box_description"><q>毎週日曜日　21:00～21:30 この番組は絶賛配信中の超大作ファンタジーRPG『グランブルーファンタジー』、略して「グラブル」の魅力を伝えていく番組です。|ぐらぶるTVちゃんねるっ！</q></span></span></a></p></div>

### 2021 年 1 月 1 日

なんですかねこれ……

**D4DJ TV お正月 12 時間スペシャル 2021** …？

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">🎍「D4DJ TV お正月12時間スペシャル2021」🎍<br><br>このあと[22:00]から TOKYO MXにてスタート❣️<br>タイムスケジュールをチェック👀✨<br><br>TVアニメ第9話も番組内[23:00]から放映📺<br>2021年の始まりをD4DJと一緒にお楽しみください🎉<br><br>YouTubeでも同時配信<br>☞<a href="https://t.co/JfXvLTfWSw">https://t.co/JfXvLTfWSw</a><a href="https://twitter.com/hashtag/D4DJ%E3%81%8A%E6%AD%A3%E6%9C%88%E7%89%B9%E7%95%AA?src=hash&amp;ref_src=twsrc%5Etfw">#D4DJお正月特番</a> <a href="https://t.co/tUo0ZimQnI">pic.twitter.com/tUo0ZimQnI</a></p>&mdash; D4DJ(ディーフォーディージェー)公式 (@D4DJ_pj) <a href="https://twitter.com/D4DJ_pj/status/1344990506795716608?ref_src=twsrc%5Etfw">January 1, 2021</a></blockquote>

### 2021 年 3 月 7 日

この日、YouTube などで『 **7 周年直前生放送！ グラブルアニバーサリー SP**』が放送され、ミリン役の高木さんも出演されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">グラブルRTA、応援ありがとうございました🙏<br>ミリン役の高木美佑です⚔️<br><br>ヨダ爺や、トレハン精鋭部隊が凄かったし<br>ミリンも活躍してくれて嬉しかった🥺<br>ドラマがあって楽しかったですー！<br><br>犬山さん本当にお疲れ様でした！素晴らしいプレイでした✨<a href="https://t.co/o9EHGPgLF9">https://t.co/o9EHGPgLF9</a><a href="https://twitter.com/hashtag/%E3%82%B0%E3%83%A9%E3%83%96%E3%83%AB?src=hash&amp;ref_src=twsrc%5Etfw">#グラブル</a> <a href="https://twitter.com/hashtag/%E3%82%B0%E3%83%A9%E3%83%96%E3%83%AB%E7%94%9F%E6%94%BE%E9%80%81?src=hash&amp;ref_src=twsrc%5Etfw">#グラブル生放送</a> <a href="https://t.co/6dZQCfkwau">pic.twitter.com/6dZQCfkwau</a></p>&mdash; 高木美佑 (@Yukgaejang98) <a href="https://twitter.com/Yukgaejang98/status/1368562674036961280?ref_src=twsrc%5Etfw">March 7, 2021</a></blockquote>

### 2021 年 6 月 5 日

**Virtua Fighter esports** の YouTube Live 『**負けたら即終了！？視聴者参加型「レジェンド組手配信」**』が配信され、高木さんは司会進行で出演されました。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">負けたら即終了!?視聴者参加型レジェンド組手配信＃1<br><br>お疲れ様でした～！<br>板橋ザンギエフさん14連勝！！<br>来週以降もご視聴ください！<br><br>アーカイブはこちら<a href="https://t.co/ao7FLunl0t">https://t.co/ao7FLunl0t</a><a href="https://twitter.com/hashtag/%E3%83%90%E3%83%BC%E3%83%81%E3%83%A3%E3%83%95%E3%82%A1%E3%82%A4%E3%82%BF%E3%83%BC?src=hash&amp;ref_src=twsrc%5Etfw">#バーチャファイター</a>　<a href="https://twitter.com/hashtag/VFes?src=hash&amp;ref_src=twsrc%5Etfw">#VFes</a> <a href="https://t.co/kDwBo1YOEx">pic.twitter.com/kDwBo1YOEx</a></p>&mdash; バーチャファイター公式／Virtua Fighter Official (@vf_official) <a href="https://twitter.com/vf_official/status/1401170218387267587?ref_src=twsrc%5Etfw">June 5, 2021</a></blockquote>

## 考察

なんとなくアクセス数が伸びるタイミングが分かった気がするのでまとめましょう。

新規コンテンツへの出演の場合には、キャスト発表のタイミングより、放送・配信のタイミングで伸びるようです。これはなんとなくアニメ見てたら出てきた人を調べようと思ったら Wikipedia を見るよなあ みたいなイメージで理解しています。キャスト発表のタイミングで騒いでる人はキャストを知っている人なので、Wikipedia を見るまでもないですね。

既存のコンテンツへの出演の場合には、発表タイミングで伸びることもあるようですね。TYPE-MOON 関連やグラブル、白猫プロジェクトがそんな感じですね。

あとは共演者のファンの方が多いような場合には伸びやすそうです。アイマス関連の声優で顕著そうですね。

あとは地上波ゴールデンタイムは強そうです。声優に詳しくない人がなんとなくテレビを見ていて興味を持った場合、Wikipedia を見ますよね。似た状況としては永野さんが Rakuten.FM TOHOKU に出たときとか、吉岡さんのかのおが便利軒とか。いつものファン層と違った層にリーチするのが重要そうですね。

あとマイナスの話題のときは伸びやすいように感じましたね。人間は邪悪な生き物。

## 感想

疲れました。思ったよりちゃんと理由が分かって良かったですね。

ここからはアドベントカレンダーについて。実は主催なので……いつも期日を守れなくてすいません。毎年紅白聴きながら書いてる気がするな……

ところで、私は WUG が大好きなので、みんなで WUG の話をする機会が永遠にほしいなあみたいなところがあり、アドカレはいい機会なので続けていきたいなと思っています。2017 年くらいから毎年[^adcal]集まっていただけてありがたい話ですね。

[^adcal]: 途中私が主催じゃない回もあります。

私自身アドカレ記事を読むのを楽しみにしていて、自分にはない視点、考え方、表現方法を 読む/見る のは面白いです。

今年もご参加（お書き/お読み）いただきありがとうございました！ 書いてくれる人がいて、読んでくれる人がいて、成り立つ企画です。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://adventar.org/calendars/6206" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-30x25.svg" style="background-image: url(https://adventar.org/og_image.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wake Up, Girls！ Advent Calendar 2021 - Adventar</q></span><span class="embed-html-box_description"><q>Wake Up, Girls！関連の記事ならなんでもOKです。愛のある記事をお願いします。お気軽にどうぞ。ハッシュタグ: [#WUG_ADVENT](https://twitter.com/hashtag/WUG_ADVENT)
枠が足りなくなった場合はどこかにリンクをまとめさせていただきますのでご連絡ください。

いくぞ！がんばっぺ！

**過去に開催されたもの**
[2020](https://adventar.org/calendars/4935) [2019](https://adventar.org/calendars/3985) [2018](https://adventar.org/calendars/3206) [2017](https://adventar.org/calendars/2232) [2014](https://adventar.org/calendars/678)
</q></span></span></a></p></div>

<small>PS. 2021 年も高木美佑現場にいると思いますので、機会があればよろしくお願いします。ブシロード沼に片足を突っ込んでいるのでそっち界隈の人も……</small>

---
