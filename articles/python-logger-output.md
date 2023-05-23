---
title: "Pythonでログを出力する方法"
emoji: "💻"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["Python", "logger"]
published: true
---

:::message alert
本記事は、Python初心者向けに作成されており、基本的な機能にフォーカスしています。上級者の方にはあまり参考にならない場合があります。
:::

こんにちは。今回は、Python初心者に向けて、ログを出力する方法について解説します。Pythonには、ログを出力するための標準ライブラリであるloggingが用意されています。

以下では、実際のコード例を交えて、ログを出力する方法について解説していきます。

## loggingモジュールを使った方法

loggingモジュールを使うことで、簡単にログを出力することができます。loggingモジュールは、ログレベルによって、出力する情報の詳細度を設定することができます。

以下は、loggingモジュールを使った例です。

```python
import logging

# ログの設定
logging.basicConfig(level=logging.DEBUG, format='%(asctime)s %(levelname)s %(message)s')

# ログの出力
logging.debug('Debugログ')
logging.info('Infoログ')
logging.warning('Warningログ')
logging.error('Errorログ')
logging.critical('Criticalログ')
```

上記のコードでは、ログレベルを設定しています。logging.DEBUGは最も詳細なログレベルで、logging.CRITICALは最も重要度の高いログレベルです。

ログの出力方法は、logging.debug()、logging.info()、logging.warning()、logging.error()、logging.critical()の5つが用意されています。

## ログファイルに出力する方法

loggingモジュールを使って、ログをファイルに出力することもできます。以下は、ログをファイルに出力する例です。

```python
import logging

# ログの設定
logging.basicConfig(level=logging.DEBUG, format='%(asctime)s %(levelname)s %(message)s', filename='example.log')

# ログの出力
logging.debug('Debugログ')
logging.info('Infoログ')
logging.warning('Warningログ')
logging.error('Errorログ')
logging.critical('Criticalログ')
```

上記のコードでは、logging.basicConfig()の引数に、filenameを指定しています。これにより、ログがファイルに出力されます。

:::message
ログファイルに出力する場合は、ファイル名と保存場所に十分注意してください。また、書き込み権限のある場所に保存する必要があります。
:::

## まとめ

Pythonでログを出力する方法について、loggingモジュールを使った方法と、ログファイルに出力する方法を紹介しました。ログを出力することで、プログラムの動作を確認しやすくなり、デバッグがしやすくなります。

今回紹介した内容は、Python初心者でも簡単に実践できる基本的な機能です。ぜひ、自分のプログラムにログ出力機能を取り入れてみてください。

## データサイエンティストスクール 無料部分あります
PythonやRなどのプログラミングを学ぶなら、
さらに統計分野を学習してデータサイエンティストを目指すのがおすすめ！

ディープラーニングやビックデータ分析などの高額システム案件の受注にも有利になります。

システム開発より、分析がやりたい方向けですが、下記載せておきます。

https://hack-note.com/programming-schools/#toc17

