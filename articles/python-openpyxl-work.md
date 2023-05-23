---
title: "Python初心者のためのopenpyxlの使い方"
emoji: "💻"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Python", "openpyxl"]
published: true
---

:::message alert
本記事は、Python初心者向けに作成されており、基本的な機能にフォーカスしています。上級者の方にはあまり参考にならない場合があります。
:::

## はじめに
こんにちは。今回は、Python初心者に向けて、Excelファイルを操作するためのライブラリである「openpyxl」について解説します。
Excelファイルは、ビジネスなどで頻繁に利用されるデータ形式の一つです。Pythonでも、Excelファイルを操作することができる「openpyxl」というライブラリがあります。このライブラリを利用することで、PythonでExcelファイルの読み込みや編集ができます。

以下では、実際のコード例を交えて、openpyxlの使い方について解説していきます。

## Excelファイルの読み込み

openpyxlを使って、Excelファイルを読み込むには、まずはライブラリをインストールする必要があります。以下のコマンドを使って、インストールしてください。

```bash
pip install openpyxl
```

Excelファイルを読み込む場合は、以下のようにコードを書きます。

```python
import openpyxl

# Excelファイルを開く
wb = openpyxl.load_workbook('sample.xlsx')

# シートを選択する
ws = wb['Sheet1']

# 1行目の1列目から値を取得する
cell = ws.cell(row=1, column=1)
print(cell.value)
```

上記のコードでは、「sample.xlsx」というファイルを開いて、Sheet1を選択しています。そして、1行目の1列目のセルの値を取得して、出力しています。

:::message
Excelファイルを開く際には、ファイル名を指定する必要があります。また、シートを選択する際には、シート名を指定するか、シートのインデックスを指定することができます。
:::

## Excelファイルの書き込み

Excelファイルにデータを書き込む場合は、以下のようにコードを書きます。

```python
import openpyxl

# Excelファイルを開く
wb = openpyxl.load_workbook('sample.xlsx')

# シートを選択する
ws = wb['Sheet1']

# 2行目の1列目に値を書き込む
ws.cell(row=2, column=1, value='Hello, World!')

# Excelファイルを保存する
wb.save('sample.xlsx')
```

上記のコードでは、「Hello, World!」という文字列を2行目の1列目に書き込んでいます。そして、Excelファイルを保存しています。

:::message
Excelファイルを保存する際には、ファイル名を指定する必要があります。また、セルに値を書き込む際には、行番号、列番号、値を指定する必要があります。
:::

## まとめ

PythonでExcelファイルを操作するためには、openpyxlというライブラリを使うことができます。Excelファイルを読み込む際には「load_workbook」を使い、Excelファイルを保存する際には「save」を使います。また、セルに値を書き込む際には、行番号、列番号、値を指定する必要があります。

以上が、Python初心者のためのopenpyxlの使い方についての解説でした。Excelファイルの操作が必要になった際には、ぜひこの記事を参考にしてみてください。

## データサイエンティストスクール 無料部分あります
PythonやRなどのプログラミングを学ぶなら、
さらに統計分野を学習してデータサイエンティストを目指すのがおすすめ！

ディープラーニングやビックデータ分析などの高額システム案件の受注にも有利になります。

システム開発より、分析がやりたい方向けですが、下記載せておきます。

https://hack-note.com/programming-schools/#toc17

