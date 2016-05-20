---
layout: post
title: MacでMMDを動かす
---

だいぶ久しぶりの更新になってしまいましたね…

昔UbuntuとOneDriveでファイルを同期するやつの[記事](./OneDrive-Ubuntu/)を書いたんですが[OneDriveの容量が縮小されたりする](http://pc.watch.impress.co.jp/docs/news/20151104_728819.html)らしいので利用している人は気をつけてください。一応データは1年位大丈夫らしいんですが。

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

