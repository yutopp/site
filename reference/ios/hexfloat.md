#hexfloat (C++11)
```cpp
namespace std {
  ios_base& hexfloat(ios_base& str);
}
```

##概要
浮動小数点数を十六進法で出力することを指示するマニピュレータ。

[`printf()`](http://linuxjm.sourceforge.jp/html/LDP_man-pages/man3/printf.3.html)関数の`%a`／`%A`相当。

##効果
`str.setf(ios_base::fixed | ios_base::scientific, ios_base::floatfield)`を実行する。

##戻り値
実引数の`str`オブジェクト。

##例
[`defaultfloat`](./defaultfloat.md)を参照。

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md):
- [GCC, C++0x mode](/implementation#gcc.md): ??
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md): 9.0, 10.0, 11.0

##参照
- [`defaultfloat`](./defaultfloat.md)
- [`fixed`](./fixed.md)
- [`scientific`](./scientific.md)
- [N1503 Proposed Additions to TR-1 to Improve Compatibility with C99](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2003/n1503.htm)

