#assign (C++11)
```cpp
template <class InputIterator>
void assign(InputIterator first, InputIterator last);

void assign(size_type n, const T& t);
void assign(initializer_list<T>);
```
* initializer_list[link /reference/initializer_list.md]

##概要

コンテナの再代入
- `template <class InputIterator>`<br/>`void assign(InputIterator first, InputIterator last);`<br/>範囲を代入。効果：<br/>[`clear`](./clear.md)`();`<br/>[`insert_after`](./insert_after.md)`(`[`before_begin`](./before_begin.md)`(), first, last);`
- `void assign(size_type n, const T& t);`<br/>`n`個の値`t`を代入。効果：<br/>[`clear`](./clear.md)`();`<br/>[`insert_after`](./insert_after.md)`(`[`before_begin`](./before_begin.md)`(), n, t);`
- `void assign(`[`initializer_list`](/reference/initializer_list.md)`<T> init);`<br/>初期化子リストを代入。効果：<br/>[`clear`](./clear.md)`();`<br/>[`insert_after`](./insert_after.md)`(`[`before_begin`](./before_begin.md)`(), init.begin(), init.end());`


##戻り値
なし


##例
```cpp
#include <iostream>
#include <forward_list>
#include <string>

template <class T>
void print(const std::string& name, const std::forward_list<T>& ls)
{
  std::cout << name << " : ";
  for (const T& x : ls) {
    std::cout << x << ' ';
  }
  std::cout << std::endl;
}

int main()
{
  // 範囲を代入
  {
    std::forward_list<int> ls = {1, 2, 3};
    std::forward_list<int> ls1;
    ls1.assign(ls.begin(), ls.end());

    print("ls1", ls1);
  }

  // n個の指定された値で埋める
  {
    std::forward_list<int> ls2;
    ls2.assign(3, 1);

    print("ls2", ls2);
  }

  // 初期化子リストを代入
  {
    std::forward_list<int> ls3;
    ls3.assign({1, 2, 3});

    print("ls3", ls3);
  }
}
```
* assign[color ff0000]

###出力
```
ls1 : 1 2 3 
ls2 : 1 1 1 
ls3 : 1 2 3 
```

##バージョン
###言語
- C++11

###処理系
- [Clang](/implementation#clang.md): ??
- [GCC](/implementation#gcc.md): 
- [GCC, C++0x mode](/implementation#gcc.md): 4.7.0
- [ICC](/implementation#icc.md): ??
- [Visual C++](/implementation#visual_cpp.md) ??


##参照


