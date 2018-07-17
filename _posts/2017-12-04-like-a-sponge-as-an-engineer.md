---
layout: post
title: 技術者としてスポンジであり続けること　あるいは老害回避戦略の話
description: エンジニアリングとは常に学習し続けることである。僕がWeb技術者として生計を立てる上で大切にしているモットーだ。 ドッグイヤーな変化の激しいIT業界、変化に取り残されないためには常に学習が必要だ。今僕たちがデファクト・スタンダートとしている技術は一年後もスタンダートであり続けるだろうか？　一年くらいなら大丈夫？　じゃあ三年後は？　五年後は？ 十年後はどうだろう？ 自信をもって技術トレンドは今と変わっていないと言えるだろうか。
image: /images/posts/book/books.jpeg
tags: tech
---

## エンジニアリングとは常に学習し続けることである

エンジニアリングとは常に学習し続けることである。僕がWeb技術者として生計を立てる上で大切にしているモットーだ。

ドッグイヤーな変化の激しいIT業界、変化に取り残されないためには常に学習が必要だ。今僕たちがデファクト・スタンダートとしている技術は一年後もスタンダートであり続けるだろうか？　一年くらいなら大丈夫？　じゃあ三年後は？　五年後は？ 十年後はどうだろう？ 自信をもって技術トレンドは今と変わっていないと言えるだろうか。

## 変化する技術トレンド

Web業界の技術トレンド変化を見るにしてもその変化が激しいことは明らかだ。古くは掲示板を動かしていたPerl CGIの時代から、最強のPHP製CMS・Wordpress、継続的にバージョンアップを重ね進化を続けるWebアプリケーションフレームワーク・Ruby on Rails…。近年だとサーバーサイドJavaScirpt・Node.js、Erlang VM上で動くRubyライクなシンタックスを持つElixir、Twitterでも運用実績を持つScala、Googleが作った爆速言語Go、Mozillaの開発したRustなどもよく聞く。お硬い感じなところだとJavaのSpring Frameworkであったり（最近はKotlin対応もしたと聞く）オープンソース化もされているMicrosoftの.NETなど。

サーバーサイド技術だけじゃなく、フロントエンド技術の変化も大きい。HTMLはHTML5になり、CSSはCSS3になってWebでリッチな表現が可能になった。貧弱な言語であったJavaScriptはES6(ES2015),ES7(ES2016)へと進化し言語として洗練されてきている（Bebelなどのトランスパイラーの進化の力も大きい）。便利な関数群を多く含みブラウザ間の挙動の差異を吸収してくれるjQueryはそこそこ長い間フロントエンドのデファクト・ライブラリだったが、フロントエンドコードの複雑化・巨大化に伴いその座をReactやAngularへと譲りつつある（React/Angularにたどり着くまでの紆余曲折はここでは省略）。

開発ワークフローもずいぶん進化した。開発者にとって一番大きかったのはGitHubの台頭だ。OSSを加速度的に推し進めエンジニアリング業界にソーシャルコーディングという概念を普及させた。これによりVCSはGitを利用しRemoteにはGithub（あるいはGithubライクなプロダクト）を使うのが当たり前となった。

テストももちろん書く。テストを書くと次はCIがしたくなる。Jenkins？ 今ならTravisCI、CircleCIなどのCIサービス使ったほうが良さそうだ。

アプリケーションのデプロイ先となるインフラはどうだ。オンプレ？ いや、今はクラウドの時代だ。IaaS業者ならAWS（Amazon Web Service）か。いや、GCP（Google Cloud Platform）も最近頑張っているようだ。そこまでインフラ面倒見る余裕なんてない？ならばHerokuなどのPaaSを選択することもできる。

モバイルアプリ開発はどうだろう？ iOS？ Objective-Cじゃなくて今はSwiftなんだっけ。Android？ 古き良きJava…ではなく最近はKotlinで書けるらしい。最近はReact Nativeという技術もあるらしい。Reactに慣れたWeb開発者にとって取っ付きやすそうだ。

## 我々は学習し続けられるか？

Web技術に限定してザッと思いつくだけ列挙してもこれだけあるのだ。これでもなお「１つの技術だけで今後も戦い続けることができる！」と自信を持って言えるだろうか。

あなたは言う。いいや、俺はこの技術一筋で勝負するんだ！なるほど、けっこうけっこう。あなたが変わらなくても世界は変わる。世界はあなたを待ってはくれない[^1]。

学習を止めた時から変化の波に取り残され、気付いた頃にはもう手遅れ…、そんな事態は避けなければならない。

