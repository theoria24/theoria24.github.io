---
layout: post
title: Amazon Rekognitionが高木美佑さんと誤認したみなさん
categories:
  - diary
tags:
  - Miyu Takagi
  - WUG
  - Tech
  - myuunews
  - AWS
  - Amazon Rekognition
key:
  - アドベントカレンダー
redirect_from:
  - /Mistaken-for-Miyu-Takagi-by-Amazon-Rekognition/
---

この記事は **Wugtodon Advent Calendar 2019** の 5日目の記事です。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://adventar.org/calendars/3956" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://adventar.org/og_image.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wugtodon Advent Calendar 2019 - Adventar</q></span><span class="embed-html-box_description"><q>https://wug.fun のアドベントカレンダーです。 WUG関連じゃなくて良いです。今年を振り返ったり振り返らなかったり最近ハマってるやつを紹介したりしなかったりしてください。 僕の一人アドベントカレンダーになりそうなのでなんでも書いてください。</q></span></span></a></p></div>

枠が余りまくっているので近々ブログを書く人はWugtodon Advent Calendar 2019の記事ということにしてください。テーマは特にないですが、人に紹介したいこととか今年の振り返りみたいなのが良いと思います。

## こんにちは！
こんにちは！ておりあです！**Wugtodon**（[wug.fun](https://wug.fun){:target="_blank" rel="noopener"}）の管理人をやっています。お世話になっております。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://wug.fun" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-120x63.svg" style="background-image: url(https://media.wug.fun/site_uploads/files/000/000/002/original/preview.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>wug.fun - Wugtodon</q></span><span class="embed-html-box_description"><q>Mastodon、やらせてください！　WugtodonはWake Up, Girls！が好きな人のためのMastodonサーバーです。 </q></span></span></a></p></div>

## myuunewsについて
WugtodonアドベントカレンダーなのにいきなりTwitterの話ですが、**@myuunews**という高木美佑さんの情報を収集するBotを動かしています。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://twitter.com/myuunews" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://pbs.twimg.com/profile_images/1178415009648406528/SOp8I1wY_400x400.jpg);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>myuunews（非公式）(@myuunews)さん | Twitter</q></span><span class="embed-html-box_description"><q>myuunews（非公式） (@myuunews)さんの最新ツイート。声優 高木美佑さんの情報を投稿するbotです。半自動。問題等はDMでお願いします。 2019年8月23日運用開始。管理者: @_theoria</q></span></span></a></p></div>

プログラムは [yoppinews/yoppinews-bot](https://github.com/yoppinews/yoppinews-bot){:target="_blank" rel="noopener"} を使わせて頂いております。MIT Licenseです。ありがとうございます。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://github.com/yoppinews/yoppinews-bot" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://avatars0.githubusercontent.com/u/50546502?s=400&amp;v=4);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>yoppinews/yoppinews-bot</q></span><span class="embed-html-box_description"><q>@yoppinews の関連ツイート検知モジュール. Contribute to yoppinews/yoppinews-bot development by creating an account on GitHub.</q></span></span></a></p></div>

それでですね、その機能に**関連画像の自動検出**というものがります。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 99.38% <a href="https://t.co/IaEPmuB2Fr">https://t.co/IaEPmuB2Fr</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1182677341669150720?ref_src=twsrc%5Etfw">October 11, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

こういうやつです。関係者が投稿した画像を調べまくるのは大変なので便利ですね。

### 仕組み
かんたんに。

AWSの **Amazon Rekognition** を使っています。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://aws.amazon.com/jp/rekognition/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://a0.awsstatic.com/libra-css/images/logos/aws_logo_smile_1200x630.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Amazon Rekognition（高精度の画像・動画分析サービス）| AWS</q></span><span class="embed-html-box_description"><q>Amazon Rekognition は、深層学習に基づいた画像認識および画像分析をアプリケーションに簡単に追加できるサービスです。数百万もの画像を検索、検証、整理し、画像内の物体、シーン、顔の検出、有名人の認識、画像の比較および不適切なコンテンツの識別などを行うことができます。</q></span></span></a></p></div>

Amazonさんが機械学習モデルを作ってくれているので、高木美佑さんの画像とTwitterのリストから取得したツイートに含まれる画像を比較して同一人物かを評価しています。

#### しかし
<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 96.56% <a href="https://t.co/44w6Fz42nw">https://t.co/44w6Fz42nw</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1193765404528775168?ref_src=twsrc%5Etfw">November 11, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

誤検出が……

Amazon Rekognitionは類似度を数値で返してくれるので、しきい値を高めにすることで誤検出を減らすことができますが、その代わりに本人の検出率も低下してしまうと思われます。そのため、多少の誤検出は許容していただきたく思います。

## 逆転の発想
**『Amazon Rekognitionが高木美佑さんと間違えた方々を集めて楽しんでいただこう！』**

まとめました。これは確かに似てるなとかこれは違うだろとか思ってください。<small>人ごとにまとめていますが、一部名前や所属を間違えている可能性があります。ごめん。ゆるして。あとでこっそり教えてくれるとありがたい。</small>

### 浜田翔子さん
アヴィラ所属（タレント事務所） / [事務所プロフィール](https://www.avilla.jp/talent/hamada/hamadaP.html){:target="_blank" rel="noopener"} / [Twitter](https://twitter.com/shokohamada){:target="_blank" rel="noopener"}

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 92.68% <a href="https://t.co/28twm6vx2K">https://t.co/28twm6vx2K</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1193875635892113409?ref_src=twsrc%5Etfw">November 11, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

### 宮原颯希さん
81プロデュース所属 / [事務所プロフィール](https://www.81produce.co.jp/dcms_plusdb/index.php/item?cell003=%E3%81%BE%E8%A1%8C&cell029=%E5%A5%B3%E6%80%A7&keyword=&cell028=&cell004=&name=%E5%AE%AE%E5%8E%9F%E3%80%80%E9%A2%AF%E5%B8%8C&id=312&label=1){:target="_blank" rel="noopener"} / [Twitter](https://twitter.com/miyamiya_satsu){:target="_blank" rel="noopener"}

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 91.10% <a href="https://t.co/a3TTcovZnf">https://t.co/a3TTcovZnf</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1177959525976027138?ref_src=twsrc%5Etfw">September 28, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

2枚目の左から2人目がヒットしています。

### 立花日菜さん
アーツビジョン所属 / [事務所プロフィール](https://www.artsvision.co.jp/talent/4704/){:target="_blank" rel="noopener"} / [Twitter](https://twitter.com/hinata__ba){:target="_blank" rel="noopener"}

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 93.22% <a href="https://t.co/pvd4kmlIct">https://t.co/pvd4kmlIct</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1193039117749235713?ref_src=twsrc%5Etfw">November 9, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

1枚目の右から4人目がヒットしています。

### 阿澄佳奈さん
81プロデュース所属 / [事務所プロフィール](https://www.81produce.co.jp/dcms_plusdb/index.php/item?cell003=%E3%81%82%E8%A1%8C&label=1&cell004=&name=%E9%98%BF%E6%BE%84%E3%80%80%E4%BD%B3%E5%A5%88&id=153){:target="_blank" rel="noopener"} / [Twitter](https://twitter.com/0812asumikana){:target="_blank" rel="noopener"}

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 95.10% <a href="https://t.co/DXUtF6Zhzc">https://t.co/DXUtF6Zhzc</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1185518566700912642?ref_src=twsrc%5Etfw">October 19, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 95.36% <a href="https://t.co/7oyihHjEQ3">https://t.co/7oyihHjEQ3</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1190505940350636032?ref_src=twsrc%5Etfw">November 2, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

### 三澤紗千香さん
スペースクラフト所属 / [事務所プロフィール](http://spacecraft.co.jp/misawa_sachika/){:target="_blank" rel="noopener"} / [Twitter](https://twitter.com/misawa_official){:target="_blank" rel="noopener"}

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 96.56% <a href="https://t.co/44w6Fz42nw">https://t.co/44w6Fz42nw</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1193765404528775168?ref_src=twsrc%5Etfw">November 11, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

右です。

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 93.09% <a href="https://t.co/rUCe4fbsRP">https://t.co/rUCe4fbsRP</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1197060365697404928?ref_src=twsrc%5Etfw">November 20, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 93.13% <a href="https://t.co/xQpGFn5ovs">https://t.co/xQpGFn5ovs</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1201118856481251328?ref_src=twsrc%5Etfw">December 1, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

右から2人目です。

### 森嶋優花さん
81プロデュース・エイベックス・ピクチャーズ 所属 / [事務所プロフィール](https://www.81produce.co.jp/actor_search/index.php/item?cell003=%E3%81%BE%E8%A1%8C&cell029=%E5%A5%B3%E6%80%A7&keyword=&cell028=&page=2&cell004=&name=%E6%A3%AE%E5%B6%8B%E3%80%80%E5%84%AA%E8%8A%B1&id=320&label=1){:target="_blank" rel="noopener"} / [Run Girls, Run！ Twitter](https://twitter.com/rgr_official_){:target="_blank" rel="noopener"}

<blockquote class="twitter-tweet"><p lang="ja" dir="ltr">【関連画像を自動検出】類似度: 92.66% <a href="https://t.co/U3MibFiIxt">https://t.co/U3MibFiIxt</a></p>&mdash; myuunews（非公式） (@myuunews) <a href="https://twitter.com/myuunews/status/1198962889526333442?ref_src=twsrc%5Etfw">November 25, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

右です。

## おわりに
そんな感じでポンコツなところもあるけれど頑張っています。気になった人はフォローしていただけるとやる気が出ます。よろしくおねがいします。

<a class="twitter-timeline" data-height="1000" href="https://twitter.com/myuunews?ref_src=twsrc%5Etfw">Tweets by myuunews</a> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

**Wugtodon Advent Calendar 2019** 5日目の記事でした！ありがとうございました！また書きます！

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://adventar.org/calendars/3956" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://adventar.org/og_image.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wugtodon Advent Calendar 2019 - Adventar</q></span><span class="embed-html-box_description"><q>https://wug.fun のアドベントカレンダーです。 WUG関連じゃなくて良いです。今年を振り返ったり振り返らなかったり最近ハマってるやつを紹介したりしなかったりしてください。 僕の一人アドベントカレンダーになりそうなのでなんでも書いてください。</q></span></span></a></p></div>

### 14:30追記
三澤さんの所属を間違えていたので修正しました。すみません。
