# do - while

まぁまずはお茶でも飲んで

---

さっきの `while` は、判断してから実行してた。

でもたまーに実行してから判断したいときもある。

それをするのが `do` - `while` 文。

文法はこんな感じ。

> do *実行する文* while ( *条件式* );

**評価と実行の順序が逆** なのが最大の特徴。

つまり、最低でも一回以上は処理が実行されるということ。

実際に使うとこんな感じ。

```cpp
#include <iostream>
int main() {
  int input;
  do {
    std::cout << "0 よりも大きい整数を入力してね\n";
    std::cin >> input;
  } while (!(0 < input));
  do {
    std::cout << "やあ！\n";
    --input;
  } while (0 < input);
}
```

入力をやり直させるときに使うこともできる。

ただ、`while` よりは使わない。使える場面がそんなにないし。

だから説明もこれで終わりだよ。
