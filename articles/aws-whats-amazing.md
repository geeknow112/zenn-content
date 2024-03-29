---
title: "AWSの何がすごい？これだけわかるとWEBサービス開発案件無双できる！"
emoji: "🔥"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["AWS", "とは"]
published: false
---

# AWSの基本について
- AWS（アマゾン ウェブ サービス）は、クラウドコンピューティングサービス
- もともとはECサイト「Amazon」自体が抱える課題を解決するために考え出したITインフラの仕組みを、クラウドサービスとして提供したもの
- クラウドサービスとは、インフラやソフトウェアを、インターネット経由でサービスとして利用する形態のこと。
- オンプレミスに対して、インターネットの先にある、雲の上のサービスを使うから「クラウド」
- さまざまなクラウドサービスのなかでも、世界190カ国以上、数百万に及ぶユーザを抱え、圧倒的なシェアを誇るAWS。
- もちろん日本国内でもかなりの企業が導入、クラウドを利用している企業の2社に1社がAWSを利用しているというデータもある。

- これだけのシェアを生み出したのは、利用者が多い→規模が大きい→ハードウェア調達などで優位に→価格が下がる→利用者が増える……という好循環を生み出したこと。
- 実際にAWSでは、サービス開始時から値下げを繰り返しており、その数は過去10年間で70回以上！「シェア1位だからシェア1位」みたいな、ほかではどうにも太刀打ちできない強さを感じます。

- さらに、オブジェクトストレージサービス「Amazon S3」からスタートしたAWSですが、
- 仮想サーバ「Amazon EC2」（コラム１）、
- マネージド型データベース「Amazon RDS」（コラム２）といった基本的なサービスに続き、
- ネットワーク、モバイル、セキュリティ、IoT、機械学習（コラム３）にいたるまで、
- いまやそのサービスは100以上！
- 最先端の技術を惜しげもなくサービスとして提供するため、いち早く新技術を使いたいエンジニアたちも、こぞってAWSに集まり、
- 利用者が増える……とこちらも好循環を生み出しているのです。

# AWSを使うと何が嬉しいのか？
- クラウドサービス全般の特徴でもありますが、なんといっても最大のメリットは「必要なときに、必要なだけ使える」ということ。
- 「新しく検証環境が欲しい」というときも簡単に用意できますし、「キャンペーン期間だけサーバを増強したい」ももちろんOK。
- 検証やキャンペーン期間が終われば、サーバを減らすのも簡単です。
- 検証環境のために、サーバなどのハードウェア購入をする必要もなければ、キャンペーン時の負荷にあわせて余裕を持ったハードウェアを用意しておく必要もありません。
- 「必要になったら、Web上の管理画面から設定するだけですぐ使える」これが、オンプレミスにはないAWSならではの魅力です。

- 費用も利用時間などに応じた従量課金制。
- 使った分だけ支払う形で、初期費用は掛かりません。
- 大きな初期投資を用意することなくスタートできるため、新規事業立ち上げ時やスタートアップ企業でも数多く利用されています。

# AWSは基本的には高い？
- クラウドが普及しはじめた当初は、クラウド移行のメリットとしてコスト削減が挙げられていました。
- ただ、最近では、クラウドは安くない、意外と高い、という意見も増えています。
- つまり、「オンプレミスは初期費用がかかるものの、その後は保守費用のみ。クラウドの月額費用を積算するとある時点でオンプレミスより高くなる」というわけですね。
- 確かに、AWSに支払う月額費用と、オンプレミスのハードウェア調達・保守サポート費用だけを考慮すると、そうなるかもしれません。
- ですが、システムやインフラにはこれ以外にもさまざまな費用がかかるもの。
- それらを一切考慮せずに高い・安いを判断するのはちょっと待ってほしい。

- まずクラウドのメリットとしてもよく言われるのが、ハードウェアの運用負荷からの解放です。
- サーバが止まってるとか、再起動しないといけないとか、データセンタに行かなきゃいけないとか、そういった保守運用から解放されるメリットは大きいもの。
- これは単に情シスが楽になる（運用負荷軽減）、というだけではなく、対応にかかっていた人件費の削減にもつながります。

- それだけではなく、オンプレミスではサーバのハードウェア以外の費用も結構かかりますよね。
- 物理的なスペースにサーバの配線、ネットワークの構築にもコストはかかりますし、稼働後は毎月電気代もかかります。
- AWSならこれらもすべて月額費用に込み！ですが、オンプレミスとクラウドのTCOを比較する際にこれらのコストもきちんと考慮しているかというと怪しくはないでしょうか？

- もうひとつ、よくやりがちなのが「オンプレミスのハードウェアを5年でリプレースするから、5年間のTCOで比較しよう」というものです。
- 実はこれが落とし穴。 確かに、5年間の比較ではクラウドの方が高くなるかもしれません。
- でも、オンプレミスは6年目に大規模なリプレースが必要になりますよね？
- もちろんAWSは6年目も大きな追加投資は不要で、そのまま使い続けられます。
- 6年目以降のコストを考慮すると、結果は大きく違ってくるはずです。

- さらにさらに！オンプレミスでは1度ハードウェアを購入すると、5年間は同じものを使い続けるしかないですが、その間も新しいアーキテクチャはどんどん出てきます。
- AWSは最新のCPU/GPUなどを採用したサービスも次々に展開しますから、自社のサービスをそちらに切り替えれば、常に最新のアーキテクチャを利用することもできるんです。

# AWSのセキュリティについて（オンプレとの比較）
- それでもなんとなくクラウドは不安……という声も以前はよく聞きましたが、この点も最近では「むしろAWSの方がセキュアでは」という意見が主流になってきたように感じます。
- AWSは、ISOをはじめとするかなりたくさんの第三者認証を取得していますし、AWSの基盤のセキュリティ対策も専門のエンジニアたちがガッツリやっているワケです。
- 自社でここまでの認証を取得するのは相当ハードルが高いですし、それだけのエンジニア部隊を自社に抱えるのも無理があります。AWS環境の方が安心、という判断もうなずけます。

# まとめ
今回は駆け足でAWSの基本やメリットを紹介してきましたが、これらのポイントをまとめて解説した資料を公開しています。「AWSはオンプレミスより高そう」「セキュリティが心配」といったAWS移行をためらう理由について、どうAWSがクリアしているのか、ひとつずつ丁寧に解説！ぜひご覧ください。
