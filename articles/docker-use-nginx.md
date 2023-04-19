---
title: "DockerでNginxを使おう！"
emoji: "🐳"
type: "tech"
topics: ["Docker", "Nginx"]
published: true
---

こんにちは。今回は、Docker初心者に向けて、Dockerを使ってNginxを実行する方法を説明します。

## はじめに

Nginxは、高速で軽量なWebサーバーです。Dockerを使ってNginxを実行することで、簡単にWebサーバーを構築することができます。

## DockerでNginxを実行する方法

DockerでNginxを実行するには、まずDockerイメージを取得する必要があります。以下のコマンドで、公式のNginxイメージを取得することができます。

```bash
docker pull nginx
```

Nginxを実行するためには、Dockerコンテナを起動する必要があります。以下のコマンドで、Nginxを実行するDockerコンテナを起動することができます。

```bash
docker run -d -p 80:80 nginx
```

上記のコマンドでは、`-d`オプションでDockerコンテナをデーモンとして実行し、`-p`オプションでホストのポート80をDockerコンテナのポート80にマッピングしています。

Dockerコンテナが正常に起動しているか確認するには、以下のコマンドを実行します。

```bash
docker ps
```

上記のコマンドで、起動しているDockerコンテナの一覧を確認することができます。

## Dockerfileを使ったNginxのカスタマイズ

Dockerでは、Dockerfileを使ってイメージをカスタマイズすることができます。Nginxの設定ファイルをカスタマイズする場合は、Dockerfileを使用して、設定ファイルをDockerイメージに組み込むことができます。

以下は、Dockerfileの例です。

```Dockerfile
FROM nginx

COPY nginx.conf /etc/nginx/nginx.conf
```

上記のDockerfileでは、`nginx.conf`ファイルを`/etc/nginx/nginx.conf`にコピーしています。このDockerfileをビルドすることで、カスタマイズされたNginxイメージを作成することができます。

```bash
docker build -t my-nginx .
```

## Docker Composeを使ったNginxと他のサービスの連携

Docker Composeを使用すると、複数のDockerコンテナを一括で管理することができます。以下は、Docker Composeを使用したNginxと他のサービスの連携の例です。

```yaml
version: '3'

services:
  nginx:
    image: nginx
    ports:
      - "80:80"
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
    depends_on:
      - app

  app:
    image: my-app
    ports:
      - "3000:3000"
```

上記のDocker Composeファイルでは、Nginxと`my-app`という名前のアプリケーションを起動しています。Nginxは、ポート80でリクエストを受け取り、`my-app`にリクエストを転送します。

## 注意点

Dockerコンテナを起動する際に、`-d`オプションを使用してデーモンモードで実行することができますが、デーモンモードで実行すると、コンテナ内でエラーが発生した場合に、エラーの原因を特定することが難しくなる場合があります。エラーを特定するためには、コンテナをインタラクティブモードで実行することをおすすめします。

また、セキュリティ上の理由から、コンテナ内でrootユーザーを使用することはおすすめしません。Dockerfileを使用して、別のユーザーを作成することをおすすめします。

:::message alert
Docker Composeを使用する場合は、コンテナの起動順序に注意する必要があります。依存するサービスが起動する前に、Nginxが起動すると、リクエストが失敗する場合があります。
:::

## まとめ

Dockerを使用して、Nginxを簡単に実行する方法について説明しました。Docker Composeを使用することで、複数のDockerコンテナを一括で管理することができます。Dockerを使用する際には、セキュリティにも注意しましょう。
