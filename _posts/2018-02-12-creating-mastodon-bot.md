---
layout: post
title: mastodonで作ったbotの話
categories:
  - technology
tags:
  - Tech
  - Ruby
  - mastodon
redirect_from:
  - /creating-mastodon-bot/
---

こんにちは。最近は[theboss.tech](https://theboss.tech){:target="_blank"}でクソbotの制作に勤しんでいるておりあです。

## つくったクソbot
- 俳句検出bot（[@find575@theboss.tech](https://theboss.tech/@find575){:target="_blank"}）
- 短歌検出bot（[@find57577@theboss.tech](https://theboss.tech/@find57577){:target="_blank"}）
- [@AnonymousPost@theboss.tech](https://theboss.tech/@AnonymousPost){:target="_blank"}

## なんでこんなん作ってんの？
### 俳句検出bot
[自鯖](https://wug.fun){:target="_blank"}でフォローしている人に、ニュース記事などから偶然できた５７５を見つけ出してトゥートしている人がいて、これ自動で検出するようにしたら楽しいのでは？と思って作ったのが俳句検出botです。細かいことを言うと俳句じゃなくて川柳だろとかあるんですが、語感を重視して俳句検出botです。

theboss.techで動かしているのはなんかあそこそういうのに寛大そう（偏見）だったからです。実際、歓迎していただいてるので寛大です。

短歌検出botは俳句検出botの要望を見ていたら短歌も検出して欲しいというのがあったので作りました。

詳しい説明は[マストポータル](https://mastportal.info/5445){:target="_blank"}に書いてあるのでご確認ください。

### AnonymousPost
<iframe src="https://theboss.tech/@the_boss/99437804997634914/embed" class="mastodon-embed" style="max-width: 100%; border: 1px solid #e1e8ed; border-radius: 5px;" width="400"></iframe><script src="https://theboss.tech/embed.js" async="async"></script>

というトゥートが鯖缶によってなされたので

<iframe src="https://theboss.tech/@AnonymousPost/99437924748252716/embed" class="mastodon-embed" style="max-width: 100%; border: 1px solid #e1e8ed; border-radius: 5px;" width="400"></iframe>

30分で作った。

<iframe src="https://theboss.tech/@the_boss/99438218725021495/embed" class="mastodon-embed" style="max-width: 100%; border: 1px solid #e1e8ed; border-radius: 5px;" width="400"></iframe>

この感じで開発者を匿名にしておく事も考えたのですが、DM設定をミスってバレてしまったので[オープンソース](https://github.com/theoria24/AnonymousPost4Mstdn){:target="_blank"}にしました。AGPL-3.0なので気をつけてください。

## 技術的な話とか、愚痴とか
いずれもRubyで、[tootsuite/mastodon-api](https://github.com/tootsuite/mastodon-api){:target="_blank"}を使って書いています。tootsuite/mastodon-apiを使う際に、`gem install mastodon-api`で入るものを使うとStreaming APIが使えないので注意してください。2018年2月11日現在、Gemfileとかで`'a3ff60a'`を指定するのがおすすめです（masterだとバグがある）。<small>指定できないオプションがあったりで使い勝手は微妙。頑張って欲しい（直せるほどの知識はない）</small>

俳句・短歌検出botには[r7kamura/ikku](https://github.com/r7kamura/ikku){:target="_blank"}というのを使っています。頭が助詞はダメとか終わりが名詞接続はダメみたいな判断をしているので、５７５なら検出されるわけではないです。また、外来語や新語に対応するため、辞書に[mecab-ipadic-NEologd](https://github.com/neologd/mecab-ipadic-neologd){:target="_blank"}を使っていますが、これはikkuが想定しているものとは違った挙動をする可能性があり、それによって誤検出や検出されないものがあると考えられます。

AnonymousPostは、画像を投稿するために一度ダウンロードして改めてアップロードしています。mediaのURLが再利用できると楽なんですが…せめてmediaのID指定すれば良いようになりませんかね？  
あとリモートの画像が`text_url`を持たないのもうーん🤔。本文からmediaのURLを除去するときに使いたいんだけどいい方法ないもんかなぁ。aタグにもmediaっぽいクラス付いてないし…

## 後日談
俳句検出botと短歌検出botがITmediaのマストドンつまみ食い日記に載りました。

- [マストドン　俳句があれば　見つけ出す](http://www.itmedia.co.jp/news/articles/1802/03/news040.html){:target="_blank"}
- [トゥートから短歌検出するボット、ておりあさんがまたも開発](http://www.itmedia.co.jp/news/articles/1802/11/news035.html){:target="_blank"}

またもって……ネタ切れ感がすごい。[TootCloudのとき](http://www.itmedia.co.jp/news/articles/1710/09/news030.html){:target="_blank"}と合わせて3回目です。

## その他
要望とかは常に受け付けています。[@theoria@theboss.tech](https://theboss.tech/@theoria){:target="_blank"}かそれぞれのGitHubにIssueとかでお願いします。プルリクも歓迎です。
