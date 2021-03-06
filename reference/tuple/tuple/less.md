#operator< (C++11)
```cpp
namespace std {
  template<class... TTypes, class... UTypes>
  bool operator<(const tuple<TTypes...>& t, const tuple<UTypes...>& u);
}
```

##概要
2つの`tuple`において、左辺が右辺より小さいかの判定を行う。


##要件
2つの`tuple`の要素数が同じであること。 
`tuple`の要素`std::`[`get`](./get.md)`<i>(t)`と`std::`[`get`](./get.md)`<i>(u)`において、すべての要素の比較 `std::`[`get`](./get.md)`<i>(t) < std::`[`get`](./get.md)`<i>(u)` の比較結果が`bool`に変換可能な型であること。


##戻り値
2つの`tuple`オブジェクト、`t`と`u`の辞書順比較を行った結果を返す。定義は以下のようになる：

[`get`](./get.md)`<i>(t) < `[`get`](./get.md)`<i>(u) || !(`[`get`](./get.md)`<i>(u) < `[`get`](./get.md)`<i>(t)) && `[`get`](./get.md)`<i+N...>(t) < `[`get`](./get.md)`<i+N...>(u) ...`


##例
```cpp
#include <iostream>
#include <tuple>
#include <string>

int main()
{
  std::tuple<int, char, std::string> t1(1, 'a', "hello");
  std::tuple<int, char, std::string> t2(2, 'b', "world");

  std::cout << std::boolalpha;
  {
    bool result = t1 < t2;
    std::cout << result << std::endl;
  }
  {
    bool result = t2 < t1;
    std::cout << result << std::endl;
  }
}
```

###出力
```
true
false
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.6.1
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md) ??


##参照
