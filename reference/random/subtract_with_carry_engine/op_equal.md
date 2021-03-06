#operator== (C++11)
```cpp
namespace std {
  template <class UIntType, size_t w, size_t s, size_t r>
  bool operator==(
    const subtract_with_carry_engine<UIntType, w, s, r>& x,
    const subtract_with_carry_engine<UIntType, w, s, r>& y);
}
```

##概要
等値比較を行う。


##戻り値
`x`と`y`の状態シーケンスの、全ての値を等値比較し、等しければ`true`、そうでなければ`false`を返す。


##計算量
O(状態シーケンスのサイズ)


##例
```cpp
#include <iostream>
#include <random>

int main()
{
  std::ranlux24_base e1;
  std::ranlux24_base e2;

  if (e1 == e2) {
	std::cout << "equal" << std::endl;
  }
  else {
	std::cout << "not equal" << std::endl;
  }
}
```
* ranlux24_base[link /reference/random/ranlux24_base.md]

###出力
```
equal
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


