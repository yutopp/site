#sleep_for (C++11)
```cpp
namespace std {
namespace this_thread {
  template <class Rep, class Period>
  void sleep_for(const chrono::duration<Rep, Period>& rel_time);
}}
```
* duration[link /reference/chrono/duration.md]


##概要
指定した相対時間だけ現スレッドをブロックする。


##効果
引数 `rel_time`で指定した相対時間だけ現在のスレッド、すなわちこの関数を呼び出したスレッド自身をブロックする。指定した相対時間<i>以上</i>の時間が経過すると、現スレッドのブロックが解除されて後続処理の実行が開始される。なお、タイマーの精度は処理系依存。


##同期
特に他操作と同期しない。


##例外
[`chrono::duration<Rep, Period>`](/reference/chrono/duration.md)オブジェクトから例外送出しない限りは、この関数は例外送出しない。


##例
```cpp
#include <thread>

int main()
{
  // 3分間 現スレッドをブロック(Sleep)
  std::this_thread::sleep_for(std::chrono::minutes(3));

  return 0;
}
```
* std::this_thread::sleep_for[color ff0000]

###出力
```
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md):
- [GCC](/implementation#gcc.md):
- [GCC, C++0x mode](/implementation#gcc.md): 4.6.3, 4.7.0
- [ICC](/implementation#icc.md):
- [Visual C++](/implementation#visual_cpp.md):


##参照
