---
title: "Github ActionsによるCI/CDの自動化"
emoji: "👨‍💻"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["github actions", "ci/cd", "automation", "workflow"]
published: true
---

Github Actionsは、Github上のイベントをトリガーに、自動化された処理を実行するためのツールです。この記事では、Github Actionsを使ってCI/CDの自動化を行う手順を説明します。

## 前提条件

この記事では、以下の前提条件があるものとします。

- Githubアカウントを持っていること。
- Githubリポジトリにアクセスできること。
- アプリケーションのビルドとデプロイに必要な設定が完了していること。

## CI/CDの自動化の手順

以下の手順に従って、Github Actionsを使ってCI/CDの自動化を行います。

### 1. Github Actionsの有効化

まず、GithubリポジトリでGithub Actionsを有効にする必要があります。

1. Githubリポジトリにアクセスします。
2. 右上の「Settings」をクリックします。
3. 左側のメニューから「Actions」を選択します。
4. 「Allow all actions」を選択します。

### 2. ワークフローファイルの作成

次に、Github Actionsの設定を記述するワークフローファイルを作成します。

1. Githubリポジトリのルートディレクトリに、`.github/workflows`ディレクトリを作成します。
2. `workflows`ディレクトリに、ワークフローファイルを作成します。ファイル名は任意のもので構いませんが、`.yml`拡張子を付ける必要があります。

以下は、Node.jsのアプリケーションをCI/CDするためのワークフローファイルの例です。

```yml
name: CI/CD Pipeline

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v2

      - name: Setup Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14.x'

      - name: Install dependencies
        run: npm install

      - name: Run tests
        run: npm test

      - name: Build app
        run: npm build

  deploy:
    needs: build
    runs-on: ubuntu-latest

    steps:
      - name: Deploy to production
        uses: some-action-for-deploying-to-production@v1
        with:
          deployment_key: ${{ secrets.DEPLOYMENT_KEY }}
```

このワークフローファイルでは、`push`イベントがトリガーとなって、`main`ブランチにコミットされた場合に、以下の処理が実行されます。

1. `build`というジョブが実行されます。このジョブでは、`ubuntu-latest`環境で以下の処理が実行されます。
   - コードのチェックアウト
   - Node.jsのセットアップ
   - 依存関係のインストール
   - テストの実行
   - アプリのビルド
2. `deploy`というジョブが実行されます。このジョブは、`build`ジョブが成功した場合にのみ実行されます。このジョブでは、`ubuntu-latest`環境で、本番環境にデプロイするためのアクションが実行されます。

また、上記のワークフローファイルでは、デプロイに必要な秘密情報（`DEPLOYMENT_KEY`）をGithubのSecretsに設定しています。このように、Github Actionsでは環境変数や秘密情報を安全に扱うことができます。

### 3. ワークフローの実行

最後に、作成したワークフローファイルを実行します。

1. Githubリポジトリにアクセスします。
2. 「Actions」タブをクリックします。
3. 実行したいワークフローを選択します。
4. 「Run workflow」をクリックします。

ワークフローが正常に実行されると、以下のような結果が表示されます。

![Github Actionsの実行結果](https://i.imgur.com/5xRZa90.png)

ワークフローの実行結果を見ることで、ビルドやデプロイに失敗した場合に問題を特定しやすくなります。

## まとめ

この記事では、Github Actionsを使ってCI/CDの自動化を行う手順を紹介しました。Github Actionsを使うことで、開発者はより効率的に、品質の高いアプリケーションを開発することができます。是非、実際にGithub Actionsを試してみてください。
