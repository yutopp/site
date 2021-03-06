#operator!= (C++11)
```cpp
bool operator!=(const error_category& rhs) const noexcept;
```

##概要
`error_category`が異なるオブジェクトかどうかを判定する。 
異なるオブジェクトであれば`true`、そうでなければ`false`を返す。


##戻り値
`!(*this == rhs)`


##例外
投げない


##例
```cpp
#include <iostream>
#include <system_error>

int main()
{
  const std::error_category& a = std::generic_category();
  const std::error_category& b = std::generic_category();
  const std::error_category& c = std::system_category();

  std::cout << std::boolalpha;

  std::cout << (a != b) << std::endl;
  std::cout << (a != c) << std::endl;
}
```

###出力
```
false
true
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.6.1
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md) 10.0


##参照
