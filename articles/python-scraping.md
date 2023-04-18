---
title: "Python初心者のためのスクレイピング入門"
emoji: "💻"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["python", "スクレイピング"]
published: true
---

こんにちは。今回は、Python初心者に向けて、スクレイピングの入門記事を書いていきます。

## はじめに

Webサイト上の情報を取得するスクレイピングは、Pythonを使ったデータ取得の方法として非常に有用です。Pythonにはスクレイピングに必要なライブラリが豊富にあり、簡単にスクレイピングができるため、初心者でも始めやすいと言われています。本記事では、Pythonでスクレイピングを行う方法を、基本的なコードを交えて解説していきます。


## スクレイピングに必要なライブラリのインストール

Pythonでスクレイピングを行うには、以下のライブラリをインストールする必要があります。

- requests
- BeautifulSoup

requestsはHTTPリクエストを送信し、HTMLコンテンツを取得するときに使われます。BeautifulSoupはHTMLコンテンツを解析し、必要な情報を抽出するために使われます。

これらのライブラリは、pipコマンドを使用して簡単にインストールできます。コマンドプロンプトまたはターミナルで以下のコマンドを入力してください。

```
pip install requests
pip install beautifulsoup4
```

:::message alert
上記のコマンドを実行する前に、Pythonがインストールされていることを確認してください。
:::

## スクレイピングの基本

スクレイピングを始める前に、スクレイピングの対象となるWebページを決定しましょう。WebページのURLを取得し、requestsライブラリを使用してHTTPリクエストを送信し、HTMLコンテンツを取得する必要があります。

以下は、PythonでHTTPリクエストを送信し、HTMLコンテンツを取得するサンプルコードです。

```python
import requests

url = "https://www.example.com"
response = requests.get(url)
html_content = response.content
```

上記のコードでは、requests.get()メソッドを使用して、指定したURLにGETリクエストを送信し、レスポンスを取得しています。レスポンスの.content属性にアクセスすることで、HTMLコンテンツを取得できます。

次に、BeautifulSoupライブラリを使用して、取得したHTMLコンテンツから必要な情報を抽出する方法を解説します。

以下は、PythonでBeautifulSoupを使用してHTMLコンテンツから情報を抽出するサンプルコードです。

```python
from bs4 import BeautifulSoup

soup = BeautifulSoup(html_content, "html.parser")
title = soup.title.string
print(title)
```

上記のコードでは、BeautifulSoupクラスを使用して、HTMLコンテンツを解析し、抽出したい情報を取得しています。例として、HTMLコンテンツから<title>タグの中身を取得しています。.string属性を使用することで、<title>タグの中身のテキストを取得できます。

## スクレイピングの注意点

スクレイピングを行う際には、以下の点に注意する必要があります。

- Webサイトの利用規約に違反しないようにする
- Webサイトのサーバーへの負荷をかけないようにする
- 取得した情報を不正に利用しないようにする

これらの注意点に従い、マナーを守ってスクレイピングを行うようにしましょう。

## まとめ

Pythonを使ったスクレイピングの基本的な方法を解説しました。requestsライブラリとBeautifulSoupライブラリを使用することで、簡単にWebサイト上の情報を取得することができます。しかし、スクレイピングを行う際には、Webサイトの利用規約に違反しないように注意する必要があります。初心者の方は、まずは練習用のWebサイトから始めて、スクレイピングの基礎を身につけていきましょう。
