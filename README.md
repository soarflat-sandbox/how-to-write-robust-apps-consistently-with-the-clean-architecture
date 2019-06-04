# [How to write robust apps every time, using “The Clean Architecture](https://medium.com/free-code-camp/how-to-write-robust-apps-consistently-with-the-clean-architecture-9bdca93e17b)

## Entity

- >エンティティはビジネスルールをカプセル化したメソッドのあるオブジェクトやデータ構造と関数の集合である
- >エンティティはアプリケーションにおいて、もっとも一般的で高次元なルールをカプセル化したビジネスオブジェクトである
- >つまりルールをカプセル化したオブジェクトというのは要するにモデルのことなのです

どういうこっちゃい？

### そもそもモデルとは？

現実の事象または概念を抽象化して表すモノ。

事象あるいは概念を抽象化する作業のことをモデリングという。

### ルールをカプセル化したオブジェクトというのは要するにモデル？

水を例にしてみる。

水には現実の事象で以下の法則（言い換えればルール）が存在する。

- 0度で凍り始める
- 100度を超えると蒸発

もしもソフトウェア開発で解決しようとしている問題に対して、この水のルールが役立つのであれば、このルールを抽象化して水を表現するオブジェクトを開発する。

開発されたオブジェクトはモデリングがされたものなので、「水のモデル」である。

そのため、ルールをカプセル化したオブジェクトは、ルールを抽象化したモノなのでモデルである。

### Entityの例

以下は非常に単純なEntityの例。

それぞれのメソッドがビジネスルールをカプセル化したメソッドを表している（はず）。

```ts
export type Counter = number;

export function createCounter(value: number = 0): Counter {
  return value;
}

export function increment(counter: Counter): Counter {
  return createCounter(counter + 1);
}

export function decrement(counter: Counter): Counter {
  return createCounter(counter - 1);
}
```

## UseCase

ざっくり言えば、「このシステムは、こんなことができるぜ」というものを表現したもの。

たとえば、「ユーザー登録処理」は「ユーザーが登録処理をできること」を表現しているため、ユースケースである。

この層の各要素は、外部レイヤーへのインターフェイスを提供し、システムの他の部分と通信するハブとして機能する。

それらはユースケースの完全な実行に対して責任があり、一般的にInteractorsと呼ばれる。# how-to-write-robust-apps-consistently-with-the-clean-architecture
