#コンストラクタ (C++11)
```cpp
constexpr enable_shared_from_this() noexcept;                     // (1)
enable_shared_from_this(const enable_shared_from_this&) noexcept; // (2)
```

##enable_shared_from_thisオブジェクトの構築
- (1) デフォルトコンストラクタ
- (2) コピーコンストラクタ


##効果
- (1), (2) : `enable_shared_from_this<T>`オブジェクトを構築する


##バージョン
###言語
- C++11

###処理系
- [GCC, C++11 mode](/implementation#gcc.md): 4.3.6
- [Clang libc++, C++11 mode](/implementation#clang.md): 3.0
- [ICC](/implementation#icc.md): ?
- [Visual C++](/implementation#visual_cpp.md): ?
