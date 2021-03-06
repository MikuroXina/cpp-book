# 名前解決

コンパイラ「誰よその関数！」

---

いろいろいじくりまわしていた人は気づいているかもしれないけれど、

このように **関数の定義を main 関数よりも下に書く** と、

```cpp
int main() {
  hey(2);
}

void hey(int num) {}
```

呼び出した行でコンパイラが

> ~ って名前は宣言されていません

みたいなエラーを吐く。

C++ での名前は、すでに **宣言していないと使用できない**。今どきの言語では上でも下でもいいのだけれど。

*定義は宣言でもある* ので、main 関数より上で関数を定義していれば問題なかった。

でも、どうしても下側に書きたい場合は、ちゃんと **宣言** だけができる。


文法はこんな感じ。

> *戻り値の型* *関数名* ( *引数リスト* ) ;

関数の定義と少し違っていて、文を書く部分は `;` になっている。

さっきのを書き足すとこうなる。

```cpp
void foo(double ratio); // どんな引数なのか名前で示す
void hey(int); // 引数名は省略してもいい

int main() {
  hey(2);
  foo(3.0);
}

void hey(int) {} // ちなみに使わない引数名も省略できる

#include <iostream>

void foo(double ratio) {
  std::cout << "Ratio: " << ratio << "\n";
}
```
