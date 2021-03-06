#iota (C++11)
```cpp
namespace std{
  template <class ForwardIterator, class T>
  void iota(ForwardIterator first, ForwardIterator last, T value);
}
```

##概要
指定された値から始まる整数列を生成する。

##パラメータ

| | |
|-------|--------------------------|
| `first` | シーケンスの先頭 |
| `last` | シーケンスの終端 |
| `value` | 初期値 |

##効果
全ての要素に対して、`first` から順番に `*it = value; ++value;` を行う


##戻り値
なし


##計算量
n 回のインクリメントと代入が行われる。


##例
```cpp
#include <numeric>
#include <iostream>
#include <string>

int main(){
  std::string s = "hello, iota!";
  std::cout << s << std::endl;
  std::iota(s.begin(), s.end(), 'A');
  std::cout << s << std::endl;
}
```
* std::iota[color ff0000]

###出力
```
hello, iota!
ABCDEFGHIJKL
```

##バージョン
###言語
- C++11

###処理系
- GCC: 4.5.0以降
- Visual C++ 9.0以降

##備考
この関数は、APL言語の「原始関数ι（イオタ）」に由来する。

