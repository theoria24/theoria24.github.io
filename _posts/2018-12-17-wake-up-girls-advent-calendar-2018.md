---
layout: post
title: WUG曲の歌詞を機械学習で分析してポエムを書きます
categories:
  - Anime
tags:
  - Anime
  - Tech
  - WUG
  - python
key:
  - アドベントカレンダー
---

この記事は **Wake Up, Girls！ Advent Calendar 2018** 17日目の記事です。今日は12月17日です。いいね？昨日はzourimusi64さんの **[WUGとクリエイターについて](https://adventar.org/calendars/3206#list-2018-12-16){:target="_blank" rel="noopener"}** のはずです。

<blockquote class="embedly-card"><h4><a href="https://adventar.org/calendars/3206">Wake Up, Girls！ Advent Calendar 2018 - Adventar</a></h4><p>Wake Up, Girls！に関する記事ならなんでもOKです。 2次、3次問わずWUG に関連する愛のある記事を募集しています。 動画とかイラストとかそういうのでもOKです〜 お忙しい場合は登録した日付より遅れての投稿なども問題ありません ゆるく楽しい雰囲気でやっていきましょう。 参考までに昨年のもの: [Wake Up, Girls！ Advent Calendar 2017](https://adventar.org/calendars/2232)</p></blockquote>
<script async src="//cdn.embedly.com/widgets/platform.js" charset="UTF-8"></script>

こんにちは、はじめましての人ははじめまして、ておりあです。WUGファン向けmastodonインスタンス [Wugtodon](https://wug.fun){:target="_blank" rel="noopener"} の運営とかをしています。

さて、2018年も終わろうとしておりますが、ワグナーの皆様におかれましてはいかがお過ごしでしょうか。僕は1日に5回くらい解散のことを思い出して落ち込みます。

今回の記事ですが、最近WUG曲を聞く時間が増え、この曲とこの曲の歌詞はやっぱり近いよなぁとか、意外とこの人とこの人の作詞の雰囲気近いんじゃないかとか思うことがありまして、これなんか見た感じでわかるやつがあれば面白いんじゃないかなぁと思っておりました。そういえば去年[こんな記事](http://kakawup.hateblo.jp/entry/2017/12/03/084602){:target="_blank" rel="noopener"}があったなぁ、歌詞で似たようなことができないかなぁと思った結果、表題のようなテーマとなりました。

<blockquote class="embedly-card"><h4><a href="http://kakawup.hateblo.jp/entry/2017/12/03/084602">Wake Up, Girls! official blogから見る7 Senses - KakawuBlog</a></h4><p>これはWake Up, Girls! Advent Calendar 2017 の 3日目の記事です。 2日目の記事は tkusanoさんの『wugnews backyard 』でした。 皆さん、こんにちわ っぷ。 WUGもAdvent Calendarをやる時代が来ましたね。 この機に はてなブログ 始めました。 あっブログと言えば(自然な切り返し) Wake Up, Girls!のブログ 、良いですよね。 どれだけ疲れていても</p></blockquote>

<small>はじめに言い訳をさせていただくと、私は機械学習とかプログラミングとかを専門でやっているわけではなくて、面白そうだなぁと思ったことをGoogle先生に聞いたりしながらやっているだけなので、ミスや誤認などあるかと思いますがそのあたり大目に見ていただけると大変ありがたく思います。[ぜんぜんわからない　俺たちは雰囲気で機械学習をやっている](https://orekabu.jp/bakakabu/){:target="_blank" rel="noopener"}</small>

### やったこと

#### 1. 歌詞を収集する

意外と問題になってくるのがこれです。無理です。ネットの海を漂うと、歌詞サイトからスクレイピングしていることが多いのですが、WUGの曲が全部掲載されているサイトがなさそうなので[Wikipedia](https://ja.wikipedia.org/wiki/Wake_Up,_Girls!%E3%82%B7%E3%83%AA%E3%83%BC%E3%82%BA%E3%81%AE%E3%83%87%E3%82%A3%E3%82%B9%E3%82%B3%E3%82%B0%E3%83%A9%E3%83%95%E3%82%A3){:target="_blank" rel="noopener"}とか[Anime Resource List](https://arl.jp/wiki/Wake_Up,_Girls!/%E3%83%87%E3%82%A3%E3%82%B9%E3%82%B3%E3%82%B0%E3%83%A9%E3%83%95%E3%82%A3){:target="_blank" rel="noopener"}とかを見ながら地道に集めました。自動化できないことはないと思うのですが、技術もないしめんどくさくなって6割くらい手動で取ってきました。なんかいい方法知ってる人がいたら教えて欲しいくらいです。

スクレイピングするやつは以下のサイトを参考にしました。色んなサイトからちょっとずつ取ってくるような場合だとHTML構造をいちいち確認しないといけないのでめんどくさいですね…

<blockquote class="embedly-card"><h4><a href="https://qiita.com/nekoumei/items/b1afca7cfb9e54303ab4">WordCloudで凛として時雨の歌詞の傾向を可視化する - Qiita</a></h4><p>コード類をGitHubにあげました。プルリクお待ちしております！ https://github.com/nekoumei/lyric_visualizer_with_wordcloud この記事では、pythonを使って↓こういう図をつくります 僕が大好きな日本の3ピースバンドです。 プログレッシブな曲展開が魅力の凛として時雨ですが、歌詞のセンスが独特でおもしろいです。 ...</p></blockquote>

最終的に収集した楽曲のリストは以下のとおりです

> 大空のプリズム, 言の葉 青葉, 16歳のアガペー, 7 Girls War, 太陽曰く燃えよカオス 岡本未夕 ver., リトル・チャレンジャー, シャツとブラウス, 極上スマイル, ジェラ, ハジマル, WOO YEAH!, 歌と魚とハダシとわたし, 可笑しの国, オオカミとピアノ, スキ キライ ナイト, ステラ・ドライブ, 極上スマイル Wake Up,  Girls! ver., タチアガレ！, ワグ・ズーズー, あぁ光塚歌劇団, DATTE, 少女交響曲, 素顔でKISS ME, 運命の女神, 地下鉄ラビリンス, Beyond the Bottom, レザレクション, 止まらない未来, セブンティーン・クライシス, プラチナ・サンライズ, お約束たいそう, HIGAWARI PRINCESS, 走り出したencore, It’s amazing show time☆, それいけオトメ, ヒカリキラリミルキーウェイ, snuggery, Into The Light, 青い月のシャングリラ, outlander rhapsody, タイトロープ ラナウェイ, 僕らのフロンティア, HELP ME！みゅーちゃん！, 桜色クレッシェンド, 狐草子, Why am I, ももいろDiary♡, てがみ, わたしの樹, 恋？で愛？で暴君です！, TUNAGO, ゆき模様 恋のもよう, One In A Billion, 王様のカデンツァ, 雫の冠, 7 senses, 同じ夢を見てる, タチアガレ！6人ver., ユメ、まっすぐ。, Non stop diamond hope～Mayu ver.～, Party! Party!, Non stop diamond hope～Airi ver.～, ぽんとPUSH! もっとSMILE!, Non stop diamond hope～Minami ver.～, Dice of Life!, Non stop diamond hope～Yoshino ver.～, ドラマチックを君と, Non stop diamond hope～Nanami ver.～, プライド, Non stop diamond hope～Kaya ver.～, シャリラ!, Non stop diamond hope～Miyu ver.～, 君とプログレス, Jewelry Wonderland, SHIFT, スキノスキル, GloriA, now is the time, あのね, Trouble!? Travel, 解放区, 七つの海のコンサート, minority emotions, Polaris, One In A Billion -Wake Up,  Girls！ver.-, 無限大ILLUSION 2017, Knock out, カケル×カケル, Glossy World

個人的に吉岡さんの作詞が気になっていまして、ソロイベ曲の歌詞も含む形になっています。若干問題がありそうですが許してください。[こんな感じ](https://imgur.com/Jh04453){:target="_blank" rel="noopener"}のCSVにまとめました。歌詞を取得できる感じにするとマズそうなので画像です。

#### 2. 必要な単語を選択

実行したコードは一番下に埋め込んでありますので気になる方はそちらを…

何も考えずにやると助詞とかがめちゃくちゃ主張してくるので、MeCabを使って **名詞、動詞、形容詞、形容動詞、副詞** を選び取りました。それでも意味のない単語が主張してきたので、[SlothLibのストップワードリスト](http://svn.sourceforge.jp/svnroot/slothlib/CSharp/Version1/SlothLib/NLP/Filter/StopWord/word/Japanese.txt){:target="_blank" rel="noopener"}を利用してストップワード処理を行いました。

#### 3. よくわからないけどとりあえずワードクラウドにしてみる

よくわかりません。当方に[たまたま](https://mastportal.info/4859){:target="_blank" rel="noopener"}ワードクラウドを作る基盤があったので、おもむろに（誤用）歌詞を全部突っ込んでワードクラウドを作ります。

使用頻度が高い単語は大きく、低い単語は小さく表示されるやつです。単語の色や場所は関係ありません。

こんな感じになりました。

<figure>
  <a href="https://i.imgur.com/QOI94xR.png"><img src="https://i.imgur.com/QOI94xR.png"></a>
</figure>

WUGの楽曲はわたしたちに **笑顔** を与えてくれるようです。いい話。

### 4. Doc2Vecの学習

いよいよ機械学習ですが、今回はこちらの **gensim** というライブラリを使って **Doc2Vec** をやっていきます。

<blockquote class="embedly-card"><h4><a href="https://radimrehurek.com/gensim/">gensim: topic modelling for humans</a></h4><p>Efficient topic modelling in Python</p></blockquote>
<script async src="//cdn.embedly.com/widgets/platform.js" charset="UTF-8"></script>

#### Doc2Vec？

**Doc2Vec**では任意の長さの文章をベクトル化することができ、文章の類似度計算などができるようです。

これを使って歌詞の類似度を計算していきたいなぁと思います。

#### 結果

難しいことはよくわかりませんが、下のような結果が得られました。なるほどね？

<figure>
  <a href="https://i.imgur.com/5dkPg0L.png"><img src="https://i.imgur.com/5dkPg0L.png"></a>
</figure>

真ん中の方の混み合ってる部分を拡大したものが以下になります。

<figure>
  <a href="https://i.imgur.com/Cjt2y7e.png"><img src="https://i.imgur.com/Cjt2y7e.png"></a>
</figure>

見づらいね。

### ポエム

この結果を受けまして、思ったことを書いていきます。

#### すきなところ

- 右上に **只野菜摘**さん、中ほどに **こだまさおり**さん、左下に **吉田詩織**さん が比較的多いように見え、作詞者ごとの傾向がやや見える
- **太陽曰く燃えよカオス** がめちゃくちゃ外れたところにいて 畑亜貴さんのすごさが感じられる
- **ぽんとPUSH！もっとSMILE！** もめちゃくちゃ外れてるので y0c1eさんもすごい
- **Poraris** の近くに **わたしの樹**、**解放区** 等があり、WUGのリーダーは青山吉能さんなんだなぁと思った
- **極上スマイル** と **運命の女神** が被っており、I-1の統一感が感じられる<small>（運命の女神作ったの誰って設定なんだろう🤔）</small>
- **可笑しの国** と **Party!Party!**、**It’s amazing show time☆** と **シャリラ！** が近くにあり、作詞者が違ってもキャラクターとしての統一感が感じられる
- **大空のプリズム** と **snuggery** の位置が近いので訝しんで歌詞をよく見ると、近い。気づかなかった。
- **Non stop diamond hope**、みゅーver.だけ若干外れたところにあり、歌詞中の自分のことと仲間のことの割合が効いてきてそう。みゅーちゃん輝いてほしいなぁ。

#### アなところ

- 辛矢凡さんの曲と他の曲との関連性を見いだせなかった。<small>個人的にGloriAとか近いかなと思っていた</small>
- 近くなさそうなのに近くなってしまうものがある。パラメータいじってなんとかしたかったが難しかった。
- これ日本語の学習モデルを歌詞の他にも準備しておかないとうまくいかないのでは？（わからん）

### 感想

よくわかりません。なれないことはするものじゃないね。

最近<s>ゆゆ</s>なんらかの影響でWUGの作曲の傾向の話をしてる人が多い気がするんですが、作詞も見てほしいよねと思いつつ、文才もないので機械学習でやっちゃおｗと思ってこんなテーマを選んだのですが、大きな成果は得られませんでした。もっと機械学習詳しい人にやってもらったら何か見えてくるのかもしれません…

これ以上書けることがないので、**Polaris**の歌詞について書きます。

#### 終わらないよ ボクら Dreamer

僕はもともとアニメWUGのオタクなので、そっち目線になります。苦手な人は適当に…

新章まではアニメの要所で歌われる曲は辛矢凡さんが作詞されており、（おそらく）いちばんアニメWUGのことを考えてきた山本寛さんの考えを反映した歌詞となっていたように思います。

新章からは山本さんも1期シリーズ構成の待田さんも制作に参加されていませんので、それでは誰がいちばんWUGのことを考えているのか、誰がいちばん歌詞を書くべきか。WUGちゃん自身なのでしょう。僕はそう思いました。<small>もちろん新章監督の板垣さんや脚本の松田さんが書いても良いんですが…</small>

さて、それでは歌詞の内容について……

僕はこの歌詞にはこれまでのアニメ本編に登場した楽曲の歌詞を意識した、あるいは意識せずともリンクしてしまった部分が多々あるように感じます。

頭の方から少しだけ…

『街明かり消えた夜 〜』の部分はどうしても震災のことを思い出してしまいます。過去の楽曲で言えば **タチアガレ！** の『ひどく傷ついて　残酷な海に』を想起します。

それに続く『君と見た景色さえ 黒く塗りつぶされて』は菊間夏夜の過去を、菊間夏夜のキャラソン『スキ キライ ナイト』を思い出させます。このパートは奥野さんが歌っているのも相まって激エモになりますね…

『諦めて逃げたくなった天に』これは **タチアガレ！** の『ただ怯えすぐ背を向けた』を、『一番星めがけ駆け出そう』は『Stand Up!　迷いなく走り出そう』、『奇跡が ボクを導いてく』は『今　夢に向かうよ』『胸の希望が君と重なる』『この先に未来がある』でしょうか。

僕は伏線というか、過去とのリンクみたいなものが大好きなので、Polarisのこういうところがほんとすきです。僕にとってPolarisという楽曲自体が **未来と今ツナグ Twinkle star** なんだよなぁ。

今回はひとまずここまで。みなさんも歌詞について解釈を考えて、教えてくださいね。

### 終わりに

最後までお付き合いいただきありがとうございました。<small>あと遅れてすいません。</small>

また、今回のアドベントカレンダーを企画してくださった gomi_ningenさん、ありがとうございました。

そして、WUGちゃん。解散するときまで、いや、その後も、応援し続けます！ありがとう！がんばっペ！

**Wake Up, Girls！ Advent Calendar 2018**、明日はみそみそピーナツ とみー。さんの[WakeUp,Girls!についての回顧録](https://privatter.net/p/4118268){:target="_blank" rel="noopener"}です。

#### 補足

今回実行したコードは以下のとおりです。<small>一部地獄みたいな実装になっている…</small>

<script src="https://gist.github.com/theoria24/ed4207c31e3f58ae55dbe5116430b6a2.js"></script>
