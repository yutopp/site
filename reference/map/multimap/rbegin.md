#rbegin
```cpp
reverse_iterator rbegin() noexcept;
const_reverse_iterator rbegin() const noexcept;
```

##概要
`multimap` コンテナ内の最後の要素を指す逆イテレータを返す。 
内部的に、`multimap` コンテナは各要素をキーの値に従って下位から上位へと並べており、従って `rbegin()` は最上位のキーにあたる値を返す。 
`rbegin()` は [`end()`](/reference/map/multimap/end.md) と同じ要素を指すわけではなく、その前の要素を指すことに注意。


##戻り値
反転したシーケンスの先頭を指す逆イテレータ。 
`reverse_iterator` と `const_reverse_iterator` はともにメンバ型である。`multimap` クラステンプレートにおいて、これらは逆双方向イテレータであり、それぞれ `reverse_iterator<iterator>`, `reverse_iterator<const_iterator>` と定義される。


##計算量
定数時間。


##例
```cpp
#include <iostream>
#include <map>
using namespace std;

int main()
{
  multimap<int, char> c;
  c.insert(std::make_pair(5, 'e'));
  c.insert(std::make_pair(2, 'b'));
  c.insert(std::make_pair(4, 'd'));
  c.insert(std::make_pair(1, 'a'));
  c.insert(std::make_pair(1, 'a'));

  multimap<int,char>::reverse_iterator i = c.rbegin();
  for( ; i != c.rend() ; ++i )
    cout << i->first << " " << i->second << endl;

  return 0;
}
```

###出力
```
5 e
4 d
2 b
1 a
1 a
```

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): ??
- [GCC, C++11 mode](/implementation#gcc.md): ??
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md): ??, 11.0


##参照
| 名前 | 説明 |
---------------------------------------------------------------------------------------------|--------------------------------------------------|
| [`multimap::begin`](/reference/map/multimap/begin.md) | 先頭を指すイテレータを取得する |
| [`multimap::end`](/reference/map/multimap/end.md) | 末尾を指すイテレータを取得する |
| [`multimap::cbegin`](/reference/map/multimap/cbegin.md) | 先頭を指すconstイテレータを取得する |
| [`multimap::cend`](/reference/map/multimap/cend.md) | 末尾を指すconstイテレータを取得する |
| [`multimap::rend`](/reference/map/multimap/rend.md) | 先頭を指す逆イテレータを取得する |
| [`multimap::crbegin`](/reference/map/multimap/rbegin.md) | 末尾を指す逆constイテレータを取得する |
| [`multimap::crend`](/reference/map/multimap/rend.md) | 先頭を指す逆constイテレータを取得する |
