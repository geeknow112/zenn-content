---
title: "Dockerを使ってLaravelの環境を構築する方法"
emoji: "🐳"
type: "tech"
topics: ["php", "docker", "laravel"]
published: true
---

こんにちは。今回は、Dockerを使ってLaravelの環境を構築する方法について解説します。Dockerを使うことで、手軽にLaravelの環境を構築することができます。

## Dockerとは
Dockerとは、コンテナ仮想化技術を利用して、アプリケーションの実行環境を構築するためのツールです。Dockerを使うことで、アプリケーションを簡単に移植することができます。

## Laravelの環境をDockerで構築する方法
Laravelの環境をDockerで構築する方法は、以下の手順で行うことができます。

### 手順1. Dockerをインストールする
まずはじめに、Dockerをインストールする必要があります。Dockerのインストール方法は、オフィシャルサイトを参照してください。

### 手順2. Laravelプロジェクトを作成する
次に、Laravelプロジェクトを作成します。Laravelのプロジェクトを作成する方法は、以下のコマンドを実行することで行うことができます。

```bash
docker run --rm -v $(pwd):/app composer create-project --prefer-dist laravel/laravel .
```

このコマンドを実行することで、カレントディレクトリにLaravelプロジェクトが作成されます。

### 手順3. Dockerfileを作成する
次に、Dockerfileを作成します。Dockerfileとは、Dockerイメージをビルドするためのスクリプトです。以下のようなDockerfileを作成します。

```dockerfile
FROM php:8.1-fpm

# 必要なパッケージのインストール
RUN apt-get update && apt-get install -y \
    libicu-dev \
    libzip-dev \
    zip \
    unzip \
    && docker-php-ext-configure intl \
    && docker-php-ext-install \
    pdo_mysql \
    intl \
    zip

# Composerのインストール
COPY --from=composer /usr/bin/composer /usr/bin/composer

# Laravelのインストール
WORKDIR /var/www/html
COPY . /var/www/html
RUN composer install

# ポートの公開
EXPOSE 9000

CMD ["php-fpm"]
```

このDockerfileでは、PHP 8.1-fpmイメージをベースに、必要なパッケージをインストールし、Composerをインストールしています。また、Laravelプロジェクトを/var/www/htmlディレクトリにコピーして、Composerを使って依存関係をインストールしています。

### 手順4. Dockerイメージをビルドする
次に、手順3で作成したDockerfileを使って、Dockerイメージをビルドします。以下のコマンドを実行して、Dockerイメージをビルドします。

```bash
docker build -t my-laravel-app .
```

### 手順5. Dockerコンテナを起動する
最後に、Dockerコンテナを起動します。以下のコマンドを実行して、Dockerコンテナを起動します。

```bash
docker run -p 8000:9000 my-laravel-app
```

このコマンドを実行することで、Dockerコンテナが起動し、Laravelアプリケーションが実行されます。ブラウザで http://localhost:8000/ にアクセスすると、Laravelのウェルカム画面が表示されます。

## 注意点
Dockerを使ってLaravelの環境を構築する際には、以下の点に注意してください。

- ポート番号を指定する必要があります。
- ホスト側のディレクトリとDockerコンテナ側のディレクトリをマウントする必要があります。
- Composerのキャッシュを削除するために、--no-cacheオプションを使う必要があります。

## まとめ
Dockerを使ってLaravelの環境を構築する方法を解説しました。Dockerを使うことで、手軽にLaravelの環境を構築することができます。ただし、ポート番号やマウントするディレクトリなど、細かい設定を行う必要があります。Dockerを使ったLaravelの開発に挑戦してみてください。
