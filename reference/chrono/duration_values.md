#duration_values
```cpp
namespace std {
namespace chrono {
  template <class Rep>
  struct duration_values;
}}
```

##概要
`duration_values`は、[`duration`](/reference/chrono/duration.md)クラスにおいて、内部表現の特別な値を取得するために使われるトレイトである。


##静的メンバ関数

| 名前 | 説明 | 対応バージョン |
|-------------------------------------|---------------------|-------|
| [`zero`](./duration_values/zero.md) | `Rep`の初期値を取得 | C++11 |
| [`min`](./duration_values/min.md)   | `Rep`の最小値を取得 | C++11 |
| [`max`](./duration_values/max.md)   | `Rep`の最大値を取得 | C++11 |


###言語
- C++11

###処理系
- [GCC, C++0x mode](/implementation#gcc.md): 4.6.1


