#clear
```cpp
void clear() noexcept;
```

##概要
`multimap` コンテナ内の全ての要素を削除する。それぞれのデストラクタが呼ばれ、コンテナから削除される。[`size()`](/reference/map/multimap/size.md) は 0 になる。


##計算量
線形時間


##例
```cpp
#include <iostream>
#include <map>

using namespace std;

int main() 
{
  multimap<int, char> c;
  c.insert( std::make_pair(3,'C'));
  c.insert( std::make_pair(4,'D'));
  c.insert( std::make_pair(1,'A'));
  c.insert( std::make_pair(2,'B'));

  std::cout << c.size() << endl;

  c.clear();

  std::cout << c.size() << endl;

  return 0;
}
```

###出力
```
4
0
```

##バージョン
###言語
- C++03

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): ??
- [GCC, C++11 mode](/implementation#gcc.md): ??
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md): ??, 11.0

##参照

| 名前 | 説明 |
|-------------------------------------------------------------------------------------|-----------------------------------------------------|
| [`multimap::erase`](/reference/map/multimap/erase.md) | 要素を削除する |
| [`multimap::size`](/reference/map/multimap/size.md) | 要素数を取得する |
| [`multimap::empty`](/reference/map/multimap/empty.md) | コンテナが空であるかどうかを調べる |



