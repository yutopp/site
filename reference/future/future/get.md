#get (C++11)
```cpp
R future::get();
R& future<R&>::get();
void future<void>::get();
```

##概要
結果を取得する


##効果
共有状態が準備完了状態([`future_status::ready`](../future_status.md))になるまで[`wait()`](./wait.md)で待機し、共有状態に格納されている値を取得する。


##戻り値
- `future::get()` ： 共有状態に格納されている値を返す。値が[`is_move_assignable`](/reference/type_traits/is_move_assignable.md)`<R>::value == true`であれば値をムーブして返し、そうでなければコピーで返す。
- `future<R&>::get()` ： 共有状態に格納されている参照を返す。
- `future<void>::get()` ： 何も返さない。


##例外
共有状態に例外が格納されていた場合、格納されている例外を送出する。


##事後条件
この関数呼び出し後は共有状態が破棄され、[`valid()`](./valid.md)` == false`となること。

つまりこの関数は1オブジェクトにつき1回しか呼び出せない。


##例
```cpp
#include <iostream>
#include <future>
#include <thread>
#include <utility>

void calc(std::promise<int> p)
{
  int sum = 0;
  for (int i = 0; i < 10; ++i) {
    sum += i + 1;
  }

  p.set_value(sum); // 結果値を書き込む
}

int main()
{
  std::promise<int> p;
  std::future<int> f = p.get_future();

  // 別スレッドで計算を行う
  std::thread t(calc, std::move(p));

  // calc()によって書き込まれた結果を取得
  std::cout << f.get() << std::endl;

  t.join();
}
```
* get[color ff0000]

###出力
```cpp
55
```

##例：`std::future<R&>`
```cpp
#include <iostream>
#include <future>
#include <thread>
#include <utility>
 
class Calculator {
  int sum_ = 0;
  std::future<int&> async_calc;
 
public:
  void start()
  {
    std::promise<int&> p;
    async_calc = p.get_future();
 
    std::thread t(&Calculator::calc, this, std::move(p));
    t.detach();
  }
 
  int get()
  {
    return async_calc.get(); // 結果値への参照を取得する
  }
 
  void calc(std::promise<int&> p)
  {
    int sum = 0;
    for (int i = 0; i < 10; ++i) {
      sum += i + 1;
    }
 
    sum_ = sum;
    p.set_value(sum_); // メンバ変数への参照を結果値として書き込む
  }
};
 
int main()
{
  Calculator c;
 
  // 非同期に計算を開始する
  c.start();
 
  // 計算結果を取得する
  int result = c.get();
 
  std::cout << result << std::endl;
}
```
* get[color ff0000]

###出力
```
55
```

##例：`std::future<void>`
```cpp
#include <iostream>
#include <future>
#include <thread>
#include <utility>
 
class Calculator {
  int sum_ = 0;
  std::future<void> async_calc;
 
public:
  void start()
  {
    std::promise<void> p;
    async_calc = p.get_future();
 
    std::thread t(&Calculator::calc, this, std::move(p));
    t.detach();
  }
 
  int get()
  {
    async_calc.get(); // 終了待機のみを行う
    return sum_;
  }
 
  void calc(std::promise<void> p)
  {
    int sum = 0;
    for (int i = 0; i < 10; ++i) {
      sum += i + 1;
    }
 
    // メンバ変数として結果を保持し、promiseでは計算終了の通知のみ行う
    sum_ = sum;
    p.set_value();
  }
};
 
int main()
{
  Calculator c;
 
  // 非同期に計算を開始する
  c.start();
 
  // 計算結果を取得する
  int result = c.get();
 
  std::cout << result << std::endl;
}
```
* get[color ff0000]

###出力
```
55
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.7.0
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md): 11.0


###備考
※ VC++11.0段階の`std::thread`クラスは、コンストラクタに引数をムーブで渡すことができない。そのため、`promise`オブジェクトはスレッド間の共有オブジェクトにする必要がある。(所有権が曖昧になるため、スタイルとしてはよくない)  
[#737812 - std::thread does not accept std::move](http://connect.microsoft.com/VisualStudio/feedback/details/737812)


##参照


