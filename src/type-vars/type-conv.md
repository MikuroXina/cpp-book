# 型変換

ﾍｼﾝ！

---

本来、違う型どうしでの計算はできないけれど、型を変換するとできるようになる。


# 暗黙的型変換

まず、違う型どうしを計算させようとしても、コンパイルできちゃう。

このとき、より表現の幅が広い型へと変換される。


例えば、`double` と `int` で演算するときは、`int` の方が `double` へと変換される。

```cpp
500 * 1.08; // => 500. * 1.08 => 540.
```

更に、変数に代入するときはその変数の型へと変換される。

```cpp
int price = 500;
price = price * 1.08; // price * 1.08 は double だが、再び int になる
price *= 1.08; // 上と同じ
```


# static_cast

暗黙的ではなく、明示的な型変換もある。それがこれ。

```cpp
static_cast < 型名 > ( 式 )
```

たまに使うくらいだけど、実際に使うとこんな感じ。

```cpp
double num = 1.46;

// double を int にすると小数点以下が切り捨てられる
int num2 = static_cast<int>(num); // => 1

// int を double にすると小数点以下が 0 でスタートする
static_cast<double>(num2); // 1.0
```

これから型変換を明示するときに使うよ。
