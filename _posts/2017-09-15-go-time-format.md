---
layout: post
title: Goの日付フォーマット 〜＜2006年1月2日＞の謎〜
description: Goの現在時刻はtime.Now()で取得することができるがフォーマットされた現在日時はどのように取得すればよいだろうか？　Format()の引数として与えられる 2006年1月2日 はどうして2006年1月2日なのだろうか？　2001年2月3日でもダメだし1234年5月6日でもダメだ。きっちり 2006年1月2日 でなければならない。
tags: go
last_modified_at: 2019-12-07
toc: true
image: "/images/posts/go-time-format.png"
---

Goの現在時刻は `time.Now()` で取得することができるが、フォーマットされた現在日時はどのように取得すればよいのだろうか？

## 今日の日付の取得

```go
package main

import (
	"fmt"
	"time"
)

func main() {
	// フォーマットなし現在時刻
	fmt.Println(time.Now())
	// フォーマットあり現在時刻
	fmt.Println(time.Now().Format("2006年01月02日"))
}
```

これで今日の日付を取得することができる。

```
2009-11-10 23:00:00 +0000 UTC m=+0.000000001
2009年11月10日
```

## 2006年1月2日の謎

しかしここで１つの疑問が残る。`Format()`の引数として与えられる `2006年01月02日` はどうして2006年1月2日なのだろうか？　2001年2月3日でもダメだし1234年5月6日でもダメだ。きっちり **2006年1月2日** でなければならない。

この理由については下記の記事で解説されている。

> では一体この2006年1月2日という特別な日は、なんの日なのか？
>
> （...中略...）
>
> 答えは単純だ。これはアメリカ式の時刻の順番なのだ。"1月2日午後3時4分5秒2006年"（つまり「自然な順番」で1, 2, 3, 4, 5, 6）を指しているのである。

via. [Goのtimeパッケージのリファレンスタイム（2006年1月2日）は何の日？ - Qiita](http://qiita.com/ruiu/items/5936b4c3bd6eb487c182)

考えてみるとなんてことはない、**アメリカ式の日時の表示順番でのインクリメンタルな自然数であった！**

## Goの内部実装を覗いてみる

もう少し深く理解するために、Goでどのように実装されているかを覗いてみる。それぞれの`const`がどの数値とマッピングするかがコメントで示されている。

```go
const (
	_                        = iota
	stdLongMonth             = iota + stdNeedDate  // "January"
	stdMonth                                       // "Jan"
	stdNumMonth                                    // "1"
	stdZeroMonth                                   // "01"
	stdLongWeekDay                                 // "Monday"
	stdWeekDay                                     // "Mon"
	stdDay                                         // "2"
	stdUnderDay                                    // "_2"
	stdZeroDay                                     // "02"
	stdHour                  = iota + stdNeedClock // "15"
	stdHour12                                      // "3"
	stdZeroHour12                                  // "03"
	stdMinute                                      // "4"
	stdZeroMinute                                  // "04"
	stdSecond                                      // "5"
	stdZeroSecond                                  // "05"
	stdLongYear              = iota + stdNeedDate  // "2006"
	stdYear                                        // "06"
	stdPM                    = iota + stdNeedClock // "PM"
	stdpm                                          // "pm"
	stdTZ                    = iota                // "MST"
	stdISO8601TZ                                   // "Z0700"  // prints Z for UTC
	stdISO8601SecondsTZ                            // "Z070000"
	stdISO8601ShortTZ                              // "Z07"
	stdISO8601ColonTZ                              // "Z07:00" // prints Z for UTC
	stdISO8601ColonSecondsTZ                       // "Z07:00:00"
	stdNumTZ                                       // "-0700"  // always numeric
	stdNumSecondsTz                                // "-070000"
	stdNumShortTZ                                  // "-07"    // always numeric
	stdNumColonTZ                                  // "-07:00" // always numeric
	stdNumColonSecondsTZ                           // "-07:00:00"
	stdFracSecond0                                 // ".0", ".00", ... , trailing zeros included
	stdFracSecond9                                 // ".9", ".99", ..., trailing zeros omitted

	stdNeedDate  = 1 << 8             // need month, day, year
	stdNeedClock = 2 << 8             // need hour, minute, second
	stdArgShift  = 16                 // extra argument in high bits, above low stdArgShift
	stdMask      = 1<<stdArgShift - 1 // mask out argument
)
```

via. [go/format.go at master · golang/go](https://github.com/golang/go/blob/master/src/time/format.go)

この実装をみると `2006-01-02` は `{stdLongYear}-{stdZeroMonth}-{stdZeroDay}` であることがわかる。

## Goの標準日付フォーマット

RFCなどの標準的な時刻フォーマットは、Goが標準で用意してくれている。

```go
const (
	ANSIC       = "Mon Jan _2 15:04:05 2006"
	UnixDate    = "Mon Jan _2 15:04:05 MST 2006"
	RubyDate    = "Mon Jan 02 15:04:05 -0700 2006"
	RFC822      = "02 Jan 06 15:04 MST"
	RFC822Z     = "02 Jan 06 15:04 -0700" // RFC822 with numeric zone
	RFC850      = "Monday, 02-Jan-06 15:04:05 MST"
	RFC1123     = "Mon, 02 Jan 2006 15:04:05 MST"
	RFC1123Z    = "Mon, 02 Jan 2006 15:04:05 -0700" // RFC1123 with numeric zone
	RFC3339     = "2006-01-02T15:04:05Z07:00"
	RFC3339Nano = "2006-01-02T15:04:05.999999999Z07:00"
	Kitchen     = "3:04PM"
	// Handy time stamps.
	Stamp      = "Jan _2 15:04:05"
	StampMilli = "Jan _2 15:04:05.000"
	StampMicro = "Jan _2 15:04:05.000000"
	StampNano  = "Jan _2 15:04:05.000000000"
)
```

これを使って下記のように書くことができる。

```go
package main

import (
	"fmt"
	"time"
)

func main() {
	fmt.Println(time.Now().Format(time.RFC822Z))
}
```

RFC822Z の形式で下記のように出力される。

```
10 Nov 09 23:00 +0000
```
