#コンストラクタ (C++11)
```cpp
explicit lock_guard(mutex_type& m);
lock_guard(mutex_type& m, adopt_lock_t);

lock_guard(lock_guard const&) = delete;
```
* adopt_lock_t[link /reference/mutex/adopt_lock.md]

##lock_guardオブジェクトの構築
- `explicit lock_guard(mutex_type& m);`<br/>非ロック状態のミューテックスオブジェクトへの参照を受け取り、メンバ変数として参照を保持する。<br/>効果： `m.lock()`
- `lock_guard(mutex_type& m, adopt_lock_t);`<br/>ロック済みミューテックスオブジェクトへの参照を受け取り、メンバ変数として参照を保持する。<br/>例外： 投げない
- `lock_guard(lock_guard const&) = delete;`<br/>コピーコンストラクタ。コピー不可。<br/>非自明なコンストラクタが定義されているため、ムーブコンストラクタは定義されない


##例
```cpp
#include <iostream>
#include <mutex>

int main()
{
  std::mutex mtx;

  {
    std::lock_guard<std::mutex> lk(mtx); // ロックを取得する

    // ...共有リソースにアクセス...

  } // ロックを手放す

  {
    mtx.lock();
    std::lock_guard<std::mutex> lk(mtx, std::adopt_lock); // ロック済みミューテックスを渡す

    // ...共有リソースにアクセス...

  } // ロックを手放す
}
```

###出力
```
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.7.0
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md) ??


##参照


