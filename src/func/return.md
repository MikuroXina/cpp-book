# 戻り値 とreturn

（っ'-')╮ =͟͟͞͞0110110011000001 ﾌﾞｫﾝ

---

`return` 文は、関数が、実行してきた誰かに *値を返す* 文。

この文を処理すると **関数の実行は終了する**。


このように、`return` の後に続けて *式* を書く。

この式は **戻り値** (もしくは返り値) というもので、関数の実行結果みたいに扱われる。

この式の型である **戻り値型** を、関数の最初に書かないといけない。

> *戻り値型* *関数名* ( *引数リスト* ) { *0個以上の文* }

実際に使うとこんな感じ。

そうそう、この戻り値型が `void` だと、値を返さない。

```cpp
#include <iostream>

// 怠けるか怠けないか
void will_be(bool lazy) {
  if (lazy) {
    std::cout << "ﾅﾏｹﾙ(・´з`・)\n";
    return; // 関数を終了する効果しかない
  }
  std::cout << "ﾊﾀﾗｸ！(・∀・)\n";
  return; // ←は省略してもいい
}

// テキトーな数字を返すだけ
int random_number() {
  return 4;
}

int main() {
  will_be(false);
  will_be(true);
  std::cout << random_number();
}
```

もっぱら、計算結果を返すのに使う。

例えば、$f(x) = x^3 + x^2 = x^2 (x + 1)$ を計算する (数学に近い) 関数はこんな風に書く。

```cpp
double f(double x) { // x^3 + x^2
  double x2 = x * x;
  return x2 * (x + 1);
}
```

さぁ、いろんな種類の値を送り返してやろう。


## main 関数に関するお詫び(？)

実は今まで黙っていたことがある。

main 関数は本当はこう書かなきゃいけなかったんだよ!!!

```cpp
int main() {
  return 0;
}
```

ΩΩΩ<な、なんだってー！？

この `0` はプログラムの正常終了を表してる。`0` 以外を返すと異常終了として扱われる。

`return 0;` を省略すると、これが最後に自動で挿入される。だから書かなくてもいいってワケ。