では問おう。**我々は学習し続けられるのか？**

## 学習の壁

我々に立ちはだかる学習の壁。この学習の壁を乗り越える続けることは難しい。

そしてこれは歳を重ねれば重ねるほどに難しくなっていく。一般的に記憶力や集中力は年齢とともに衰えていくと言われるからだ[^2]。

一方で学習能力は年齢とは関係ないとする説もある[^3]。記憶力そのものに年齢は関係なく、老化とともに記憶力が低下したと感じる理由は＜学習意欲の低下＞に起因しているとする説だ。

僕の考えとしては前者の説も後者の説もどちらも支持したい。我々の学習能力は年齢とともに衰えていくし、学習意欲もまた年齢とともに低下する。

## スポンジであるということ

では我々はこれにどう抗ったらよいだろうか？　

前者の年齢とともに不可避的に衰える能力は仕方がないにせよ、せめて後者の学習意欲は高く保ち続けようではないか。新しいものを進んで吸収できるスポンジであろう。弾力を失ってはいけない。柔軟にしなやかであろう。硬直化する脳に抗おう。

スポンジであるということ。これによって学習という困難も楽しみとして享受できるようになるのではないだろうか。

## 老害になってはいないか

学習し続ける姿勢、これは老害化するのを防ぐ上でも大切な心がけだと思う。

そもそも老害とはどういう人なのか？ 僕が思う老害とは下記の通りだ。

老害とは自分の過去の栄光や成功体験を元にして自分の価値観ややり方を周囲（主に若者がターゲットにされやすい）に押し付けるような人のこと。その結果、チーム/個人のパフォーマンスを低下させる。

こういうタイプの人は過去の成功を根拠としてロジックを展開するので、その成功が現代では通用しない時代錯誤なものであったとしても気にせず押し通そうとする。そして新しいことに関しては「よくわからない」などと言って斬り捨てる。

そんな老害にはなりたくないと思う。きっとこの文章を読んでいるあなたもそうだろう。だがあなたは **自分が老害になっていないとハッキリ言えるだろうか？**

一般的に、歳を取ると価値観は固まっていき保守的になってゆく。あなたは自分の気づかないレベルで無意識に新しいことを拒絶していないだろうか。自分の考えを無意識に他者に押し付けてはいないだろうか。職場で気づいたら老害になってはいないだろうか。

## 老害回避戦略

エンジニアとして老害にならないための僕なりの老害回避戦略を考えてみたのでまとめてみる。

### マサカリを投げるな

技術的な厳しい指摘をよく「マサカリを投げる」と表現したりするが[^4]、マサカリを投げるのは止めよう。

そのマサカリが本当に意味のあるものか今一度考えてみよう。あなたの飛ばしたマサカリは周囲を萎縮させチームの空気を悪くしパフォーマンスを下げている可能性が高い。

あなたがどんなに優れたエンジニアだとしてもそれをマサカリという形で誇示する必要は無い。あなたの優秀さはマサカリではなくコードで示せるはずだ。

剣ではなく弁を。攻撃ではなく教育を。

### 技術に素直でいよう

コンピュータの内部が0か1のバイナリで構成されているの同様に、プログラミングという行為も0か1のように正誤がハッキリするものが多いように感じる。

バグがある挙動、バグが無い挙動であればバグが無い挙動が正しいし、速いコードと遅いコードであれば速いコードが良いし、DRYなコード、そうじゃないコードがあればDRYなコードを選択すべきだし、テストがないコードよりもテストがあるコードが信頼性は高い。

老害であれば技術的正しさを無視して自説を展開するかもしれないが、それではダメだ。常に技術的に正しい世界を目指そう。技術にたいして素直でいよう。

<blockquote class="twitter-tweet" data-lang="en"><p lang="ja" dir="ltr">個人開発は遊びでいいけど仕事における開発は遊びじゃない。技術的/仕様的正しさは常に追求すべきだしデータ的正しさは検証すべきだしプログラムにはバグが無いように（テストコード書くなどして）努力すべきだし自分のコードにはオーナーシップを持つべきだ。</p>&mdash; toshimaru (@toshimaru_e) <a href="https://twitter.com/toshimaru_e/status/995968055342649344?ref_src=twsrc%5Etfw">May 14, 2018</a></blockquote>

僕たちが持っている知識は変化する技術の流れの中で明日には変わっているかもしれない。今に凝り固まるのではなく、常に技術的正しさを求めて学習しよう。

