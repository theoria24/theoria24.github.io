---
layout: post
title: AnonymousPostの解説
categories:
  - technology
tags:
  - Tech
  - Ruby
  - mastodon
redirect_from:
  - /anonymouspost-update/
---

利用規約は[こちら](https://theoria24.github.io/anonymouspost-agreement/){:target="_blank"}にあります。

こんにちは．クソbot製作者のておりあです．

本日 [@AnonymousPost@theboss.tech](https://theboss.tech/@AnonymousPost){:target="_blank"} をアップデートしたのでその話を書いておこうというわけです．

### そもそも
AnonymousPostの仕様がどこにもまとまっていないので，書きます．

### 通常の匿名トゥート
```
@AnonymousPost ほにゃらら
```

という形式で ***DM*** を送ると，@AnonymousPostが『ほにゃらら』とトゥートします．このとき， `@AnonymousPost` は `@anonymouspost` や `@AnonymousPost@theboss.tech` でも構いません（AnonymousPost側で受信できる形式であれば）．

トゥートの先頭の `@AnonymousPost ` を削除する設定になっています．`@AnonymousPost` という文字列を残したい場合には，先頭以外に `@AnonymousPost` を入れてください．（ `@AnonymousPost ` を削除したい場合には，先頭以外に入れないでください．）

匿名Fav，BT機能（後述）を利用する場合以外には，トゥートの先頭に `@AnonymousPost fav ` および `@AnonymousPost bt ` を使用することはできません．大文字，小文字の区別はありません．

[theboss.tech](https://theboss.tech){:target="_blank"} の仕様により，ハッシュタグを含まない匿名トゥートの末尾には `#theboss_tech` というハッシュタグが挿入されます．これを挿入されたくない場合，なんらかのハッシュタグを使用する必要があります． `#AnonymousPost` などで良いと思います．  
逆に，本文中に他のハッシュタグを使用すると `#theboss_tech` は挿入されません． `#theboss_tech` を他のハッシュタグと同時に使用したい場合，@AnonymousPostへ送信するDMの本文にあらかじめ `#theboss_tech` を含めておく必要があります．

theboss.tech内のユーザーに対しては，@AnonymousPost経由でリプライを送信することができます．しかし，DMを送信する際に，送信先ユーザーのアカウント名を含む必要があり，送信先の相手に送信元ユーザーが伝わってしまうため，実用的でありません．

### 匿名BT，Fav
[本日のアップデート](https://github.com/theoria24/AnonymousPost4Mstdn/pull/4){:target="_blank"}で追加された機能です．

```
@AnonymousPost bt https://example.com/@example/123456789012345678
```

のような ***DM*** を送ることで，@AnonymousPostでブーストすることができます．

また，
```
@AnonymousPost fav https://example.com/@example/123456789012345678
```

のような ***DM*** を送ることで，@AnonymousPostでお気に入り登録をすることができます．<small>お前を見ているぞ的な使い方が可能です．</small>

上記のいずれも，大文字小文字の区別はありません（ `bt` は `BT` ， `Bt` などでも構わないということ）． `@AnonymousPost` と `bt` または `fav` ， `URL` は半角スペースで区切る必要があります．URLはmastodonの `/api/v1/search` が認識できる形式で記入します（Web UIの検索欄に入力することで認識可能な形式か確認できます）．mastodonが認識できるものであればpleromaなどの連合を構成するアプリケーションの投稿も利用できるはずです．

また，対象のトゥートは半角スペースで区切って複数指定することも可能です．例えば，
```
@AnonymousPost bt https://example.com/@example/123456789012345678 https://mstdn.example.jp/@user1/100000000000000000 https://pleroma.example.org/objects/12345678-90ab-cdef-1234-567890abcdef https://peertube.example.com/videos/watch/12345678-90ab-cdef-1234-567890abcdef 
```
とすることで4つの投稿を指定できます．

### その他
わからないことがあれば [@theoria@theboss.tech](https://theboss.tech/@theoria){:target="_blank"} にお尋ねください．要望などもここに送ってください．[GitHub](https://github.com/theoria24/AnonymousPost4Mstdn){:target="_blank"} にissueなど立てていただいてもかまいません．プルリクもお待ちしております．
