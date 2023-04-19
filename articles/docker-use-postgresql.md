---
title: "Docker初心者のためのPostgreSQLのDockerコンテナの作成方法"
emoji: "🐘"
type: "tech"
topics: ["docker", "postgresql"]
published: true
---

こんにちは。今回は、Docker初心者に向けて、PostgreSQLのDockerコンテナの作成方法について解説します。Dockerを使うことで、簡単にPostgreSQLの環境を構築することができます。Dockerコンテナを使うことで、環境依存性を排除し、開発環境と本番環境の差異を解消することができます。

# Dockerコンテナの作成方法

Dockerコンテナを作成するためには、以下の手順を実行します。

## 1. Dockerイメージの取得

まず、PostgreSQLのDockerイメージを取得します。以下のコマンドを実行して、Docker HubからPostgreSQLの最新のDockerイメージを取得します。

```bash
docker pull postgres
```

## 2. Dockerコンテナの作成

次に、Dockerコンテナを作成します。以下のコマンドを実行して、PostgreSQLのDockerコンテナを作成します。

```bash
docker run --name my-postgres -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```

このコマンドで、名前が「my-postgres」というPostgreSQLのDockerコンテナが作成されます。また、環境変数「POSTGRES_PASSWORD」に「mysecretpassword」というパスワードが設定されます。

## 3. Dockerコンテナの起動

Dockerコンテナを起動するには、以下のコマンドを実行します。

```bash
docker start my-postgres
```

これで、PostgreSQLのDockerコンテナが起動されます。

## 4. Dockerコンテナの停止

Dockerコンテナを停止するには、以下のコマンドを実行します。

```bash
docker stop my-postgres
```

## 5. Dockerコンテナの削除

Dockerコンテナを削除するには、以下のコマンドを実行します。

```bash
docker rm my-postgres
```

# PostgreSQLの設定

Dockerコンテナ上でPostgreSQLを設定するには、以下の手順を実行します。

## 1. Dockerコンテナにログイン

まず、以下のコマンドを実行して、Dockerコンテナにログインします。

```bash
docker exec -it my-postgres bash
```

## 2. PostgreSQLの設定ファイルの編集

PostgreSQLの設定ファイルである「postgresql.conf」を編集します。以下のコマンドを実行して、設定ファイルを開きます。

```bash
vi /var/lib/postgresql/data/postgresql.conf
```

設定ファイルの編集を行います。たとえば、以下のように「listen_addresses」を設定すると、PostgreSQLに外部からの接続が可能になります。

```
listen_addresses = '*'
```

## 3. PostgreSQLの再起動

設定ファイルの編集が終わったら、以下のコマンドを実行してPostgreSQLを再起動します。

```bash
service postgresql restart
```

以上で、Dockerコンテナ上でのPostgreSQLの設定が完了しました。

:::message alert
Dockerコンテナ上でPostgreSQLを設定する際には、設定ファイルのバックアップを取るなど、注意深く作業を行うようにしましょう。
:::

# まとめ

Dockerを使えば、簡単にPostgreSQLの環境を構築することができます。また、Dockerコンテナを使うことで、環境依存性を排除し、開発環境と本番環境の差異を解消することができます。Dockerを使って、効率的な開発を行いましょう。
