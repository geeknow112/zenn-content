---
title: "Docker Composeで外部Volumeを使う方法"
emoji: "🐳"
type: "tech"
topics: ["Docker", "Docker Compose", "外部Volume"]
published: true
---

こんにちは。今回は、Docker初心者に向けて、Docker Composeを使って外部Volumeをマウントする方法について説明します。

## Docker Composeとは？

Docker Composeは、複数のDockerコンテナを定義して管理するためのツールです。Docker Composeを使うと、複雑なアプリケーションを構築するために必要なコンテナやネットワークなどを簡単に定義できます。また、Docker Composeを使うことで、複数のコンテナを一括で起動・停止することができます。

## 外部Volumeとは？

Dockerコンテナは、データを永続化するためにVolumeを使用することができます。しかし、コンテナが削除されると、Volumeに保存されたデータも一緒に削除されてしまいます。この問題を解決するために、外部Volumeを使用することができます。外部Volumeを使用すると、コンテナが削除されてもデータは残ります。

外部Volumeを使用する場合は、Dockerコンテナとホストマシンの間でデータの共有をする必要があります。以下では、Docker Composeを使って外部Volumeをマウントする方法について説明します。

## Docker Composeで外部Volumeをマウントする方法

外部Volumeをマウントするには、Docker Composeファイルに以下のような設定を追加します。

```yaml
version: '3'
services:
  app:
    image: myapp
    volumes:
      - mydata:/data
volumes:
  mydata:
```

上記の例では、`app`という名前のサービスに対して、`mydata`という名前の外部Volumeをマウントしています。`mydata`という名前のVolumeが存在しない場合は、自動的に作成されます。

外部Volumeをマウントする際には、`volumes`セクションで定義したVolume名を、`services`セクションで定義したサービスの`volumes`オプションで指定します。上記の例では、`mydata:/data`という形式で指定しています。これにより、`mydata`という名前のVolumeが、`/data`というマウントポイントにマウントされます。

## サンプルコード

以下は、Docker Composeを使ってMongoDBを起動し、外部Volumeをマウントする例です。

```yaml
version: '3'
services:
  mongodb:
    image: mongo
    volumes:
      - mongodb-data:/data/db
volumes:
  mongodb-data:
```

上記の例では、`mongodb`という名前のサービスに対して、`mongodb-data`という名前の外部Volumeをマウントしています。`mongodb-data`という名前のVolumeが存在しない場合は、自動的に作成されます。

## 注意点

外部Volumeを使用する場合は、ホストマシンのファイルシステムに直接アクセスするため、セキュリティ上のリスクがあります。外部Volumeを使用する際には、適切なアクセス権限を設定することが重要です。

また、外部Volumeを使用する場合は、ホストマシン上のディレクトリをマウントすることが多いため、ディレクトリのパスを間違えると、ホストマシン上のファイルが上書きされる可能性があります。注意して設定してください。

:::message alert
外部Volumeを使用する際には、適切なアクセス権限を設定することが重要です。
:::

## まとめ

Docker Composeを使って外部Volumeをマウントする方法について説明しました。外部Volumeを使用することで、コンテナが削除されてもデータを永続化することができます。Docker Composeを使うことで、複数のコンテナの管理やネットワークの設定などを簡単に定義することができます。適切なアクセス権限を設定して、安全に外部Volumeを使用しましょう。
