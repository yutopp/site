#milliseconds (C++11)
```cpp
namespace std {
namespace chrono {
  typedef duration<最低でも45ビットを持つ符号付き整数型, milli> milliseconds;
}}
```
* duration[link /reference/chrono/duration.md]

##概要
ミリ秒単位を表現する`duration`の別名

##例
```cpp
#include <iostream>
#include <chrono>

int main()
{
  std::chrono::milliseconds ns1(30);
  std::chrono::milliseconds ns2(20);

  std::chrono::milliseconds result = ns1 + ns2;

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