### フラットでいよう

GitHubのOSSコミュニティで人種・性別・年齢関係なくコラボレーションするように、我々も技術の文脈においてフラットなコミュニケーションを目指そう。

この世界、どんなに自分より歳をとっていてもかなわないなというエンジニアもいるし、逆に自分よりずっと若くても優秀なエンジニアはたくさんいる。「俺の方が人生経験が長いから」「私の方が年齢が高いから」という理由では奢れない（もしそんな理由でエラそうにしているのであればそれは老害だ）。

実際のところ、先輩後輩・上下関係を重んじる日本社会においてこれを実現するのは容易ではないわけだが、技術コミュニケーションにおいてできるだけフラットなコミュニケーションを心がけよう。この姿勢は前述の<技術に素直でいる>ことにも繋がることだと思う。

### 次の世代を育てる

老害でないということは同時に若手とうまく付き合うということでもある。今まで述べてきたような老害的な態度を取らなければ、若手が伸び伸びと働ける職場環境にできるのではないだろうか。

次の世代を育てよう。そして彼らが伸び伸びと活躍できるような雰囲気作りを目指そう。

こんなことを言うとたまに「若手に自分のポジションを脅かせれる」「自分の仕事が奪われる」と言って拒否反応を示す人をたまに見かける。その考え方も分からなくはないが、僕はそれは自己保身的で一面的な考え方だと感じる。

次の世代を育てることで得られるメリットは数多くあると思う。

- 次の世代を育てる過程で自分も育つ: 育てている過程の中で自分もちゃんと理解できていなかった部分が理解できるようになったり、自分の理解が深まる
- 次の世代が育つことでチームひいては会社の生産性が高まり自分自身の仕事が相対的に減る
- 次の世代が育つと自分一人ではできなかったことが出来るようになるかもしれない: 切磋琢磨出来る仲間が増えるとチームとしてもう一段上のレベルへと上がり、一人では思いつかなかったアイディアやソリューションが発案されるかもしれない

自分の立場ばかり考える保身的な老害にはならないようにしよう。どんどん次の世代を育てていき、次の世代とともにステップアップを目指そう。

## 「35歳定年説」は嘘

[35歳定年説](https://tech-camp.in/note/engineer/30204/)的な言説を技術界隈で聞くことがある。

この35歳の35の数字の部分は38でも40でもなんだって良いのだが、僕は基本的にこのn歳定年説は間違っていると思う。

これを反証することは簡単で、40歳でバリバリ現役でコードを書き続けている技術者を見つければ良い。僕は40歳でバリバリ前線で頑張っている技術者を知っている。なのでこの説は間違っているとハッキリ言える。

思うに、**コードを書かず学習意欲を失ってしまった35歳のおじさんたちが自分がコードが書けないこと・学ばないことの言い訳として言い出し始めたのがこの「35歳定年説」の真実じゃないだろうか。** 20歳の技術者は35歳定年説なんて言い出さない。それを言い出すのは35を過ぎて自身のパフォーマンスが出なくなったと感じている技術者たちだけだ。もし本当にそんな理由で言っているのであればハッキリ言ってダサすぎだと思う。

年齢を言い訳にするのは止めよう。学習するのに遅すぎるなんてことはないはずだ。

> You're never too old to learn

## 最後に

この文章は僕自身が若手とは言えない年齢となり今後シニアな立場へとなっていく中で「自分は老害化していくのではないか」という危機感から自戒も込めて書いたものである。願わくば五年後十年後自分がここに書いたような老害になっていないことを祈る。

[^1]: もちろん１つのことに特化して高度な専門性を武器に戦っている技術者もいる。しかしトレンドは常に追っているべきだ。なぜならブレークスルーが起こってその技術が死んだときに自分の食い扶持がなくなるからだ（それでもすぐにその技術がなくなるわけではないのでその技術を使う古い現場で細々と食い扶持を得るのも戦略としてありえるが）。
[^2]: [集中力は43歳！ 人間の脳のピーク年齢は、能力ごとに違っていた \| BUSINESS INSIDER JAPAN](https://www.businessinsider.jp/post-100550)
[^3]: [「加齢で記憶力が低下」は誤解 知能も低下せず、問題は前頭葉老化 \| 東洋経済ONLINE \| 福井新聞ONLINE](http://www.fukuishimbun.co.jp/articles/-/62618)
[^4]: [マサカリの起源について - Qiita](https://qiita.com/kaityo256/items/d7d8f7a0e522895c8f5d)