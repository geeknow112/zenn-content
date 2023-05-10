---
title: "Github Actionsでsecretsを使って認証情報をセキュアに管理する"
emoji: "🔑"
type: "tech"
topics: ["github", "secrets", "actions", "初心者"]
published: true
---

こんにちは。今回は、githubについて初心者エンジニアに向けて、github actionsでsecretsを使ってみる方法について解説していきます。

## はじめに

github actionsは、ci/cdパイプラインを作成するためのプラットフォームで、github上で簡単に使用することができます。ですが、プライベート情報やapiキーのような秘密情報を、githubのリポジトリ上に保存するのは非常に危険です。そのため、githubではsecretsと呼ばれる方式で、秘密情報を安全に管理することができます。

## github actionsでsecretsを使う方法

### 1. secretsの登録

まずは、githubのリポジトリの`settings`タブから、`secrets`を選択します。ここで、秘密情報の名前と値を入力し、`add secret`ボタンをクリックして登録します。

![secrets](https://user-images.githubusercontent.com/12345678/111000000-11111a00-1111-1111-1111-111111111111.png)

### 2. github actionsでのsecretsの使用

次に、`.github/workflows`ディレクトリ内に、`yml`ファイルを作成します。具体的には、以下のような内容のファイルを作成します。

```
name: example

on: [push]

env:
  my_secret: ${{ secrets.my_secret }}

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - name: example
      run: echo $my_secret
```

上記の例では、`env`にsecretsを定義しています。この例の場合、secretsの名前が`my_secret`であると仮定します。`env`に定義したsecretsは、`$my_secret`などの形で呼び出すことができます。

### 3. secretsの確認

最後に、github actionsを実行することで、定義したsecretsが正しく呼び出されているかを確認します。`actions`タブから、実行したジョブのログを確認することができます。

## まとめ

今回は、github actionsでsecretsを使う方法について解説しました。secretsを利用することで、秘密情報の漏洩を防ぐことができます。是非、実際に手を動かして、github actionsとsecretsの使い方を覚えていきましょう。

:::message alert
secretsは、秘密情報を安全に管理するための有力なツールですが、鍵の管理によってはその効果を失うことがあります。secretsの適切な管理には、注意が必要です。
:::

参考url:
- [working with github actions secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository)
- [creating a github secret and using it within github actions](https://rachelcarmena.github.io/2019/12/12/creating-a-github-secret-and-using-it-in-github-actions.html)
