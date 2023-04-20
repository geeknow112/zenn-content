---
title: "matplotlibでグラフの色を変更する方法"
emoji: "📊"
type: "tech"
topics: ["python", "matplotlib", "色"]
published: true
---

こんにちは。今回は、matplotlib初心者に向けて、Pythonでグラフの色を変更する方法についてお話しします。

## はじめに

Pythonのmatplotlibライブラリを使うと、グラフを描画することができます。グラフの色を変更することで、より見やすく、わかりやすいグラフを作成することができます。

Pythonでは、matplotlibライブラリを使ってグラフを描画することができます。matplotlibライブラリは、グラフを描画するための非常に強力なツールであり、多くのカスタマイズオプションを提供しています。

## matplotlibでグラフの色を変更する方法

matplotlibライブラリでグラフの色を変更するには、plot関数にcolorパラメータを指定します。colorパラメータには、以下のように色を指定する方法があります。

- 文字列で指定する方法
- RGB値を指定する方法

### 文字列で指定する方法

plot関数のcolorパラメータには、文字列で色を指定することができます。代表的な色名は以下の通りです。

- 赤：'red'
- 緑：'green'
- 青：'blue'
- 黄：'yellow'
- 紫：'purple'
- ピンク：'pink'
- オレンジ：'orange'
- グレー：'gray'

以下は、赤色のグラフを描画するサンプルコードです。

```python
import matplotlib.pyplot as plt
import numpy as np

# データの作成
x = np.arange(0, 10, 0.1)
y = np.sin(x)

# グラフの描画
plt.plot(x, y, color='red')

# グラフの表示
plt.show()
```

### RGB値を指定する方法

plot関数のcolorパラメータには、RGB値を指定することもできます。RGB値は、赤、緑、青の3つの成分からなり、それぞれ0から255までの値を取ります。

以下は、RGB値を指定してグラフの色を変更するサンプルコードです。

```python
import matplotlib.pyplot as plt
import numpy as np

# データの作成
x = np.arange(0, 10, 0.1)
y = np.sin(x)

# グラフの描画
plt.plot(x, y, color=(0, 0, 1)) # 青色

# グラフの表示
plt.show()
```

## 注意点

- colorパラメータに指定する色名は小文字でも大文字でも構いません。
- RGB値を指定する場合、各成分の値は0から1の範囲の浮動小数点数で指定することもできます。

## まとめ

本記事では、Pythonのmatplotlibライブラリを使ってグラフの色を変更する方法について解説しました。グラフの色を変更することで、より見やすく、わかりやすいグラフを作成することができます。グラフの色を変更するには、plot関数のcolorパラメータに色を指定する方法があります。色を指定する方法は、文字列で指定する方法とRGB値を指定する方法があります。
