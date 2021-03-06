#operator== (C++11)
```cpp
namespace std {
  template<class... TTypes, class... UTypes>
  bool operator==(const tuple<TTypes...>& t, const tuple<UTypes...>& u);
}
```
* tuple[link ../tuple.md]

##概要
2つの[`tuple`](../tuple.md)オブジェクトの等値比較を行う。


##要件
2つの[`tuple`](../tuple.md)オブジェクトの要素数が同じであること。 
[`tuple`](../tuple.md)の要素`std::`[`get`](./get.md)`<i>(t)`と`std::`[`get`](./get.md)`<i>(u)`において、すべての要素の比較 `std::`[`get`](./get.md)`<i>(t) == std::`[`get`](./get.md)`<i>(u)` の比較結果が`bool`に変換可能な型であること。

##効果
0番目の要素から順に等値比較を行う。


##戻り値
[`tuple`](../tuple.md)の全ての要素を`std::`[`get`](./get.md)`<i>(t) ==std::`[`get`](./get.md)`<i>(u)` した結果が`true`である場合`true`を返し、そうでなければ`false`を返す。


##例
```cpp
#include <iostream>
#include <tuple>
#include <string>

int main()
{
  std::tuple<int, char, const char*> t1(1, 'a', "hello");
  std::tuple<int, char, std::string> t2(1, 'a', "hello");
  std::tuple<int, char, std::string> t3(1, 'a', "hellot");

  std::cout << std::boolalpha;
  {
    bool result = t1 == t2; // ※型は異なっていてもかまわない
    std::cout << result << std::endl;
  }
  {
    bool result = t1 == t3;
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
