---
layout: post
title: WUGメンバーが声を当てたキャラクターの見た目を分析します
categories:
  - Anime
tags:
  - Anime
  - WUG
  - Wake Up Girls!
key:
  - アドベントカレンダー
  - animeface-2009
twimage: https://i.imgur.com/AIsrAhz.jpg
---

この記事は **Wake Up, Girls！ Advent Calendar 2020** の 20 日目の記事です。 ~~今日は 12/20 です。~~

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://adventar.org/calendars/4935" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://adventar.org/og_image.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wake Up, Girls！ Advent Calendar 2020 - Adventar</q></span><span class="embed-html-box_description"><q>Wake Up, Girls！関連の記事ならなんでもOKです。 愛のある記事をお願いします。お気軽にどうぞ。 いくぞ！がんばっぺ！ 2019: https://adventar.org/calendars/3985 2018: https://adventar.org/calendars/3206 2017: https://adventar.org/calendars/2232 2014: https://adventar.org/calendars/678 </q></span></span></a></p></div>

## こんにちは！

こんにちは！ておりあです！Advent Calendar 2020 主催です！！！全然間に合ってなくてすいません！！！！！

Wugtodon（[wug.fun](https://wug.fun){:target="\_blank" rel="noopener"}）という mastodon サーバーの管理人をやっています。最近サーバーを増強したのでちょっと早くなりました。よろしくおねがいします。

mastodon…？って何？って方は ↓ の記事を読んだり読まなかったりしてください。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://theoria24.github.io/article/2019/12/01/what-is-wugtodon.html" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://theoria24.github.io/images/logo.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wugtodon…って何…？</q></span><span class="embed-html-box_description"><q>この記事は Wugtodon Advent Calendar 2019 の 1日目の記事です。</q></span></span></a></p></div>

## 言い訳

僕は Advent Calendar を書くときはなんか新しいものを触ってそれに関するやつを書きたいと思っている（WUG 駆動開発[^1]）ので、ディープラーニングってやつ流行ってんな（時代遅れ）となってそれっぽいやつをやりたかったのですが余裕がなさすぎて諦めました。

ので、その残骸みたいな記事になります。すいませんが、よろしくお願いいたします。

## さて

### 発端

WUG ちゃんも最近はいろんなアニメで見るなぁ（しみじみ）

せや、メンバーごとにキャラクターの特徴見ていったら面白んちゃうか？（エセ関西弁）

キャラクターの画像からキャラの色とか取り出して比べてみるか。

できるだけ主観が入らないようにテクノロジーの力を借りたいと思い…

### animeface-2009

界隈で有名なやつ、 **animeface-2009** があります。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://github.com/nagadomi/animeface-2009" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://avatars1.githubusercontent.com/u/287255?s=400&amp;v=4);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>nagadomi/animeface-2009</q></span><span class="embed-html-box_description"><q>Face and Landmark Detector for Anime/Manga. This is 2009s version of Imager::AnimeFace, but it works on recent system. - nagadomi/animeface-2009</q></span></span></a></p></div>

インストールが難しい的なことが書いてあるのでビビってましたが大丈夫でした[^install]。

これを使うとこんな感じに顔とパーツの位置、髪、肌、目の色を検出してくれます。

<figure class="half">
  <a href="https://i.imgur.com/Atfxjbj.png"><img src="https://i.imgur.com/Atfxjbj.png"></a>
  <a href="https://i.imgur.com/b6CqNH5.png"><img src="https://i.imgur.com/b6CqNH5.png"></a>
  <figcaption>animeface-2009で検出された顔とランドマーク</figcaption>
</figure>

なかなかいい感じなのでこれでキャラクターのイラストから髪の色とかを取って比べたいですね。

### 画像集め

アニメのスクリーンショット等だとカットによって効果が違ってアレだと思ったので Wikipedia の情報を頼りに公式サイトや作者のブログ等から頑張って集めます。

公式サイトには設定画がないのにプレスに出てるやつとかもあったのでそれも。

### 集まった画像

顔を切り出したやつです。顔が検出されなかったやつはとりあえず諦めました。すいません。

1 人ずつ。

<figure>
  <center>
    <a href="https://i.imgur.com/GFlBrxx.jpg"><img src="https://i.imgur.com/GFlBrxx.jpg"></a>
    <figcaption>吉岡茉祐さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/JbBmRkT.jpg"><img src="https://i.imgur.com/JbBmRkT.jpg"></a>
    <figcaption>永野愛理さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/tsUANht.jpg"><img src="https://i.imgur.com/tsUANht.jpg"></a>
    <figcaption>田中美海さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/xNTiGeC.jpg"><img src="https://i.imgur.com/xNTiGeC.jpg"></a>
    <figcaption>青山吉能さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/Jcwz5eC.jpg"><img src="https://i.imgur.com/Jcwz5eC.jpg"></a>
    <figcaption>山下七海さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/LSfi9yr.jpg"><img src="https://i.imgur.com/LSfi9yr.jpg"></a>
    <figcaption>奥野香耶さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/VmjkkJb.jpg"><img src="https://i.imgur.com/VmjkkJb.jpg"></a>
    <figcaption>高木美佑さん</figcaption>
  </center>
</figure>

思ったより見てないコンテンツが多くてヤバいなとなった。

### 色の表し方

肌の色、髪の色は取れてきたのでこれを図にプロットしていけば良いでしょう。

さて……

あれ？？？？？

色って平面図に表現できるんか？？？？？

見切り発車でした。

### CIE1931 色度図

CIE（国際照明委員会）で 1931 年に規定された、物理的な色と心理学的な色の関係を初めて定量的に定義した色空間である **CIE1931 色空間** から輝度を除いて xy 平面上で色度を表したものらしいです。詳しくはググってください。

これで色をなんとなく比較できそう？

## やってみました

Python に **Colour** という色に関することが色々できそうなのがあり、色度図も描けるようだったので、使いました。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://www.colour-science.org/" target="_blank" rel="noopener nofollow"><span class="embed-html-box_metano-image"><span class="embed-html-box_title"><q>Colour Science for Python</q></span><span class="embed-html-box_description"><q>Colour is an open-source Python of algorithms and datasets for colour science.</q></span></span></a></p></div>

### 髪の色

まずは髪の色から（カラフルそうなので）

<figure>
  <center>
    <a href="https://i.imgur.com/WOlPSUz.png"><img src="https://i.imgur.com/WOlPSUz.png"></a>
    <figcaption>吉岡茉祐さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/ti8OrEv.png"><img src="https://i.imgur.com/ti8OrEv.png"></a>
    <figcaption>永野愛理さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/f5XF7Aa.png"><img src="https://i.imgur.com/f5XF7Aa.png"></a>
    <figcaption>田中美海さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/hSBm2wi.png"><img src="https://i.imgur.com/hSBm2wi.png"></a>
    <figcaption>青山吉能さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/armvqNB.png"><img src="https://i.imgur.com/armvqNB.png"></a>
    <figcaption>山下七海さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/GH0Zm20.png"><img src="https://i.imgur.com/GH0Zm20.png"></a>
    <figcaption>奥野香耶さん</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/8Ahnwcp.png"><img src="https://i.imgur.com/8Ahnwcp.png"></a>
    <figcaption>高木美佑さん</figcaption>
  </center>
</figure>

いかがでしょうか。難しいですね。

以下感想です（定量的に見ていないので直感的なやつ）

- 田中さん山下さんはかなり広い範囲をカバーしている
- 青山さんは青系に寄っている感がある
- 吉岡さんは青系・橙系がほとんど（茶髪が橙に入ってそう）
- 高木さんはオレンジ〜赤〜ピンク（右の方）が多い

イメージと比べてどうでしょう？ 私は割とまあそんな感じだよなあとなりました。

参考のためにアニメ WUG のキャラクターだけを抽出してみましょう。旧章です。

<figure>
  <center>
    <a href="https://i.imgur.com/zEqWv2T.png"><img src="https://i.imgur.com/zEqWv2T.png"></a>
    <figcaption>髪の色（アニメWUG）</figcaption>
  </center>
</figure>

上の傾向に概ね当てはまってるかなと感じました（岡本ちゃんの髪色ピンクに寄ってるんだ）。

全キャラクター分を重ねてみます。

<figure>
  <center>
    <a href="https://i.imgur.com/3HR6RnS.png"><img src="https://i.imgur.com/3HR6RnS.png"></a>
    <figcaption>髪の色（全キャラ分）</figcaption>
  </center>
</figure>

なんもわからん

大きく外れているところを確認してみましょう。

<figure>
  <center>
    <a href="https://i.imgur.com/503foZO.png"><img src="https://i.imgur.com/503foZO.png"></a>
    <figcaption>中心から外れている点のキャラクター</figcaption>
  </center>
</figure>

ソシャゲのキャラとか擬人化は極端な色使いになりがちですね。

改めて田中さんのカバー範囲が広いのが分かった。すごい。

髪の色は割と性格とかに関わってくる気がするのでなんとなく傾向が見えてよかったですね。

作品によってどれくらい極端に変えるかが違うので現実よりの作品は今回は埋もれてしまいました。なんかうまいこと重み付けできると良いんですけどね……

### 肌の色

これほぼ同じなので全部まとめて離れているとこだけ確認しますね……

結果

<figure>
  <center>
    <a href="https://i.imgur.com/WpzR1SS.png"><img src="https://i.imgur.com/WpzR1SS.png"></a>
    <figcaption>肌の色（全キャラ分）</figcaption>
  </center>
</figure>

<figure>
  <center>
    <a href="https://i.imgur.com/MqMTIsb.png"><img src="https://i.imgur.com/MqMTIsb.png"></a>
    <figcaption>中心から外れている点のキャラクター</figcaption>
  </center>
</figure>

右の方の黒っぽい肌のキャラには田中さんが多めですが、そもそものキャラ数が多いので幅の広さ……という感じです。高木さんも多いですね。肌の色と性格を結びつけるのは難しいので語ることがない……日焼けとかは言えるかもしれないですが今回特にいないので……

一方で下の方、ピンクよりは山下さんが多いかな…？ これは描き方にも影響されそうですが……

あんまり肌の色で人を分類すると問題になるのでやめます。

## 感想

animeface-2009 が便利でいい感じの画像をいい感じに用意できればいい感じの遊びができそう。画像処理で rmagick とか matplotlib とかの勉強になった。

色を比較するの難しいですね。今回色度だけを比較しているので灰色と黒はほぼ同じところに出ています。どうなんでしょう。なんかいい方法をご存じの方がおりましたらこっそり教えてください。やっぱり 3 次元系か…？

髪の色はなんとなく傾向が見られた気がしますが、まだ演じたキャラ数自体少ないのでもっと増えていくと何もわからなくなるのかなと思いました。

肌の色はあんまり差がないので難しいですね。ゾンビィの方のリリィ入れとけばよかった。

これらの画像を使ってディープラーニング的に遊びたかったのですが、データが少ないので厳しいのかな。ちょっと余裕がないのでまた今度……

## Wake Up, Girls！ Advent Calendar 2020

全然間に合っていませんが WUG Advent Calendar 2020 の記事でした。

<div class="embed-html-box"><p class="embed-html-box-inner"><a href="https://adventar.org/calendars/4935" target="_blank" rel="noopener nofollow"><span class="embed-html-box_image"><img src="https://woinc.jp/img/cache/thumbnail-1x1.svg" style="background-image: url(https://adventar.org/og_image.png);"></span><span class="embed-html-box_meta"><span class="embed-html-box_title"><q>Wake Up, Girls！ Advent Calendar 2020 - Adventar</q></span><span class="embed-html-box_description"><q>Wake Up, Girls！関連の記事ならなんでもOKです。 愛のある記事をお願いします。お気軽にどうぞ。 いくぞ！がんばっぺ！ 2019: https://adventar.org/calendars/3985 2018: https://adventar.org/calendars/3206 2017: https://adventar.org/calendars/2232 2014: https://adventar.org/calendars/678 </q></span></span></a></p></div>

みなさんたいへんアツい文章を書いてくださり毎日楽しく読ませていただいておりました。

実は私このカレンダーの主催なので、なんか思ってることを書いておきたいなと思うので、書きます。

3 年前でしょうか、某所で Advent Calendar というものを見かけて[^adcal]、技術系の文章が多いかなという印象でしたが、それだけでなく趣味系でもやられているのを見て、私には WUG しかなかったので、立てました。

生来 文化祭的な 1 つのことに向かってみんなで頑張るみたいなのが好きだったので、みんなで WUG に関するブログ書いたら楽しいよなあ、それくらいの気持ちでした。私のような弱小ワグナーが立てたところで埋まるのかみたいな不安はありましたが当時は余裕があったのでまあいけるだろうと。

そしてなんだかんだで今年で 4 年も続いて…… 皆様のおかげです。本当にありがとうございます。こんな期日も守れない主催のカレンダーに参加していただいて……素晴らしい文章やその他の表現を見せていただいて…………

昔から、夜中に突然 TL に湧いてきて、なんかネガティブなこと言ってみんなで頭抱えてるみたいなワグナーが大好きだったので、そういったなんとなく繋がっているんだみたいな状況が大好きだったので、そういう関係が続いていったらなあと思っています（もちろんポジティブなこと言い合うのが良いよ）。

私には文才とかないので、そういった場を準備できたらなあと思います。みんな WUG という一番星めがけて走ってきた仲間だと思っているので。たまには思い出して思い出を、そして未来を語り合いたいので。

とりとめのない文章になってしまいましたが、お読みいただきありがとうございました。あっ、 2021 年もよろしくお願いします。

---

[^1]: 元ネタ\: [アイマス駆動開発](https://www.slideshare.net/treby/imas-driven-developemnt){:target="\_blank" rel="noopener"}
[^install]: build.sh を[ちょっといじった](https://gist.github.com/theoria24/3121c6212e05da64bcdfd28843bcf0e5){:target="\_blank" rel="noopener"}だけで入った
[^adcal]: mastodon には情報系の人が多く、そういう文化を学べた
