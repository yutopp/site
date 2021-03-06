#remove_pointer (C++11)
```cpp
namespace std {
  template <class T>
  struct remove_pointer {
    typedef … type;
  };
}
```

##概要
型からポインタを除去する。


##効果
`remove_pointer`は、型`T`が何らかの型`U`への(cv修飾された)ポインタである場合、型に含まれるポインタを除去した型`U`を、メンバ型`type`として定義する。そうでなければ、型`T`をそのままメンバ型`type`として定義する。  


##例
```cpp
#include <type_traits>

static_assert(std::is_same<std::remove_pointer<int>::type, int>::value, "transform int to int");
static_assert(std::is_same<std::remove_pointer<int*>::type, int>::value, "transform int* to int");
static_assert(std::is_same<std::remove_pointer<int**>::type, int*>::value, "transform int** to int*");
static_assert(std::is_same<std::remove_pointer<int&>::type, int&>::value, "transform int& to int&");
static_assert(std::is_same<std::remove_pointer<int*&>::type, int*&>::value, "transform int*& to int*&");

int main() {}
```

###出力
```
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): 3.0
- [GCC, C++0x mode](/implementation#gcc.md): 4.3.6
- [Visual C++](/implementation#visual_cpp.md): ??


