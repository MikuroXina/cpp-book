# for

フォウ、フォーウ！ファッ！

---

`for` 文は、`while` よりも数段上の **上位互換**。それも尋常ではないレベルで。

文法はこんな感じ。心して読んでくれ。

> for ( *初期化式* ; *条件式* ; *更新式* ) *実行する文*

なかなかにクセのある文法だけど、伝統工芸品的なものなのでしょうがない。多分来世紀にも残る。


## 処理の順序

`for` 文に三つある式たちには実行順序がある。以下のプログラムを例に処理を追いかけてみよう。

```cpp
int main() {
  int i;
  for (i = 0; i < 3; ++i) { /* ~ */ }
}
```

ループ前

> *初期化式* `i = 0` を実行

ループ 1 回目

> `i` は `0`
>
> *条件式* `i < 3` が `true` なのでループ続行
>
> 処理 (今回は空) を実行
>
> *更新式* `++i` を実行

が繰り返されていき、

ループ 4 回目

> `i` は `3`
>
> *条件式* `i < 3` が `false` なのでループ終了

というふうに全部で 3 回処理が実行される。


### for で continue

`for` の中でも `continue` が使える。

これを実行してみよう。

```cpp
for (int count = 1; count <= 10; ++count) {
  if (count % 3 == 0) {
    continue; // A へとジャンプ
  }
  std::cout << count << " ";
  // A
}
```

次の *評価式*、続いて *条件式* の実行に移るのがわかったかな？


## 実例

実際に使うとこんな感じ。初期化式の中で変数を作ることもできるので、こう書いてもいい。

```cpp
//               これ↓が繰り返す回数になっている
for (int i = 0; i < 3; ++i) {
  ; // 何かする
}
```

数を数えつつ繰り返すのに最適。よく使うのでしっかり書きなれておいてほしい。

ちなみに、この `i` のようにループの制御に使っている変数を *制御変数* と言ったりする。


### カウントアップの例

`0` から `10` まで数え上げる。

```cpp
for (int count = 0; count < 10; ++count) { }
```

`1` から `5` まで数え上げる。上とは **条件式の演算子が違う** ので注意！

```cpp
for (int count = 1; count <= 5; ++count) {}
```


### カウントダウンの例

`11` から `0` まで数え下げる。上とは **更新式の演算子が違う** ので注意！

```cpp
for (int count = 11; 0 < count; --count) { }
```

`7` から `2` まで数え上げる。

```cpp
for (int count = 7; 2 <= count; --count) {}
```

回数を指定した繰り返しにおいて、ふんだんに使うので絶対に覚えてね？

ちなみに、最近はループする文が `for` だけのプログラミング言語もある。
