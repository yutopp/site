#pop_back (C++11)
```cpp
void pop_back();
```

##概要
末尾の1要素を削除する。


##要件
`!`[`empty`](./empty.md)`()`


##効果
[`erase`](./erase.md)`(`[`size()`](./size.md)` - 1, 1)`


##例外
投げない


##例
```cpp
#include <iostream>
#include <string>

int main()
{
  std::string s = "helloo";

  // 末尾の`o`を1つ削除する
  s.pop_back();

  std::cout << s << std::endl;
}
```

###出力
```
hello
```

##バージョン
###言語
- C++11

###処理系
- [Clang, C++11 mode](/implementation#clang.md): 3.0
- [GCC, C++11 mode](/implementation#gcc.md): 4.7.3
- [ICC](/implementation#icc.md): ?
- [Visual C++](/implementation#visual_cpp.md): ?

