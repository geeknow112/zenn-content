---
title: "初級エンジニアがプログラミング副業で稼ぐまでの5手順"
emoji: "💻"
type: "tech"
topics: ["プログラミング", "副業", "未経験"]
published: true
---

こんにちは。今回は、プログラミングについて未経験のエンジニア向けて、副業としてプログラミングを始めるための5つのステップをご紹介します。

## 1. プログラミングの基礎を学ぶ

プログラミングを始める前に、まずは基礎的な知識を身につけることが必要です。プログラミング言語の種類は多岐にわたりますが、初心者におすすめなのはPythonやJavaScriptです。これらの言語は学びやすく、幅広い用途に利用されています。

初心者向けの学習用書籍やオンライン講座が充実しているため、自分に合った方法で基礎を学びましょう。学習には時間がかかるかもしれませんが、プログラミングの基礎をしっかりと身につけることが、将来的に副業として稼ぐための大切なファンデーションになります。

以下はPythonで書かれたFizzBuzz問題のサンプルコードです。

```python
for i in range(1, 101):
    if i % 15 == 0:
        print('FizzBuzz')
    elif i % 3 == 0:
        print('Fizz')
    elif i % 5 == 0:
        print('Buzz')
    else:
        print(i)
```

### プログラミングスクールについて
プログラミングはYoutubeやネット独学で十分に習得できますが、最初の"手ほどき"があった方が習得速度が速いです。
ぼくは独学で基礎は習得しましたが、いざ現場に出ると使い物にならず、OJTで納品レベルまで習得することができました。。
スキル習得スピードを求めるならスクールで手ほどきしてもらうのをおススメします。
ただスクールにも向き不向きあるので、無料レッスンできるとこから試したらいいと思います。
下記、ご紹介です。
- <a href="//af.moshimo.com/af/c/click?a_id=2612475&p_id=1555&pc_id=2816&pl_id=66181" rel="nofollow" referrerpolicy="no-referrer-when-downgrade">在宅ワークで稼げるスキルを身につける テックアカデミーWeb制作講座</a><img src="//i.moshimo.com/af/i/impression?a_id=2612475&p_id=1555&pc_id=2816&pl_id=66181" width="1" height="1" style="border:none;">

- <a href="//af.moshimo.com/af/c/click?a_id=2613693&p_id=2011&pc_id=4076&pl_id=27478" rel="nofollow" referrerpolicy="no-referrer-when-downgrade">【RaiseTech】最速で稼げるプロになるエンジニアリングスクール受講申し込み</a><img src="//i.moshimo.com/af/i/impression?a_id=2613693&p_id=2011&pc_id=4076&pl_id=27478" width="1" height="1" style="border:none;">

- <a href="//af.moshimo.com/af/c/click?a_id=2612470&p_id=1870&pc_id=3646&pl_id=26004" rel="nofollow" referrerpolicy="no-referrer-when-downgrade">プログラミングスクール「クリプテックアカデミア」の無料体験レッスン受講</a><img src="//i.moshimo.com/af/i/impression?a_id=2612470&p_id=1870&pc_id=3646&pl_id=26004" width="1" height="1" style="border:none;">


## 2. 実際にコーディングしてみる

プログラミングを学んだら、次は実際にコーディングしてみることが大切です。自分で考えたアイデアを実現することで、より実践的なスキルを身につけることができます。

まずは、自分が興味を持っている分野や、解決したい問題をテーマにして、簡単なアプリケーションを作ってみましょう。また、GitHubなどのコード共有サイトに自分のコードを公開することで、技術力のアピールにもつながります。

以下は、Pythonで作成したシンプルなポモドーロタイマーのサンプルコードです。

```python
import time

def pomodoro(minutes):
    seconds = minutes * 60
    while seconds > 0:
        print(f"Time remaining: {seconds // 60} minutes {seconds % 60} seconds")
        time.sleep(1)
        seconds -= 1
    print("Time's up!")

if __name__ == "__main__":
    pomodoro(25)
```

## 3. プロジェクトに参加する

自分でアプリケーションを作るのは難しい場合は、オープンソースプロジェクトに参加することをおすすめします。GitHubなどのプラットフォームには、さまざまなプロジェクトが公開されており、自分のスキルアップにもつながります。

プロジェクトに参加することで、実際の開発現場でのコミュニケーションやコーディングスキルの向上につながるだけでなく、有名なオープンソースプロジェクトに貢献することで、自分の技術力をアピールすることもできます。プロジェクトに参加する前に、プロジェクトの目的や開発言語、コーディング規約などをしっかりと把握しましょう。

以下は、PythonのWebフレームワークであるDjangoのオープンソースプロジェクトに参加するためのサンプルコードです。

```python
# コントリビュートの手順
# 1. プロジェクトをフォークする
# 2. ローカル環境にクローンする
# 3. ブランチを作成する
# 4. コードを変更する
# 5. コミットメッセージを記述する
# 6. プッシュする
# 7. プルリクエストを送信する

# プルリクエストの例
# Djangoのドキュメントに誤字を修正する
# https://github.com/django/django/pull/12345
```

## 4. フリーランスサイトで仕事を受注する

プログラミングのスキルを身につけたら、次は実際に仕事を受注して稼ぐことができます。オンライン上で仕事を受注できるフリーランスサイトは多数存在し、自分のスキルに合った案件を見つけることができます。

フリーランスサイトで仕事を受注する場合は、クライアントとのコミュニケーションや納期管理、報酬の設定などに注意が必要です。自分のスキルに見合った報酬を設定し、クライアントとのやり取りを円滑に進めることが大切です。

以下は、フリーランスサイトで受注したPythonのWebアプリケーション開発案件のサンプルコードです。

```python
# Flaskを使ったWebアプリケーションの例
from flask import Flask, request, render_template

app = Flask(__name__)

@app.route('/')
def index():
    return render_template('index.html')

@app.route('/submit', methods=['POST'])
def submit():
    name = request.form['name']
    message = request.form['message']
    # データベースに保存するなどの処理
    return render_template('result.html', name=name, message=message)

if __name__ == '__main__':
    app.run(debug=True)
```

:::message alert
フリーランスサイトで仕事を受注する場合は、詐欺やクレームなどのリスクもあるため、信頼できるサイトを利用することが重要です。また、クライアントとの契約内容や報酬条件は、しっかりと確認するようにしましょう。
:::

## 5. プログラミングコミュニティに参加する

プログラミングコミュニティに参加することで、他のプログラマーと交流し、刺激を受けることができます。また、コミュニティ内での情報交換や技術的な相談などにより、スキルアップにつながることが期待できます。

プログラミングコミュニティに参加する方法は、オンライン上での活動やオフラインイベントへの参加などがあります。自分の興味のある分野や、利用しているプログラミング言語に関するコミュニティに参加することをおす
