---
title: "Docker ComposeでのWindowsファイル共有エラーの解決方法"
emoji: "🐳"
type: "tech"
topics: ["Docker", "Docker Compose", "Windows", "ファイル共有", "エラー"]
published: true
---

## 1. 前提

本記事は、WindowsでDocker Composeを使用してファイル共有をする際に発生するエラーについて解説します。

WindowsでDocker Composeを使用する場合、Docker Desktopの設定画面からフォルダーを共有しても、アクセス権限の問題でエラーが発生することがあります。このエラーは、Windowsのファイル共有機能に対するDockerの制限によって引き起こされます。

## 2. 問題発生

Docker Composeを使用してWindows上でファイル共有を設定しようとすると、以下のようなエラーが表示される場合があります。

```
ERROR: for {service_name}  Cannot create container for service {service_name}: failed to mount local volume: mount C:/Users/{user_name}/project:/app/{volume_name} : drive is not shared
```

このエラーは、Dockerが指定されたフォルダーをマウントできなかったことを示しています。Windowsのファイル共有機能が正しく構成されていないため、Dockerがファイルにアクセスできない状態になっている可能性があります。

## 3. 解決策

WindowsでDocker Composeを使用してファイル共有を設定する場合、以下の手順を実行してください。

1. 共有するフォルダーを右クリックし、[プロパティ]をクリックします。
2. [共有]タブをクリックし、[高度な共有]をクリックします。
3. [共有の設定]をクリックし、[このフォルダーを共有する]と[ネットワーク上からの変更を許可する]を選択します。
4. [アクセス許可]をクリックし、[追加]をクリックして、Dockerアカウントを追加します。
5. 追加したDockerアカウントに、フルコントロールのアクセス許可を与えます。
6. Docker Desktopを開きます。
7. [設定]をクリックし、[共有ドライブ]を選択します。
8. 共有するフォルダーを選択し、[適用]をクリックします。
9. Dockerを再起動します。

以上の手順を実行することで、WindowsでDocker Composeを使用してファイル共有を設定する準備が整いました。

なお、上記手順に加えて、Docker Desktopの設定を変更する必要がある場合があります。具体的には、以下の手順を実行してください。

1. Docker Desktopを開きます。
2. [設定]をクリックし、[共有ドライブ]を選択します。
3. 共有するフォルダーを選択し、[適用]をクリックします。
4. Dockerを再起動します。

これにより、WindowsでのDocker Composeファイル共有エラーの解決方法が完了しました。

## 4. 解決

以下は、Docker Composeファイルの例です。このファイルを使用することで、DockerでMySQLデータベースを実行し、WindowsホストのファイルシステムにあるSQLファイルを実行することができます。

```yaml
version: '3.8'
services:
  db:
    image: mysql:8.0
    command: --default-authentication-plugin=mysql_native_password
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: root_password
    volumes:
      - /c/Users/{user_name}/project/sql:/docker-entrypoint-initdb.d
```

このファイルでは、Docker Composeを使用してMySQLデータベースを実行し、Windowsホストの`/c/Users/{user_name}/project/sql`フォルダーをコンテナ内の`/docker-entrypoint-initdb.d`フォルダーにマウントしています。コンテナが起動すると、Dockerは自動的に`/docker-entrypoint-initdb.d`フォルダー内のSQLファイルを実行します。

以上で、WindowsでのDocker Composeファイル共有エラーの解決方法を説明しました。これらの手順に従って、ファイル共有を正しく構成し、Docker Composeを使用して開発を続けてください。
