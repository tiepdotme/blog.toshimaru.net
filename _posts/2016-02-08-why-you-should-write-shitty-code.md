---
title: ひどいコードを書いてもよいとき
published: true
description: なぜひどいコードを書いてはいけないか - hitode909の日記 / ひどいコードを書いてもよいときとは？　ひどくないコードを書けるだけの技術力がない プロジェクトの生産期間が短い プロダクトの寿命が短い 将来アーキテクチャを作り直すことが決まっている 自分が近い将来退職する 技術的負債を残したい
tags: tech
---

[なぜひどいコードを書いてはいけないか - hitode909の日記](http://hitode909.hatenablog.com/entry/2016/02/08/140232)

ひどいコードを書いてもよいときとは:question:

- ひどくないコードを書けるだけの技術力がない
- プロジェクトの生産期間が短い
- プロダクトの寿命が短い
- 将来アーキテクチャを作り直すことが決まっている
- 自分が近い将来退職する
- 技術的負債を残したい

良いコード:innocent:と悪いコード:imp:の分別がつかないような**技術力の低い**新卒くんとかは好むと好まざるとにかかわらずひどいコードを書いてしまうときもある。担当メンターはきちんと彼らが良いコードを書けるように導いていかなければならない。

**プロジェクトの生産期間が短かったり、プロダクトの寿命が極端に短い** とわかっているものであればひどいコードを書いてもよい。:imp: ひどいコードとわかっていても時間が足りなければ直せないし、たとえ直したとしてもその成果はプロダクトの寿命と共に終わる。ただし長期的にメンテンナンスをしていくのであればこの限りではない。

言語選択とかフレームワーク選定とかデータベース設計とかアーキテクチャレベルで**作り直すことを将来想定しているのであれば**、ひどいコードを書いてもよい。:imp: かの有名なFacebookだって最初はひどいコードから始まってるんだ[^1]。そのコードを未来の優秀なエンジニアたちが塗り替えていって綺麗にしていったんだ。そうしてFacebookは大きくなり大成功を収めた。ビジネス :moneybag: を作るのに綺麗なコードは要らない。

あなたは近い将来**退職**することを目論んでいて現在の職場に少ならからずのヘイトを溜めている。さぁ復讐のときだ。技術的負債を目いっぱい残してやろう。:imp:

### 過去に書いた関連エントリ
* [メンテナンス性の高いコードを書く意義とは](/mentenability/)

[^1]: [Facebook PHP Source Code from August 2007](https://gist.github.com/nikcub/3833406)
