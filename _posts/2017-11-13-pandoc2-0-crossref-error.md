---
layout: post
title: Homebrewで入るpandoc 2.0とpandoc-crossrefを組み合わせるとエラーになる
categories:
  - technology
tags:
  - pandoc
  - pandoc-crossref
  - Tech
---

MacOS上で[Homebrew](https://brew.sh/){:target="_blank"}でインストールした[Pandoc](https://pandoc.org/){:target="_blank"}を使っているが、最近Pandocが2.0にアップデートされたので、特に深く考えずに```brew upgrade```したところ図表番号を管理するために使っていた[pandoc-crossref](https://github.com/lierdakil/pandoc-crossref){:target="_blank"}が動かなくなってしまった。

数日後にpandoc-crossrefにもアップデートが来ていたのでこれで動くだろうと思ってアップデートするも動かず。pandoc-crossrefは **v0.2.7.0** にアップデートされましたが、pandoc-crossrefのGitHubを見ると```Pandoc 2.0 support```となっているのは **v0.3.0.0-beta** から。

なので、pandoc-crossrefの開発版を入れることにした（Pandocのバージョンを戻せば良いのだが、homebrewでバージョンを戻すのが多少面倒くさくて開発版を入れたほうが早い！となった）。

### 方法

```--devel``` をつけて更新すれば良いです。

   brew update
   brew upgrade --devel pandoc-crossref

なんかすごい時間かかった（今までcabalとか使ってなかったのか）

なぜかリンクが貼られず実行できなかったので

   brew link pandoc-crossref

として完了。

## さあレポートを書こう！
