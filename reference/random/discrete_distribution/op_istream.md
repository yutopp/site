#operator>> (C++11)
```cpp
namespace std {
  template <class CharT, class Traits, class IntType>
  basic_istream<CharT, Traits>& operator>>(
    basic_istream<CharT, Traits>& os
    discrete_distribution<IntType>& x);
}
```
* basic_istream[link /reference/iostream/basic_istream.md]

##概要
ストリームからの入力を行う。


##効果
`discrete_distribution`のパラメータを読み取り、オブジェクト`x`に格納する。  
不正な入力だった場合、`is.setstate(ios::failbit)`を呼び出し、ストリームを失敗状態にする。


##事後条件
`is`のフォーマットフラグが、この関数を呼び出す前の状態に戻ること。


##戻り値
`is`


##例
```cpp
#include <iostream>
#include <sstream>
#include <cassert>
#include <random>

int main()
{
  std::stringstream ss;

  // ストリームへ出力
  {
    std::discrete_distribution<> dist = {0.1, 0.2, 0.3};
    ss << dist;
  }

  // 出力結果を確認
  std::cout << ss.str() << std::endl;

  // 出力したストリームから読み込む
  {
    std::discrete_distribution<> dist;
    ss >> dist;

    assert(ss);
  }
}
```

###出力例
```
3 1.66666666666666657e-01 3.33333333333333315e-01 4.99999999999999889e-01
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.7.2
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md) ??


##参照


