---
title: "PythonのMatplotlibで簡単に日本語を表示する方法"
emoji: "📊"
type: "tech"
topics: ["python", "matplotlib", "日本語"]
published: true
---

こんにちは。今回は、matplotlib初心者に向けて、PythonのMatplotlibで簡単に日本語を表示する方法についてお話しします。

## はじめに

Matplotlibは、Pythonのグラフ描画ライブラリの一つであり、様々な種類のグラフを描画することができます。しかし、デフォルトでは日本語を表示することができません。本記事では、PythonのMatplotlibで簡単に日本語を表示する方法について解説します。

## 日本語を表示する方法

Matplotlibで日本語を表示するには、以下の手順を実行します。

1. フォントを指定する
2. グラフを描画する

### 1. フォントを指定する

まずは、日本語のフォントを指定します。Matplotlibでは、`rcParams`という設定ファイルを用いて、フォントを指定することができます。以下のコードを実行すると、フォントを`IPAexGothic`に変更することができます。

```python
import matplotlib as mpl

mpl.rcParams['font.family'] = 'IPAexGothic'
```

### 2. グラフを描画する

次に、グラフを描画します。以下のコードは、x軸に1から5までの数字、y軸にそれぞれ対応する日本語のラベルを持つ棒グラフを描画するコードです。

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [10, 5, 20, 15, 30]
labels = ['りんご', 'みかん', 'ぶどう', 'バナナ', 'キウイ']

plt.bar(x, y, tick_label=labels)
plt.xlabel('フルーツ')
plt.ylabel('売上数')
plt.title('フルーツの売上数')
plt.show()
```

上記のコードを実行すると、以下のようなグラフが表示されます。

![matplotlib_graph](https://user-images.githubusercontent.com/84633626/148834544-3d1e3d3d-cc00-4ac9-915c-309acc7d6b5a.png)

## 注意点

Matplotlibで日本語を表示する際には、以下の点に注意する必要があります。

- 使用するフォントによっては、文字化けすることがある
- フォントがインストールされていない場合、グラフが表示されないことがある

## まとめ

PythonのMatplotlibで日本語を表示する方法について解説しました。フォントを指定することで、簡単に日本語を表示することができます。しかし、使用するフォントによっては文字化けすることがあるため、注意が必要です。以上が本記事の内容となります。

## データサイエンティストスクール 無料部分あります
PythonやRなどのプログラミングを学ぶなら、
さらに統計分野を学習してデータサイエンティストを目指すのがおすすめ！

ディープラーニングやビックデータ分析などの高額システム案件の受注にも有利になります。

システム開発より、分析がやりたい方向けですが、下記載せておきます。

https://hack-note.com/programming-schools/#toc17

