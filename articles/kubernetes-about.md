---
title: "Kubernetesとは？初心者エンジニア向け基本的な操作方法とサンプルコード"
emoji: "🐳"
type: "tech"
topics: ["Kubernetes", "コンテナオーケストレーション", "初心者エンジニア"]
published: true
---

こんにちは。今回は、初心者エンジニア向けにKubernetesについて解説します。

## Kubernetesとは

Kubernetesは、コンテナオーケストレーションシステムの一つで、Googleが開発したオープンソースのプロジェクトです。Kubernetesは、Dockerなどのコンテナ技術を使ってアプリケーションを展開、管理するためのプラットフォームで、クラウドネイティブなアプリケーションを構築するために必要な機能を提供します。

Kubernetesは、コンテナ化されたアプリケーションを複数のホストに分散配置し、自動的にスケールアップやスケールダウンを行い、アプリケーションを高可用性で実行することができます。また、アプリケーションのデプロイやアップデート、ロールバックなどの管理も簡単に行えます。

## Kubernetesの構成要素

Kubernetesは、マスターノードとワーカーノードから構成されます。

### マスターノード

マスターノードは、Kubernetesクラスタ全体の管理を行うためのコントロールプレーンです。以下のコンポーネントから構成されています。

- kube-apiserver: Kubernetes APIを公開し、クラスタ全体のリソースの操作や管理を行います。
- etcd: クラスタの状態を格納するデータベースです。
- kube-scheduler: Podのスケジューリングを担当します。
- kube-controller-manager: クラスタ全体の状態を監視し、必要に応じてクラスタの状態を変更します。

### ワーカーノード

ワーカーノードは、実際にアプリケーションが動作するノードです。以下のコンポーネントから構成されています。

- kubelet: ノード上でのPodの実行を管理します。
- kube-proxy: クラスタ外部からのアクセスを内部のPodに転送するためのネットワークプロキシです。
- コンテナランタイム: Dockerなどのコンテナランタイムを使って、コンテナを実行します。

## Kubernetesの操作方法

Kubernetesの基本的な操作方法について、簡単に説明します。

### Kubernetesクラスタの作成

まずは、Kubernetesクラスタを作成します。以下のようなコマンドを実行します。

```
$ kubeadm init
```

### Kubernetesオブジェクトの作成

次に、Kubernetesオブジェクトを作成します。例えば、Deploymentを作成する場合は、以下のようなYAMLファイルを作成します。

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```

そして、以下のようなコマンドを実行してオブジェクトを作成します。

```
$ kubectl apply -f <YAMLファイル名>
```

### Kubernetesオブジェクトの確認

Kubernetesオブジェクトの状態を確認するには、以下のようなコマンドを実行します。

```
$ kubectl get <オブジェクトの種類>
```

例えば、Deploymentの状態を確認する場合は、以下のようにします。

```
$ kubectl get deployment
```

### Kubernetesオブジェクトの削除

Kubernetesオブジェクトを削除する場合は、以下のようなコマンドを実行します。

```
$ kubectl delete <オブジェクトの種類> <オブジェクト名>
```

例えば、Deploymentを削除する場合は、以下のようにします。

```
$ kubectl delete deployment nginx-deployment
```

## Kubernetesのサンプルコード

最後に、Kubernetesのサンプルコードを紹介します。

### Podの作成

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    app: nginx
spec:
  containers:
  - name: nginx
    image: nginx:latest
    ports:
    - containerPort: 80
```

### Deploymentの作成

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: nginx-deployment
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx
  template:
    metadata:
      labels:
        app: nginx
    spec:
      containers:
      - name: nginx
        image: nginx:latest
        ports:
        - containerPort: 80
```

以上が、Kubernetesの基本的な操作方法とサンプルコードの紹介です。初心者エンジニアでも理解しやすいように、わかりやすく解説しているつもりです。Kubernetesは、クラウドネイティブなアプリケーションを構築するために必要な技術の一つなので、ぜひ学習してみてください。
