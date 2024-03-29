---
title: "【基礎】AWS FSxとは！？クラウドストレージの料金比較"
emoji: "🖥"
type: "tech"
topics: ["aws", "fsx", "料金", "比較"]
published: true
---

こんにちは。今回は、awsについて初心者エンジニアに向けて、aws fsxについて解説していきます。aws fsxとは何か、どのような用途に向いているのか、また類似サービスとの料金比較を行い、おすすめのサービスについてもご紹介します。

## aws fsxとは？

aws fsxは、awsのクラウドストレージサービスの1つです。fsxは「file server」という意味で、主にwindowsやlinuxのファイル共有ニーズに対応しています。具体的には、以下のような機能があります。

- windows用のfsx for windows file server
- lustre用のfsx for lustre

ファイル共有を行うために必要な機能が豊富であり、スケーラブルなストレージ容量を提供しています。データの耐久性も高く、高性能なストレージを必要とするアプリケーションや大容量のファイルを扱う場合に最適です。

## aws fsxとworkdocsの違い

aws fsxと似たような機能を持つサービスとして、amazon workdocsがあります。workdocsもクラウドストレージサービスで、共有機能がありますが、fsxとの違いは以下のようになります。

- workdocsはドキュメント編集が可能であり、fsxはドキュメントの共有専用
- workdocsはローカルでのファイル編集時に同期が必要
- workdocsはストレージ容量が限られているが、fsxはスケーラブル

要するに、workdocsはファイル共有だけでなく編集もできるサービスですが、fsxはファイル共有専用で、ストレージ容量が大きくスケールアウトが容易といった特徴があります。

## aws fsxと類似サービスの料金比較

aws fsxと似たような機能を持つ他のサービスとしては、以下のものがあります。

- microsoft azure file
- google cloud filestore

それでは、これらのサービスとaws fsxの料金を比較してみましょう。

| サービス名 | ストレージ容量(gb)/月 | 費用(usd)/月 |
| --- | --- | --- |
| aws fsx | 2,000 | $2,328 |
| microsoft azure file | 10,240 | $2,873 |
| google cloud filestore | 1,000 | $900 |

※上記料金は、2022年9月時点のものです。詳細については各社公式ページでご確認ください。

上記の表からわかる通り、ストレージ容量2,000gb/月で比較した場合、aws fsxが最も高価で、google cloud filestoreが最も安価です。ただし、ストレージ容量によって異なるため、利用する際には各社公式ページで料金シミュレーションを行うことをおすすめします。

:::message alert
※料金表はあくまでも各社公式ページで確認していただくようにお願いします。期間限定のキャンペーンもあるため、常に変動している可能性があります。
:::

## 比較結果からおススメは？

ストレージ容量や料金面、利用用途によってオススメのサービスは異なるため一概には言えませんが、以下のような点からaws fsxをおすすめします。

- スケーラブルなストレージ容量を提供しており、今後の拡張性を考慮したい場合に最適
- 高い耐久性とソリッドステートドライブ(ssd)を採用しており、高品質なストレージが必要な場合に最適

ただし、awsの操作に慣れていない場合や、ファイルの編集機能を求めるなど、他のサービスを利用する方が良い場合もあります。それぞれのサービスの特徴を把握し、利用用途に合わせてサービスを選択することが大切です。

以上が、aws fsxについての解説と比較結果になります。サービス選択に迷った場合は、今回ご紹介したサービス以外にも様々なクラウドストレージサービスがありますので、どのサービスが自分にとって最適か考えてみてください。

## AWSをさらに学ぶにはこちらもおススメ
https://hack-note.com/programming-schools/

## 参考記事

- [aws fsx、複数azにおいてnfsストレージファイルの持続的な利用を可能に](https://enterprisezine.jp/news/detail/12165)
- [azure file storage とは？その概要、使い方、メリット・デメリットについて紹介します！](https://www.publickey1.jp/blog/20/azure_file_storage.html)
