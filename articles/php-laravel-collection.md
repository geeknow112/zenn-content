---
title: "Laravelで便利なCollectionの使い方"
emoji: "📚"
type: "tech"
topics: ["php", "laravel", "collection"]
published: true
---

こんにちは。今回は、Laravel初心者に向けて、Collectionという機能について解説します。LaravelでのCollectionは、PHPの配列を拡張したもので、データのフィルタリング、マッピング、ソートなどの操作を簡単に行うことができます。この記事では、LaravelのCollectionの基本的な使い方を紹介し、実際のコード例も交えながら説明していきます。

## Collectionとは

LaravelのCollectionは、PHPの配列を拡張したもので、様々な便利なメソッドを提供しています。これらのメソッドを使うことで、配列を簡単に操作することができます。Collectionは、データベースから取得したデータやAPIから取得したデータなど、様々なデータを扱う場合に便利です。

## 基本的な使い方

Collectionを使うには、まずはじめに配列を作成します。配列を作成したら、それをCollectionに変換します。配列をCollectionに変換するには、collect関数を使います。

```php
$array = [1, 2, 3, 4, 5];

$collection = collect($array);
```

上記のコードでは、$arrayという配列を作成し、それをcollect関数でCollectionに変換しています。

## フィルタリング

Collectionを使うと、データのフィルタリングが簡単に行えます。例えば、以下のような配列があったとします。

```php
$users = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 30],
    ['name' => 'Charlie', 'age' => 20],
    ['name' => 'Dave', 'age' => 35],
];
```

この配列から、ageが30以上のユーザーだけを取り出すには、filterメソッドを使います。

```php
$filtered = collect($users)
    ->filter(function ($user) {
        return $user['age'] >= 30;
    });
```

上記のコードでは、collect関数で配列をCollectionに変換し、filterメソッドでageが30以上のユーザーだけを取り出しています。

## マッピング

Collectionを使うと、データのマッピングが簡単に行えます。例えば、以下のような配列があったとします。

```php
$users = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 30],
    ['name' => 'Charlie', 'age' => 20],
    ['name' => 'Dave', 'age' => 35],
];
```

この配列から、nameだけを取り出して新しい配列を作成するには、mapメソッドを使います。

```php
$names = collect($users)
    ->map(function ($user) {
        return $user['name'];
    });
```

上記のコードでは、collect関数で配列をCollectionに変換し、mapメソッドでnameだけを取り出しています。

## ソート

Collectionを使うと、データのソートが簡単に行えます。例えば、以下のような配列があったとします。

```php
$users = [
    ['name' => 'Alice', 'age' => 25],
    ['name' => 'Bob', 'age' => 30],
    ['name' => 'Charlie', 'age' => 20],
    ['name' => 'Dave', 'age' => 35],
];
```

この配列をageの昇順でソートするには、sortByメソッドを使います。

```php
$sorted = collect($users)
    ->sortBy('age');
```

上記のコードでは、collect関数で配列をCollectionに変換し、sortByメソッドでageの昇順でソートしています。

## まとめ

LaravelのCollectionは、PHPの配列を拡張したもので、データのフィルタリング、マッピング、ソートなどの操作を簡単に行うことができます。この記事では、Collectionの基本的な使い方を紹介し、実際のコード例も交えながら説明しました。ぜひ、Laravelでの開発に役立ててください。

:::message alert
注意：Collectionは、大量のデータを扱う場合にはパフォーマンスが悪くなる場合があります。そのため、大量のデータを扱う場合には、データベースのクエリビルダやEloquentを使うことをおすすめします。
:::

:::message
注意：Collectionは、PHPの配列を拡張したものであるため、PHPの配列と同様に、多次元配列やオブジェクトの配列に対しても使えます。
:::
