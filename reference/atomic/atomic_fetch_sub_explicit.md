#atomic_fetch_sub_explicit (C++11)
```cpp
namespace std {
  template <class T>
  T atomic_fetch_sub_explicit(volatile atomic<T>* object, T operand, memory_order order) noexcept;

  template <class T>
  T atomic_fetch_sub_explicit(atomic<T>* object, T operand, memory_order order) noexcept;
}
```
* atomic[link ./atomic.md]
* memory_order[link ./memory_order.md]

##概要
アトミックに減算を行う


##効果
`order`で指定されたメモリオーダーにしたがって、現在の値に`operand`を減算した値でアトミックに置き換える


##戻り値
変更前の値が返される


##例外
投げない


##備考
符号付き整数型に対しては、2の補数表現による演算が行われ、未定義動作はない。アドレス型に関しては結果として未定義アドレスになる場合があるが、それ以外の未定義動作はない。


##例
```cpp
#include <iostream>
#include <atomic>

int main()
{
  std::atomic<int> x(3);

  int before = std::atomic_fetch_sub_explicit(&x, 2, std::memory_order_seq_cst);

  std::cout << before << std::endl;
  std::cout << x.load() << std::endl;
}
```
* atomic_fetch_sub_explicit[color ff0000]


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
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.7.0
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md) ??


##参照


