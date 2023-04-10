---
title: "AWS WSP（Workspaces Streaming Protocol）が利用できずあがいた件"
emoji: "🔥"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["AWS", "WSP", "Workspaces"]
published: false
---

# 参考
こちらの記事で概ね全て記載ありましたので、これに沿って利用確認してみました。
https://dev.classmethod.jp/articles/general-availability-about-amazon-workspaces-streaming-protocol/

# 事前準備
参考記事の通り、普通にWSP版を利用して動作確認をしました。
手順は下記の通りです。
1. コンソール画面でWorkspacesのバンドルを移行（PCoIP → WSP）
2. Workspacesアプリのデバイス設定で「リモートで利用する」に設定
3. ウェブカメラテストサイト(https://ja.webcamtests.com/)で動作確認

検証には、meetを使うと認証で面倒だったのでテストサイトを使いました。

# 異常
3台ほどWorkspacesを立ち上げて確認しましたが、どれもローカルのカメラを認識してくれず、エラーとなっていました。
