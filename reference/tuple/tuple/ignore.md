#ignore (C++11)
```cpp
namespace std {
  const unspecified ignore;

}
```
* unspecified[italic]

##概要
`ignore`は、[`tie()`](./tie.md)を使用してタプルから値を抽出する際に、「不要な値」をマーキングするためのプレースホルダーである。 
使用例は[`tie()`](./tie.md)を参照。


##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ?
- [GCC](/implementation#gcc.md): ?
- [GCC, C++0x mode](/implementation#gcc.md): 4.6.1
- [ICC](/implementation#icc.md): 
- [Visual C++](/implementation#visual_cpp.md) 9.0, 10.0


##参照
- [`std::make_tuple`](./make_tuple.md)
- [`std::forward_as_tuple`](./forward_as_tuple.md)
- [`std::tie`](./tie.md)

