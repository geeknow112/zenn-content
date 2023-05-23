---
title: "Pythonで配列に要素を追加する方法"
emoji: "💻"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Python", "配列", "追加"]
published: true
---

こんにちは。今回は、Python初心者に向けて、配列に要素を追加する方法について解説します。

## 配列とは

配列とは、複数の要素をまとめたデータ構造のことです。Pythonでは、リスト(List)と呼ばれます。リストは、角括弧([])で要素を囲み、カンマ(,)で区切ります。

以下は、リストの例です。

```python
fruits = ["apple", "banana", "orange"]
```

## リストへの要素追加方法

リストに要素を追加する方法には、以下の2つがあります。

1. `append()`メソッドを使用する方法
2. `+`演算子を使用する方法

### `append()`メソッドを使用する方法

`append()`メソッドを使用すると、リストの末尾に要素を追加することができます。

```python
fruits = ["apple", "banana", "orange"]
fruits.append("grape")  # "grape"を追加
print(fruits)  # ["apple", "banana", "orange", "grape"]
```

### `+`演算子を使用する方法

`+`演算子を使用すると、2つのリストを結合して新しいリストを作成することができます。

```python
fruits1 = ["apple", "banana", "orange"]
fruits2 = ["grape", "kiwi"]
fruits = fruits1 + fruits2  # fruits1とfruits2を結合
print(fruits)  # ["apple", "banana", "orange", "grape", "kiwi"]
```

## サンプルコード

以下は、`append()`メソッドを使用してリストに要素を追加するサンプルコードです。

```python
fruits = ["apple", "banana", "orange"]
fruits.append("grape")  # "grape"を追加
print(fruits)  # ["apple", "banana", "orange", "grape"]
```

以下は、`+`演算子を使用して2つのリストを結合するサンプルコードです。

```python
fruits1 = ["apple", "banana", "orange"]
fruits2 = ["grape", "kiwi"]
fruits = fruits1 + fruits2  # fruits1とfruits2を結合
print(fruits)  # ["apple", "banana", "orange", "grape", "kiwi"]
```

## 注意点

注意点として、リストには異なる型の要素を追加することができます。しかし、可読性を考えると、同じ型の要素を追加する方が良いでしょう。

また、リストに要素を追加する場合は、リストの長さが増えるため、メモリ消費量が増加します。特に、大量の要素を追加する場合は注意が必要です。

## まとめ

Pythonでリストに要素を追加する方法について学びました。`append()`メソッドを使用する方法と、`+`演算子を使用する方法があります。また、異なる型の要素を追加できるため、可読性を考慮して同じ型の要素を追加することが望ましいです。

## データサイエンティストスクール 無料部分あります
PythonやRなどのプログラミングを学ぶなら、
さらに統計分野を学習してデータサイエンティストを目指すのがおすすめ！

ディープラーニングやビックデータ分析などの高額システム案件の受注にも有利になります。

システム開発より、分析がやりたい方向けですが、下記載せておきます。

https://hack-note.com/programming-schools/#toc17
 
