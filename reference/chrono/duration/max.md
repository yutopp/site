#max (C++11)
```cpp
static constexpr duration max();
```

##概要
`rep`の最大値から成る`duration`を取得する

##戻り値
`duration(`[`duration_values`](/reference/chrono/duration_values.md)`<rep>::`[`max`](/reference/chrono/duration_values/max.md)`())`


##例
```cpp
#include <iostream>
#include <chrono>

using std::chrono::duration;
using std::micro;

int main()
{
  typedef duration<int, micro> microseconds;

  microseconds m = microseconds::max();
  std::cout << m.count() << std::endl;
}
```
* max()[color ff0000]


###出力例
```
2147483647
```

##バージョン
###言語
- C++11

###処理系
- GCC: 4.5.1, 4.6.1

