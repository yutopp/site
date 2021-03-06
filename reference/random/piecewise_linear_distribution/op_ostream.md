#operator<< (C++11)
```cpp
namespace std {
  template <class CharT, class Traits, class RealType>
  basic_ostream<CharT, Traits>& operator<<(
    basic_ostream<CharT, Traits>& os
    const piecewise_linear_distribution<RealType>& x);
}
```
* basic_ostream[link /reference/iostream/basic_ostream.md]

##概要
ストリームへの出力を行う。


##効果
`os`に対して、分布オブジェクト`x`の現在状態を出力する。


##事後条件
`os`のフォーマットフラグが、この関数を呼び出す前の状態に戻ること。


##戻り値
`os`


##例
```cpp
#include <iostream>
#include <random>
#include <array>

int main()
{
  std::array<double, 3> intervals = {0.0, 5.0, 10.0};
  std::array<double, 3> densities = {0.0, 0.5,  0.1};

  std::piecewise_linear_distribution<> dist(
    intervals.begin(),
    intervals.end(),
    densities.begin()
  );

  std::cout << dist << std::endl;
}
```

###出力例
```
2 0.00000000000000000e+00 5.00000000000000000e+00 1.00000000000000000e+01 0.00000000000000000e+00 1.81818181818181823e-01 3.63636363636363688e-02
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


