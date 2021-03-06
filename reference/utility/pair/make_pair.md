#make_pair
```cpp
namespace std {
  template <class T1, class T2>
  pair<V1, V2> make_pair(T1&& x, T2&& y);
}
```
* pair[link /reference/utility/pair.md]

##概要
pairクラスのオブジェクトを構築する。


C++03の場合、結果型の`V1`および`V2`は以下のような型となる：
- `V1` : `T1`
- `V2` : `T2`

C++11以降の場合、結果型の`V1`および`V2`は以下のような型となる：

`T1`と`T2`それぞれの型`T`において、
- `decay<T>::type`の結果型を使用し、
- かつ`T`が`reference_wrapper`型であった場合`T&`型を使用する


##戻り値
[`pair`](/reference/utility/pair.md)`<V1, V2>(`[`forward`](/reference/utility/forward.md)`<T1>(x), `[`forward`](/reference/utility/forward.md)`<T2>(y))`


##例
```cpp
#include <iostream>
#include <utility>
#include <functional>

int main()
{
  std::pair<int, char> p1 = std::make_pair(1, 'a');

  int ar[3] = {1, 2, 3};
  char c = 'b';

  // 配列はT*となり、reference_wrapper<T>はT&となる。
  std::pair<int*, char&> p2 = std::make_pair(ar, std::ref(c));
}
```
* make_pair[color ff0000]

###出力
```
```

##参照
