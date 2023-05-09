---
title: "Flutterの使い方入門"
emoji: "📱💻"
type: "TECH"
topics: ["Flutter", "モバイルアプリ", "UI"]
published: true
---

こんにちは。今回は、Flutterについて初心者エンジニアに向けて、使い方の入門を解説していきます。

## Flutterとは？

Flutterは、Googleが開発したクロスプラットフォームのフレームワークで、AndroidやiOSのモバイルアプリ開発を行うことができます。DARTという言語を用いて開発するため、JavaやKotlin、Swiftなどの言語を完全に置き換えることができます。また、独自のUIフレームワークを持っており、簡単に美しいUIを実現できます。

## 環境構築

まずは、Flutterの環境構築を行いましょう。以下の手順でインストールが可能です。

1. 公式サイトからFlutter SDKをダウンロードして解凍する。

2. 解凍したフォルダを適当な場所に設置する。

3. 環境変数の設定をする。

4. flutter doctorコマンドを実行して、必要な依存パッケージがインストールされているか確認する。

環境構築の詳細については、公式ドキュメントを参照してください。

:::message alert
注意点として、AndroidやiOSにアプリをビルドするには、それぞれのプラットフォームの開発環境も必要になります。
:::

## プロジェクトの作成

環境構築が完了したら、早速プロジェクトを作成してみましょう。

1. Flutterコマンドを用いて、新規プロジェクトを作成する。

   ```
   flutter create my_app
   ```

2. vscodeなどのエディタで、my_appフォルダを開く。

3. main.dartファイルを開いて、コードを書き始める。

## UIの作成

Flutterは、独自のUIフレームワークを持っており、ウィジェットと呼ばれるUIの部品を組み合わせて作成します。以下に、シンプルな画面を作成するコードを示します。

```dart
import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      home: Scaffold(
        appBar: AppBar(
          title: Text('My First Flutter App'),
        ),
        body: Center(
          child: Text('Hello, World!'),
        ),
      ),
    );
  }
}
```

上記のコードでは、MaterialApp、Scaffold、AppBar、Center、Textなどのウィジェットを組み合わせて、タイトルバーと中央に表示されるテキストを持つ画面を作成しています。

また、Flutter Widget Catalogという公式のドキュメントには、様々なウィジェットの使用例が掲載されています。

## アプリの実行

アプリを実行するには、以下のコマンドを実行します。

```
flutter run
```

これにより、アプリが実行されてスマートフォンなどの画面上に表示されます。

## まとめ

Flutterは、Googleが提供するクロスプラットフォームのフレームワークで、DART言語を使って開発を行います。独自のUIフレームワークを持っており、美しいUIを簡単に実現できます。環境構築やプロジェクトの作成、UIの作成、アプリの実行までを解説しました。

Flutterは、まだまだ新しいフレームワークですが、非常にアクティブに開発が進められており、今後も多くの機能が追加されることが期待されます。ぜひ、手軽に始めてみてはいかがでしょうか。

参考記事：
- [Flutter公式ドキュメント](https://flutter.dev/docs)
- [Flutter公式ウィジェットカタログ](https://flutter.dev/docs/development/ui/widgets/catalog)
