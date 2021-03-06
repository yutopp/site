#swap (C++11)
```cpp
void swap(array& other) noexcept(noexcept(swap(declval<T&>(), declval<T&>())));
```
* swap[link /reference/utility/swap.md]
* declval[link /reference/utility/declval.md]

##概要
自身と他の`array`オブジェクトの値を入れ替える


##効果
[`swap_ranges`](/reference/algorithm/swap_ranges.md)`(`[`begin`](./begin.md)`(), `[`end`](./end.md)`(), other.`[`begin`](./begin.md)`())`


##戻り値
なし


##例外
`array`クラスの要素型`T`に対する`swap`操作が例外を投げない場合、この`swap`関数は決して例外を投げない。


##計算量
線形時間


##備考
`0`要素の場合(`N == 0`)、`noexcept(true)`となる。


##例
```cpp
#include <iostream>
#include <array>

#include <string>
#include <algorithm> // std::for_each

template <class T, std::size_t N>
void print(const std::string& name, const std::array<T, N>& ar)
{
  std::cout << name << " : ";
  std::for_each(ar.begin(), ar.end(), [](const T& x) {
    std::cout << x << ' ';
  });
  std::cout << std::endl;
}

int main()
{
  std::array<int, 3> x = {1, 2, 3};
  std::array<int, 3> y = {4, 5, 6};

  x.swap(y);

  print("x", x);
  print("y", y);
}
```
* swap[color ff0000]


###出力
```
x : 4 5 6 
y : 1 2 3 
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.7.0
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md): 9.0 (std::tr1), 10.0, 11.0


##参照

