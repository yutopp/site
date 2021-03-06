#new
```cpp
// 単純な記憶域の確保

void* operator new(std::size_t size);

// 単純な記憶域の確保（例外をスローしない）
void* operator new(std::size_t size, const std::nothrow_t&) noexcept;

// 単純な配列の記憶域の確保
void* operator new[](std::size_t size);

// 単純な配列の記憶域の確保（例外をスローしない）
void* operator new[](std::size_t size, const std::nothrow_t&) noexcept;

// 配置newによる記憶域の確保
void* operator new(std::size_t size, void* ptr) noexcept;

// 配置newによる配列の記憶域の確保
void* operator new[](std::size_t size, void* ptr) noexcept;
```
* nothrow_t[link /reference/new/nothrow_t.md]


##効果
プログラムが動的に記憶域を確保する。


##戻り値
確保した記憶域の先頭アドレスを指すポインタ。


##備考
一般にプログラム実行中の記憶域の動的確保は処理系がOSからヒープを割り当てるのに対し、placement-new では既にプログラムに割り当て済みの任意の記憶域を新たに確保を求められた際に便宜上割り当てる手法で、上手く使った場合は new / delete を大量に繰り返す必要のある処理を高速に実現しうる。


##例
```cpp
#include <iostream>
#include <new>

int main()
{
  try {
    // int型変数を動的に作成
    // 確保失敗時にbad_alloc例外が送出される
    int* p1 = new int();
    delete p1;

    // int型変数を動的に作成
    // 確保失敗時にヌルポインタが返される
    int* p2 = new (std::nothrow) int();
    delete p2;

    // 3要素のint型配列を動的に作成
    // 確保失敗時にbad_alloc例外が送出される
    int* p3 = new int[3];
    delete[] p3;

    // 3要素のint型配列を動的に作成
    // 確保失敗時にbad_alloc例外が送出される
    int* p4 = new (std::nothrow) int[3];
    delete[] p4;

    // char配列のスタック領域に、int型変数を動的に作成
    char one_field[sizeof(int)] = {};
    int* p5 = new(one_field) int();

    // char配列のスタック領域に、3要素のint型配列を動的に作成
    char array_field[sizeof(int) * 3] = {};
    int* p6 = new(array_field) int[3];
  }
  catch (std::bad_alloc& e) {
    std::cout << e.what() << std::endl;
    throw;
  }
}
```

###出力
```
```

