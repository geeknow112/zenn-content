---
title: "【初心者向け】Twitterのツイートをダウンロードする方法"
emoji: "🐓"
type: "tech"
topics: ["Twitter", "使い方"]
published: true
---

こんにちは。今回は、TWITTERについて初心者エンジニアに向けて、TWEETのダウンロード方法について解説していきます。

## はじめに

TWITTERは、世界中の人々がつぶやきを投稿し共有するSNSの1つです。TWITTERでは、1つの投稿を「TWEET」と呼びます。TWEETは、テキストだけでなく、画像や動画、リンクを含めることができます。

そんなTWEETですが、自分が気に入ったTWEETを保存したいことがあるかもしれません。しかし、TWITTERにはダウンロード機能がないため、どのようにダウンロードするか迷ってしまう方も多いのではないでしょうか。

そこで、本記事ではTWEETのダウンロード方法を解説します。

## TWEETのダウンロード方法

TWITTERにはTWEETのダウンロード機能がありませんが、第三者が開発したツールを利用することで、TWEETをダウンロードすることが可能です。以下に、代表的なツールを紹介します。

### 1. twdownload.com

twdownload.comは、TWEETのURLを入力することで、画像や動画を含むTWEETをダウンロードできるサイトです。

1. ダウンロードしたいTWEETのURLをコピーします。
2. twdownload.comにアクセスします。
3. コピーしたTWEETのURLを入力し、「ダウンロード」ボタンをクリックします。
4. ダウンロードファイルが生成され、ダウンロードが開始されます。

### 2. GetMyTweet.com

GetMyTweet.comは、TWEETのURLを入力することで、テキストや画像、動画、リンクを含むTWEETをダウンロードできるサイトです。

1. ダウンロードしたいTWEETのURLをコピーします。
2. GetMyTweet.comにアクセスします。
3. コピーしたTWEETのURLを入力し、「Download」ボタンをクリックします。
4. ダウンロードファイルが生成され、ダウンロードが開始されます。

以上の方法で、TWEETのダウンロードができます。

## サンプルコード

```python
import requests
import urllib.request

url = 'https://twitter.com/zenn_dev/status/1429836430640152578'
response = requests.get(url).text

start = '<div class="css-1dbjc4n r-1d2f490 r-18u37iz r-1wbh5a2">'
end = '<div class="css-1dbjc4n r-1wbh5a2 r-dnmrzs">'

tweet_html = response.split(start)[1].split(end)[0]
print(tweet_html)

img_srcs = []
video_srcs = []
for sub_html in tweet_html.split('</div>'):
    for img in sub_html.split('<img '):
        img_src = img.split('src="')[1].split('"')[0]
        if 'media' in img_src and img_src not in img_srcs:
            img_srcs.append(img_src)
    for video in sub_html.split('<video '):
        video_src = video.split('src="')[1].split('"')[0]
        if 'video' in video_src and video_src not in video_srcs:
            video_srcs.append(video_src)

for i, img_src in enumerate(img_srcs):
    urllib.request.urlretrieve(img_src, f'tweet_img_{i}.jpg')

for i, video_src in enumerate(video_srcs):
    urllib.request.urlretrieve(video_src, f'tweet_video_{i}.mp4')
```

上記のサンプルコードは、Pythonを利用してTWEETの画像や動画をダウンロードする方法を示しています。`requests`モジュールを利用して、TWEETのHTMLを取得し、`urllib.request`モジュールを利用して、画像や動画をダウンロードしています。

## まとめ

本記事では、TWEETのダウンロード方法について解説しました。TWEETをダウンロードするには、第三者が開発したツールを利用する必要がありますが、手軽にダウンロードできるので、ぜひ試してみてください。

TWEETのダウンロードには、著作権やプライバシーに関する規約があるため、注意が必要です。ダウンロードする前に、TWITTERの利用規約を確認し、適切な使用方法に従うようにしましょう。

また、本記事ではPythonを利用したサンプルコードを示しましたが、他のプログラミング言語でも同様にTWEETのダウンロードが可能です。ぜひ、自分の好きな言語でTWEETのダウンロード機能を実装してみてください。

## 参考記事

- [【初心者でもできる】Twitterから画像をダウンロードする方法](https://simsuma.com/twitter-image-download/)
- [【超簡単】Twitterの画像、動画をダウンロードする方法まとめ](https://vazblog.com/twitter-download/)
