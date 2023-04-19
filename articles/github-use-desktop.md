---
title: "Github Desktopの使い方入門"
emoji: "🐱"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["github", "desktop"]
published: true
---

こんにちは。今回は、Github初心者に向けて、Github Desktopの基本的な使い方について解説します。

## はじめに

Github Desktopは、WindowsおよびmacOS用のGithubクライアントソフトウェアです。このソフトウェアを利用することで、プログラムの管理や編集をより簡単に行うことができます。Github Desktopの基本的な使い方について、以下で説明します。

## Github Desktopのインストール

まず最初に、Github Desktopをインストールする必要があります。以下の手順でインストールを行ってください。

1. Github DesktopのWebサイトにアクセスします。
2. ダウンロードページから、自分のOSに合ったインストーラーをダウンロードします。
3. ダウンロードしたインストーラーを実行し、インストールを開始します。
4. インストールが完了したら、Githubアカウントにログインして、Github Desktopを起動します。

## リポジトリのクローン

Github Desktopでプロジェクトを管理するには、まずリポジトリをクローンする必要があります。クローンとは、Githubサーバー上のリポジトリを自分のPCに複製することです。以下の手順でクローンを行ってください。

1. Github Desktopを起動します。
2. メニューバーから「File」→「Clone Repository」を選択します。
3. クローンしたいリポジトリのURLを入力します。
4. クローン先のディレクトリを選択し、「Clone」ボタンをクリックします。

これで、Githubサーバー上のリポジトリが、自分のPC上に複製されます。

## コミットとプッシュ

リポジトリをクローンしたら、プログラムの編集や変更を行うことができます。変更を行ったら、以下の手順でコミットとプッシュを行ってください。

1. Github Desktopで編集したファイルを選択し、変更内容を入力します。
2. 「Commit to main」ボタンをクリックします。
3. 「Push Origin」ボタンをクリックします。

これで、Githubサーバー上のリポジトリに変更内容が反映されます。

## ブランチの作成とマージ

プログラムの開発では、複数の人が同時に作業を行うことがあります。このような場合には、ブランチを作成して、それぞれが分担して作業を行うことができます。以下の手順でブランチの作成とマージを行ってください。

1. Github Desktopで、編集対象のリポジトリを開きます。
2. メニューバーから「Branch」→「New Branch」を選択します。
3. ブランチ名を入力し、「Create Branch」ボタンをクリックします。
4. ブランチを切り替えたい場合は、メニューバーから「Branch」→「Switch Branch」を選択します。
5. ブランチの変更内容をコミットし、プッシュします。
6. 変更を反映するために、マージを行います。メニューバーから「Branch」→「Merge into Current Branch」を選択します。

これで、複数人での開発作業がスムーズに行えます。

## まとめ

以上で、Github Desktopの基本的な使い方について解説しました。Github Desktopを利用することで、Gitによるバージョン管理がより簡単になります。是非、Github Desktopを活用して、プログラムの開発をスムーズに行ってください。

サンプルコード1：

```python
def greet(name):
    print("Hello, " + name + "!")

greet("John")
```

サンプルコード2：

```javascript
function add(a, b) {
    return a + b;
}

console.log(add(3, 5));
```

:::message alert
注意点として、Github Desktopは基本的にGitの操作を行うためのツールであるため、Gitに関する基本的な知識が必要です。Gitについては、別途学習することをおすすめします。
:::

:::message
本記事は、2023年4月現在のGithub Desktopのバージョンを対象としています。今後のアップデートにより、記載内容が変更される可能性があります。
:::
