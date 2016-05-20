---
layout: post
title: MacでMMDを動かす
---

だいぶ久しぶりの更新になってしまいましたね…

昔UbuntuとOneDriveでファイルを同期するやつの[記事](../OneDrive-Ubuntu/)を書いたんですが[OneDriveの容量が縮小されたりする](http://pc.watch.impress.co.jp/docs/news/20151104_728819.html)らしいので利用している人は気をつけてください。一応データは1年位大丈夫らしいんですが。

で、本題です。
タイトルの通りなんですが、MacでMMDを動かしたい。

本家MikuMikuDanceはDirectXやらVisual C++ランタイムやらを利用しており、Windowsでしか動作しないんですね。

普通にBootcampでデュアルブートしたりVirtualPCでWindows入れたりすれば使えるだろって話なんですが、SSDの空き容量的にそれは厳しいので別の方法を探します。

まず最初に当たったのは[VPVP（Vocaloid Promotion Video Project）](http://www.geocities.jp/higuchuu4/)（公式）。

Macのことは書いてないですね（当然）

[VPVP wiki – Mac用覚え書き](http://www6.atwiki.jp/vpvpwiki/pages/450.html)を発見。

Blender、Metasequoiaはモデリング用っぽい（偏見）のでまた今度。（[Unityで動かす方法もある](http://mmd-for-unity-proj.github.io/mmd-for-unity/)らしいのですが容量の関係でパス）

ページを見ていくと… MMDAI2！！これだ！！！！ → [MMDAI Project Portal2](http://hkrn.github.io/MMDAI/)

　　　↓

> ## INFO
> ###【重要】
> MMDAI2/VPVM は配布を終了しました。今後の再配布の予定はありません。

け、けわしい〜〜〜、けわしい〜〜〜〜〜〜〜〜  
でも、

> 現在代替として[nanoem](http://blog.hikarin.jp/2015/06/nanoem-for-osx.html)が公開されています。

とのこと。  
やったぜ！

無料・無保証ということで自己責任で利用するようにとのこと。はじめからそのつもりなので喜んでDL。

アプリを立ち上げるとこんな感じ

![nanoem](http://theoria24.github.io/images/nanoem.png)

とりあえずあんまり凝ったもの作るのもめんどくさい()ので手元にあった[おんだ式 ハッカドール1号](http://3d.nicovideo.jp/works/td23472)を開いてみると…

![ハッカドール1号](http://theoria24.github.io/images/nanoem_hacka1.png)

おおおお！！！普通に開けた！！！！！うおおおおお！！！！！！！

モーションも付けてみよう！

例のごとくめんどくさいので手元にあった[Daisukeのモーション](http://www.nicovideo.jp/watch/sm14987400)を放り込むと…

[![Daisuke](http://img.youtube.com/vi/rr819tfoToY/0.jpg)](https://www.youtube.com/watch?v=rr819tfoToY)

普通に動いた！！！普通に嬉しい！！！！！普通に！！！

そんな感じでMacで普通にMMDモデルとモーションを使った動画が作れることを[かくにん！よかった。](http://www.excite.co.jp/News/reviewbook/20140509/E1399598138826.html)

モデル動かせるくらいだろうと思ったらエフェクトも動かせるらしく、MMEからバイナリ形式に変換した形式のFXNファイルを読み込めるらしいです。が、手元にDirectX SDKが導入されたWin PCがないのでMMEファイルをコンパイルできない…誰か試してみてどんな感じか教えてください……

ということでMacでもMMD動画が作れる時代なのでみなさんも作ってみてくださいね（？）

nanoemについて詳しいことは[nanoem のマニュアル · GitHub](https://gist.github.com/hkrn/d7c7b56911d3e1d60643)を確認してください。

ではまた