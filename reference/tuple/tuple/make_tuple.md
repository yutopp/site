#make_tuple (C++11)
```cpp
namespace std {
  template <class... Types>
  tuple<VTypes ...> make_tuple(Types&&...);
}
```

##概要
渡された可変個パラメータのコピーから`tuple`型のオブジェクトを構築する。


##戻り値
パラメータパックの値からなる`tuple`オブジェクト。


##例
```cpp
#include <tuple>
#include <string>
#include <functional> // ref, cref

int main()
{
  // 渡した値からtupleを構築
  std::tuple<int, char, const char*> t1 = std::make_tuple(1, 'a', "Hello");

  // tupleのコンストラクタによってconst char*をstd::stringに型変換
  std::tuple<int, char, std::string> t2 = std::make_tuple(1, 'a', "Hello");

  int a = 1;
  char b = 'b';
  std::string c = "hello";

  // 変数のコピーからtupleを構築
  std::tuple<int, char, std::string> t3 = std::make_tuple(a, b, c);

  // 変数の一部を参照と見なしてtupleを構築
  std::tuple<int, char&, const std::string&> t4 = std::make_tuple(a, std::ref(b), std::cref(c));
}
```
* make_tuple[color ff0000]

###出力
```
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ?
- [GCC](/implementation#gcc.md): ?
- [GCC, C++0x mode](/implementation#gcc.md): 4.6.1
- [ICC](/implementation#icc.md): ?
- [Visual C++](/implementation#visual_cpp.md) 9.0, 10.0


##参照


