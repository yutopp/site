#nanoseconds (C++11)
```cpp
namespace std {

namespace chrono {
  typedef duration<最低でも64ビットを持つ符号付き整数型, nano> nanoseconds;
}}
```
* duration[link /reference/chrono/duration.md]

##概要
ナノ秒単位を表現する`duration`の別名

##例
```cpp
#include <iostream>
#include <chrono>

int main()
{
  std::chrono::nanoseconds ns1(30);
  std::chrono::nanoseconds ns2(20);

  std::chrono::nanoseconds result = ns1 + ns2;

  std::cout << result.count() << std::endl;
}
```

###出力
```
50
```

##バージョン
###言語
- C++11

###処理系
- [GCC, C++0x mode](/implementation#gcc.md): 4.6.1

