---
title: "Github Actionsを使ってGithubにpushしたらQiitaに自動投稿する方法"
emoji: "📝"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["github actions", "qiita api", "workflow", "automation"]
published: true
---

こんにちは。今回は、Github Actionsを使って、GithubにpushしたらQiitaに自動投稿する方法について解説していきます。Github Actionsを使えば、Github上のイベントをトリガーに、様々な処理を自動化することができます。この記事では、Github Actionsを使ってGithubにpushしたらQiitaに自動投稿する方法を実際の例を交えながら解説します。

## 前提条件

この記事を読む前に、以下の前提条件を満たしていることを確認してください。

- Githubアカウントを持っていること
- Qiitaアカウントを持っていること
- Qiita APIのアクセストークンを取得していること

## 手順

以下の手順に従って、GithubにpushしたらQiitaに自動投稿するワークフローを作成しましょう。

### 1. Qiita APIのアクセストークンを取得する

Qiita APIを使うためには、アクセストークンが必要です。以下の手順に従って、Qiita APIのアクセストークンを取得してください。

1. [Qiita](https://qiita.com/)にログインする。
2. 右上のユーザーメニューから「設定」をクリックする。
3. 「アプリケーション」タブから「新しいトークンを発行」をクリックする。
4. トークン名を設定し、「新しいトークンを発行する」をクリックする。
5. 発行されたアクセストークンをメモしておく。

### 2. Githubにリポジトリを作成する

Githubにリポジトリを作成し、ローカル環境にクローンします。

### 3. Qiita APIを使うためのライブラリをインストールする

Qiita APIを使うためのライブラリである[qiita-js](https://github.com/inabajunmr/qiita-js)をインストールします。npmを使ってインストールすることができます。

```bash
npm install qiita-js
```

### 4. Qiitaに投稿するスクリプトを作成する

Github Actionsで実行するスクリプトを作成します。ここでは、以下のようなスクリプトを作成します。

```javascript
const QiitaJS = require('qiita-js').default;
const qiita = new QiitaJS({ token: process.env.QIITA_ACCESS_TOKEN });

const title = 'Qiitaに投稿するタイトル';
const body = 'Qiitaに投稿する本文';
const tags = ['Qiita', 'Github Actions'];

qiita.items.create({ title, body, tags })
  .then(() => {
    console.log('投稿が完了しました！');
  })
  .catch((error) => {
    console.error(error);
  });
```

このスクリプトでは、Qiita APIを使用して、タイトル、本文、タグを指定して、Qiitaに投稿することができます。

### 5. ワークフローファイルを作成する

Github Actionsで実行するワークフローファイルを作成します。リポジトリのルートに、.github/workflowsディレクトリを作成し、以下のような内容のqiita.ymlという名前のファイルを作成します。

```yaml
name: Post to Qiita on Push

on:
  push:
    branches:
      - main

jobs:
  post-to-qiita:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v2
      - name: Setup Node.js
        uses: actions/setup-node@v2
        with:
          node-version: '14.x'
      - name: Install Dependencies
        run: npm install
      - name: Post to Qiita
        env:
          QIITA_ACCESS_TOKEN: ${{ secrets.QIITA_ACCESS_TOKEN }}
        run: node post-to-qiita.js
```

このワークフローでは、mainブランチにpushされた場合、post-to-qiita.jsスクリプトが実行され、指定したタイトル、本文、タグを持つ投稿がQiitaに作成されます。

### 6. シークレット情報を設定する

ワークフローで使用するシークレット情報を設定します。Githubのリポジトリ設定から、シークレット情報QIITA_ACCESS_TOKENを設定します。先程取得したQiita APIのアクセストークンを設定します。

### 7. Githubにpushする

以上の手順が完了したら、Githubにpushしてワークフローを実行します。Githubにpushすると、自動的にワークフローが実行され、Qiitaに投稿されます。

## まとめ

以上が、Github Actionsを使ってGithubにpushしたらQiitaに自動投稿する方法です。Github Actionsを使うことで、様々な処理を自動化することができます。今回の例では、Qiitaに投稿するような処理を自動化することができました。是非、自分の開発に活用してみてください。
