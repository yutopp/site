#shared_from_this (C++11)
```cpp
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```
* shared_ptr[link /reference/memory/shared_ptr.md]

##概要
`this`ポインタを`shared_ptr`に変換する。


##要件
`*this`のインスタンスが[`shared_ptr`](/reference/memory/shared_ptr.md)オブジェクトとして共有されていること。


##戻り値
`this`ポインタを、`enable_shared_from_this`の派生クラス型`T`の[`shared_ptr`](/reference/memory/shared_ptr.md)オブジェクトとして構築して返す。


##例
```cpp
#include <cassert>
#include <memory>

struct X : public std::enable_shared_from_this<X> {
  std::shared_ptr<X> f()
  {
    // thisを指すshared_ptrオブジェクトを作る
    return shared_from_this();
  }
};

int main()
{
  std::shared_ptr<X> p(new X());
  std::shared_ptr<X> q = p->f();

  assert(p == q);
}
```

###出力
```
```

##バージョン
###言語
- C++11

###処理系
- [GCC, C++11 mode](/implementation#gcc.md): 4.3.6
- [Clang libc++, C++11 mode](/implementation#clang.md): 3.0
- [ICC](/implementation#icc.md): ?
- [Visual C++](/implementation#visual_cpp.md): ?
