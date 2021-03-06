# 最小限のコード

綴る！

---

C++ での **最小限** のコードは、

```cpp
int main(){}
```

となる。これを実行しても何もしない。この *虚空* プログラムがメモリに読み込まれるだけ。

こう書いても良い。

```cpp
int    main 
( 
)
{
}
```

```cpp
   int
 main
 (   ) { }
```

なぜかというと、C++ では **スペースや改行は自由** なの。でも、意味のある英単語がくっつくのはだめ。

```cpp
intmain(){}
```

↑をコンパイルしようとしても **失敗** する。スペースとかで区切られていないから判別できなくなっちゃう。

同様に、何か書き方を間違えていてコンパイラが理解できないと、エラーメッセージを **吐く** (テキストメッセージを出すことをたまにこう表現する)。

「コンパイルできない！」「動かない！」「なんかメッセージが大量に出てきちゃった！」とかあったらどんどん質問してね。
