# 配列型

一列に並べ〜！

---

今までの型だと、一つの値を一つづつ丁寧に扱うことしかできなかった。

ここでは、扱う数が決まっている、それなりの量のデータを格納するときの型について書くよ。

**配列型** は、データを格納する **要素** を指定した数だけ持つ。

文法はこう。

> *格納する型* *名前* \[ *要素数* ]

```cpp
int array[10]; // int が 10 個分
```


## 初期化

この型で初期化するときには、**リスト初期化** が使える。

これは以下のように、`{` から `}` の間に、`,` で区切って値を入れたものを初期値にする書き方だよ。


### 要素数を指定して、同じ長さのリストを用意する場合

その長さぴったりの配列型の変数が作られる。

```cpp
int nums[5] = {0, 2, 4, 8, 1};
```

`nums` はこんな感じになる。

| 位置 | 値  |
| ---- | --- |
| 0    | 0   |
| 1    | 2   |
| 2    | 4   |
| 3    | 8   |
| 4    | 1   |

**インデックス** (位置を表す数字) は `0` から始まる。これ大事。


### 要素数を指定しない場合

リスト側と同じ要素数になる。

```cpp
int nums[] = {0, 4, 5};
//       ↑ に 3 を入れたのと同じ
```


### 要素数より、リストの数が少ない場合

リスト側で足りない部分には、`0` に相当するものが入る。

```cpp
int buffer[15] = {}; // 残りすべては 0
double vertexes[20] = {1.0, 1.0, 1.0}; // 残りは 0.0
```


## 要素にアクセス

作った配列は、ちゃんとその中身を触れる。

配列に格納されている値のことを **要素** っていうよ。

要素にアクセスするときは、`[` と `]` の間に **インデックス** を入れる。

```cpp
int nums[5] = {1, 4, 5, 7};

nums[0]; // 1
nums[3]; // 5

nums[2] = 2;
nums[4] = 8;
```

変数も入れられるので、こういうこともできる。

```cpp
#include <iostream>

int main() {
  int nums[5] = {1, 4, 5, 7};
  for (int i = 0; i < 5; ++i) { // i は 0 から 4 へ
    int const &nums_i = nums[i]; // i 番目の nums
    std::cout << "nums[" << i << "] ~~~ " << nums_i << "\n";
  }
}
```

まぁこれからこの配列型を使う機会はほとんどない。

けれど、**複数の値を格納したり取り出したりする感覚** を少しつかんでもらえたらいいな。


ちなみに、ここでやった **リスト初期化** は今までの型にも使える。

```cpp
int a = {}; // 0 と同じ
double b = {2.0};
```
