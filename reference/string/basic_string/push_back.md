#push_back
```cpp
void push_back(charT c);
```

##概要
末尾に要素を追加する。


##効果
[`append`](./append.md)`(static_cast<size_type>(1), c)`


##例
```cpp
#include <iostream>
#include <string>

int main()
{
  std::string s = "hell";

  // 末尾に'o'を追加する
  s.push_back('o');

  std::cout << s << std::endl;
}
```

###出力
```
hello
```

##参照

