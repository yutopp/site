#operator() (C++11)
```cpp
template <class URNG>
result_type operator()(URNG& g);

template <class URNG>
result_type operator()(URNG& g, const param_type& parm);
```

##概要
指定された値の範囲に基いて、乱数生成を行う。

パラメータを受け取るバージョンは、コンストラクタで設定されたパラメータの代わりに、`param`を乱数生成のパラメータとして使用する。


##戻り値
指定された確率に基いて、ランダムな値を生成して返す。  
確率[`p()`](./p.md)で`true`を生成し、確率`1 - `[`p()`](./p.md)で`false`を生成する。


##計算量
償却定数時間(`g()`の呼び出し回数)


##例
```cpp
#include <iostream>
#include <random>

int main()
{
  std::random_device seed_gen;
  std::mt19937 engine(seed_gen());

  std::cout << std::boolalpha;
  {
    std::bernoulli_distribution dist(0.5);

    for (int i = 0; i < 5; ++i) {
      bool result = dist(engine);
      std::cout << result << std::endl;
    }
  }

  // パラメータを渡すバージョン
  std::cout << std::endl;
  {
    typedef std::bernoulli_distribution dist_type;
    dist_type dist;

    for (int i = 0; i < 5; ++i) {
      dist_type::param_type param(0.5);
      bool result = dist(engine, param);
      std::cout << result << std::endl;
    }
  }
}
```


###出力例
```
false
false
false
true
true

true
false
false
true
true
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.7.2
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md) ??


##参照


