#equivalent (C++11)
```cpp
virtual bool equivalent(int code, const error_condition& condition) const noexcept;
virtual bool equivalent(const error_code& code, int condition) const noexcept;
```
* error_condition[link ../error_condition.md]
* error_code[link ../error_code.md]

##概要
エラーコードとエラー状態の等値比較を行う。


- `equivalent(int code, const error_condition& condition)`

`return default_error_condition(code) == condition;`

- `equivalent(const error_code& code, int condition)`

`return *this == code.category() && code.value() == condition;`


##例外
投げない


##例
```cpp
#include <iostream>
#include <system_error>
#include <string>
#include <cerrno>

int main()
{
  const std::error_category& cat = std::generic_category();

  std::error_code generic_ec(ENOTDIR, std::generic_category());
  std::error_code system_ec(ENOTDIR, std::system_category());

  std::cout << std::boolalpha;

  std::cout << cat.equivalent(ENOTDIR, generic_ec.default_error_condition()) << std::endl;
  std::cout << cat.equivalent(ENOTDIR, system_ec.default_error_condition()) << std::endl;

  std::cout << cat.equivalent(generic_ec, ENOTDIR) << std::endl;
  std::cout << cat.equivalent(system_ec, ENOTDIR) << std::endl;
}
```
* equivalent[color ff0000]

###出力
```
true
false
true
false
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
