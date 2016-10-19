---
layout: page
title: 岡山県立大学・プログラミング言語II(計算機言語I)実施記録
---
岡山県立大学情報工学部情報通信工学科で2012年度まで実施していた講義「プログラミング言語II」
(旧名称：「計算機言語I」)の実施記録です。

## 講義のコンセプトと経緯

着任前から担当することが決まっていた講義の一つで、何かのプログラミング言語に関する講義、ということまでは
決まっていました。ただし、どのプログラミング言語を選ぶかは任されていました。で、実験その他でCを、
「[計算機言語II](/opu-computer-language-ii/)」でJavaを取り上げているので、それ以外で、という
ことで、選んだのがStandard MLでした。

それほど深く考えていたわけではありません。手続き型言語(C)とオブジェクト指向型言語(Java)をやっているから、
関数型か論理型なんだけど、どっちかといったら関数型かなあ。関数型だとLisp系がまず浮かぶけど、かっこが
たくさんあると学生さんにはわかりにくいかなあ。じゃ、学生時代から憧れのあったStandard MLにするかな。
これくらいの考えでした。

けれど、この選択が結果的に正しかった。やり始めてすぐに、再帰を教える道具として非常に優れているということが
わかってきました。パターンや高階関数といった、プログラミング言語のモダンな機能を紹介するのにも適している。
インタプリタ型なので、学生自身にパソコンで動かしてみさせることもしやすい。何より自分自身、Standard ML
という言語が好きになりましたし、再帰も非常に深く理解するようになりました。

Ullmanの書いた優れた入門書があったのも大きかったです。Ullmanはデータ工学分野の著名な研究者ですが、本人
が前書きで書いている通り、Standard MLについては素人です。でもそれが逆によくて、理論に踏み込み過ぎず、
かといって単なる入門書でもない、情報工学の教科書としては絶妙な難易度になっています。これがなかったら、
正直、講義が成功していたかはわかりません。

途中からは、ちょうど同時期にC言語の実験を担当することになりまして、こちらでもリストや2分木といったデータ構造
を扱うプログラミングをさせました。つまり、再帰という、プログラミングにおいて重要な概念を、Standard MLという
優れた道具による講義と、C言語による実践とを同時並行的に教える、ということができたのです。偶然とはいえ、
かなり理想的な教育ができたと思っています。

ソフトウェア開発者としても教育人としても、この講義、そしてStandard MLという言語から学んだことは大きかったです。

## 関連ブログ投稿

- [今期の講義振り返り: Standard MLの講義、今年度で終了](https://knsm.net/%E4%BB%8A%E6%9C%9F%E3%81%AE%E8%AC%9B%E7%BE%A9%E6%8C%AF%E3%82%8A%E8%BF%94%E3%82%8A-standard-ml%E3%81%AE%E8%AC%9B%E7%BE%A9-%E4%BB%8A%E5%B9%B4%E5%BA%A6%E3%81%A7%E7%B5%82%E4%BA%86-d33b74ad2d0b#.cnq84awwv)

## プログラムコード

講義の実施にあたり[作成したStandard MLのプログラム](https://github.com/kunishi/standard-ml-toy-programs)をGitHubで公開しています。

## 平成22年度シラバスより

### 概略

リスト処理、再帰、型など、計算機工学において重要なソフトウェア技術について、型付き関数型プログラミング言語 ML によるプログラムを用いて解説する。また、高階関数、多相など、C 言語にはないが現代のプログラミング言語において重要な考え方についても解説する。

### 授業の到達目標

以下の 2 点を理解することを目標とする。(1) リスト、木などの再帰的データ構造と、それを対象とする再帰的 アルゴリズム (2) プログラミング言語の動作モデル、型、高階関数、多相など、ソフトウェアの基礎概念。具体 的な目安としては次の 2 点が目標となる。(1) 実際にアルゴリズムを設計し、ML でプログラムを記述できるよ うになること (2) 講義で扱った範囲内で任意のプログラムの動作や型などの説明ができること

### 教材

参考書として以下の書籍を用いました。

- Jeffrey D.Ullman, *Elements of ML Programming (ML97 Edition)*, Prentice-Hall, 1998.

## 講義メモ

おおむね以下の順序に従って講義を進めました。

1. [導入](https://drive.google.com/open?id=15QzIetAY_2X5wVH10nBuuSEtFFbvgymnxkMTYtevl_k)
1. [式、型](https://drive.google.com/open?id=1RbHZvSOabL711SGnfA2A76pA30siWtrBZq3Zd3J002w)
1. [変数、環境](https://drive.google.com/open?id=12WNVSYWIEWl6aRafdMWz7WxJM9FQtzqEwg3HbfDgYDo)
1. [組、リスト](https://drive.google.com/open?id=1_wOhzPiNUJVA10wemCLs1Km-GfltR_HUuzkzHXVd4cY)
1. [関数](https://drive.google.com/open?id=1e9JszYVUO-OiKCHZr2J8_OIJXwMpxmXVDghJEZBCSl4)
1. [再帰関数](https://drive.google.com/open?id=1KBhfG0OptR6L3WEvK-apmzu-3U1pHbYlddvWp3pRRv4)
1. [パターン](https://drive.google.com/open?id=133QK_JH2GT0_MrkRJEX3fve50XfuLnHN_-IblfwZIIg)
1. [局所変数](https://drive.google.com/open?id=1FlpMSf1Yjy7UzFqknOS_bWZYhWI5J1Dyqh3uHLRvcFU)
1. [高階関数](https://drive.google.com/open?id=1vz1jQYe1r_ZbKBYQL4Yh2_ls51NJQYileLyxA3gy5xU)
1. [多相関数](https://drive.google.com/open?id=107QGhbu6YQJCImMzgaeJ4djcPT6WPuOJJJStnHK1Pik)
1. [線形時間のreverse](https://drive.google.com/open?id=1Rtitoy-QpdWmOdwP98RxB3Q5G3h11KgiIo9JovLgMjQ)
1. [新しい型を定義する](https://drive.google.com/open?id=1XOxwBHI8vJlXpPXzO_Ltga6S8TMWdXT4lZnhry8evhk)

## 定期試験問題

- [1999年度(2000年2月実施)](opu-computer-language-i-exam-2000.pdf)
- [2000年度(2001年2月実施)](opu-computer-language-i-exam-2001.pdf)
- [2001年度(2002年2月実施)](opu-computer-language-i-exam-2002.pdf)
- [2002年度(2003年2月実施)](opu-computer-language-i-exam-2003.pdf)
- [2003年度(2004年2月実施)](opu-computer-language-i-exam-2004.pdf)
- [2004年度(2005年2月実施)](opu-computer-language-i-exam-2005.pdf)
- [2005年度(2006年2月実施)](opu-computer-language-i-exam-2006.pdf)
- [2006年度(2007年2月実施)](opu-computer-language-i-exam-2007.pdf)
- [2007年度(2008年2月実施)](opu-computer-language-i-exam-2008.pdf)
- [2008年度(2009年2月実施)](opu-programming-language-ii-exam-2009.pdf)
- [2009年度(2010年2月実施)](opu-programming-language-ii-exam-2010.pdf)
- [2010年度(2011年2月実施)](opu-programming-language-ii-exam-2011.pdf)
- [2011年度(2012年2月実施)](opu-programming-language-ii-exam-2012.pdf)
