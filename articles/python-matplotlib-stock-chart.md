---
title: "株価のテクニカル分析をmatplotlibで！忘れやすいシグナルをチャート1枚で把握する！"
emoji: "📈"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["python", "matplotlib", "chart", "投資", "分析", "株"]
published: true
---

# 株の基本的な売買戦略
基本的にテクニカル分析重視で売買を行います。
そのため、下記のようなニーズに応えるべく、分析チャートを作りました。
- チャート上で現れるシグナルをつぶさに把握したい
- 煩雑にならないように銘柄毎に1枚で把握したい
- なんのシグナルだったか想起しやすいチャートがほしい
- シグナルの見落としを無くしたい

## 目的
これは株価を予測するものではなく、
売買判断の際にこのチャートを見ながら売買することで、
「最悪のタイミングで反対売買することを避ける」ことが目的です。

## テクニカル分析についての参考
テクニカル分析でのシグナルなどは下記の書籍から引用させていただきました。
詳しく知りたい方はリンクを貼っておきますのでこちらからどうぞ。
https://hack-note.com/


# 海運株のチャートで解説
個人的に、海運株のチャートがいちばん指標通りに動いているように見えるので、解説にはこの銘柄を使用します。
[![日本郵船（9101）](https://trident-capital-strage.s3.ap-northeast-1.amazonaws.com/charts/latest/9101.png =750x)*日本郵船（9101）*](https://trident-capital-strage.s3.ap-northeast-1.amazonaws.com/charts/latest/9101.png)

[![商船三井（9104）](https://trident-capital-strage.s3.ap-northeast-1.amazonaws.com/charts/latest/9104.png =750x)*商船三井（9104）*](https://trident-capital-strage.s3.ap-northeast-1.amazonaws.com/charts/latest/9104.png)

[![川崎汽船（9107）](https://trident-capital-strage.s3.ap-northeast-1.amazonaws.com/charts/latest/9107.png =750x)*川崎汽船（9107）*](https://trident-capital-strage.s3.ap-northeast-1.amazonaws.com/charts/latest/9107.png)

# 用語、シグナルの解説
- MA: 移動平均線
- GC: ゴールデンクロス
- DC: デッドクロス
- GC_5_20: 5日MAが20日MAをゴールデンクロス
- DC_5_20: 5日MAが20日MAをデッドクロス

# MAによるトレンドゾーンの考え方
売買の方針を考える上で前提となるトレンドをゾーン分けして一目で把握できるように背景色を変えて表示しています。
各ゾーンのは次のような内容です。

| 色 | 状況 | 判断 |
| -- | -- | -- |
| 薄青 | 下落 初期 | 様子見 |
| 青 | 下落 中期 | 売り |
| 濃青 | 下落 後期 | 利確 or 買い |

| 色 | 状況 | 判断 |
| -- | -- | -- |
| 薄赤 | 上昇 初期 | 様子見 |
| 赤 | 上昇 中期 | 買い |
| 濃赤 | 上昇 後期 | 利確 or 売り |

## データサイエンティストスクール 無料部分あります
PythonやRなどのプログラミングを学ぶなら、
さらに統計分野を学習してデータサイエンティストを目指すのがおすすめ！

ディープラーニングやビックデータ分析などの高額システム案件の受注にも有利になります。

システム開発より、分析がやりたい方向けですが、下記載せておきます。

https://hack-note.com/programming-schools/#toc17
 
