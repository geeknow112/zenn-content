---
title: "PythonでJSONを扱う方法"
emoji: "🐍"
type: "tech"
topics: ["Python", "JSON"]
published: true
---

こんにちは。今回は、Pythonについて初心者エンジニアに向けて、JSONを扱う方法をご紹介します。

## JSONとは

JSON(JavaScript Object Notation)は、データをクライアントとサーバーの間で簡単にやりとりするための形式です。JavaScriptで使用されるオブジェクトの記法を参考に、テキストベースの軽量な文書形式で記述されます。PythonでもJSONを扱うことができます。

## JSONの書式

JSONは、以下のような書式で表現されます。

```json
{
  "name": "John",
  "age": 30,
  "city": "New York"
}
```

上記の例では、"name"という名前で"John"という値、"age"という名前で30という値、"city"という名前で"New York"という値がそれぞれ設定されています。

## PythonでJSONを扱う方法

Pythonでは、JSONを扱うための標準ライブラリが用意されています。JSON形式の文字列をPythonのデータ型に変換する方法と、Pythonのデータ型をJSON形式の文字列に変換する方法をそれぞれご紹介します。

### JSON形式の文字列をPythonのデータ型に変換する方法

JSON形式の文字列をPythonのデータ型に変換するには、json.loads()メソッドを使用します。以下は、JSON形式の文字列をPythonのデータ型に変換する例です。

```python
import json

# JSON形式の文字列
json_string = '{"name": "John", "age": 30, "city": "New York"}'

# JSON形式の文字列をPythonのデータ型に変換する
data = json.loads(json_string)

# データ型を表示する
print(type(data)) # <class 'dict'>
print(data["name"]) # John
```

### Pythonのデータ型をJSON形式の文字列に変換する方法

Pythonのデータ型をJSON形式の文字列に変換するには、json.dumps()メソッドを使用します。以下は、Pythonのデータ型をJSON形式の文字列に変換する例です。

```python
import json

# Pythonのデータ型
data = {
  "name": "John",
  "age": 30,
  "city": "New York"
}

# Pythonのデータ型をJSON形式の文字列に変換する
json_string = json.dumps(data)

# JSON形式の文字列を表示する
print(json_string) # {"name": "John", "age": 30, "city": "New York"}
```

## まとめ

Pythonでは、JSONを扱うための標準ライブラリが用意されています。JSON形式の文字列をPythonのデータ型に変換するには、json.loads()メソッドを使用し、Pythonのデータ型をJSON形式の文字列に変換するには、json.dumps()メソッドを使用します。是非、JSONを扱う際にはこの方法を参考にしてみてください。

:::message alert
本記事で使用するコードはサンプルであり、実際に利用する際には適切なチェックやバリデーションを行ってください。
:::

参考にしたブログ記事:
- [PythonでJSONを扱う方法](https://www.atmarkit.co.jp/ait/articles/1910/04/news028.html)
- [PythonでJSONデータを取得する方法](https://qiita.com/Taiga__/items/5dcd4e5e5e9e5837b514)
