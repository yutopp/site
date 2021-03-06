#empty
```cpp
bool empty() const noexcept;
```

##概要
コンテナが空かどうかをテストする。 
`set` コンテナが空（[`size()`](./size.md) が 0）の場合に `true` を返す。 

この関数はコンテナ内のコンテンツを変化させない。コンテンツをクリアするには [`clear()`](./clear.md) メンバを使う。


##戻り値
コンテナサイズが 0 のときに `true`, そうでないときに `false`。


##計算量
定数時間。


##例
```cpp
#include <iostream>
#include <set>
using namespace std;
 
int main ()
{
  set<int> c;
 
  cout << c.empty() << endl;
  
  c.insert(42);
  
  cout << c.empty() << endl;
  
  return 0;
}
```

###出力
```
1
0
```

##参照

| | |
|---------------------------------------------------------------------------------------|-----------------------|
| [`insert`](./insert.md) | 要素を挿入する |
| [`(constructor)`](./set.md) | コンストラクタ |


