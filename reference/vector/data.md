#data (C++11)
```cpp
T* data() noexcept;
const T* data() const noexcept;
```

##効果
配列の先頭へのポインタを返す。

`vector`が空の場合であっても、この関数の呼び出し自体は問題なく行える。ただし、その戻り値については規定されていないため、間接参照を行うと未定義動作になる。

##戻り値
`[data(), data() + size())` が適正な範囲になるようなポインタ。

空ではない`vector`に対しては`data() == &front()`となる。

##計算量
定数時間


##例
```cpp
#include <iostream>
#include <vector>

int main()
{
  std::vector<int> v = {3, 1, 4};

  int* p = v.data();

  std::cout << *p << std::endl;

  ++p;
  std::cout << *p << std::endl;
}
```
* data[color ff0000]

###出力
```
3
1
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): ??
- [GCC, C++0x mode](/implementation#gcc.md): ??
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md): 10.0, 11.0, 12.0


###備考
gcc 4.8.2 の時点で libstdc++ の実装にはバグがあり、`vector` が空の場合に `data()` を呼び出すと未定義動作になる。([Bug 59829](http://gcc.gnu.org/bugzilla/show_bug.cgi?id=59829))


