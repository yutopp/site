#論理反転関数オブジェクト
```cpp
namespace std {
  template <typename Pred>
  struct unary_negate {
    explicit unary_negate(const Pred &pred);
    bool operator()(const typename Pred::argument_type &x) const;
    typedef typename Pred::argument_type argument_type;
    typedef bool result_type;
  };

  template <typename Pred>
  unary_negate<Pred> not1(const Pred &pred);

  template <typename Pred>
  struct binary_negate {
    explicit binary_negate(const Pred &pred);
    bool operator()(const typename Pred::first_argument_type &x, const typename Pred::second_argument_type &y) const;
    typedef typename Pred::first_argument_type first_argument_type;
    typedef typename Pred::second_argument_type second_argument_type;
    typedef bool result_type;
  };

  template <typename Pred>
  binary_negate<Pred> not2(const Pred &pred);
}
```

##概要
述語関数オブジェクトの結果を反転する関数オブジェクトアダプタ。`unary_negate` は1引数述語用、 `binary_negate` は2引数述語用。


テンプレート引数 `Pred` に対する要求
- `unary_negate`の場合
- 型`Pred`に`argument_type`という nested typedef が存在すること
- 型`Pred`への`const`参照`pred`に対して、式 `(bool)pred(x)` が有効であること。ただし `x` は `argument_type` への `const` 参照。
- `binary_negate`の場合
- 型`Pred`に`first_argument_type`、`second_argument_type`という nested typedef が存在すること
- 型`Pred`への`const`参照`pred`に対して、式 `(bool)pred(x, y)` が有効であること。ただし `x` と `y` は、それぞれ `first_argument_type` と `second_argument_type` への `const` 参照。メンバ関数

| | |
|----------------------------------------------|------------------------------------|
| `unary_negate<Pred>::operator()` | `!pred(x)` と等価 |
| `binary_negate<Pred>::operator()` | `!pred(x, y)` と等価 |

###メンバ型

| | |
|-----------------------------------|------------------------------------------------------------------------------------------------|
| `argument_type` | (`unary_negate`のみ) `typename Pred::argument_type` と等価 |
| `first_argument_type` | (`binary_negate`のみ) `typename Pred::first_argument_type` と等価 |
| `second_argument_type` | (`binary_negate`のみ) `typename Pred::second_argument_type` と等価<br/> |
| `result_type` | `bool` |
フリー関数 

| | |
|-------------------------------------|--------------------------------------------------------------|
| `not1(const Pred& pred)` | `unary_negate<Pred>(pred)` を構築して返す |
| `not2(const Pred& pred)` | `binary_negate<Pred>(pred)` を構築して返す |

###例
```cpp
#include <iostream>
#include <functional>

int main()
{
  std::cout << std::boolalpha << std::not2(std::less<int>())(3, 5) << std::endl;
}
```

###出力
```
false
```

