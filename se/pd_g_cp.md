# Generics In C++


## Key Characters of C++ (comparing with C)

> * 用引用来解决指针的问题。
* 用 namespace 来解决名字空间冲突的问题。
* 通过 try-catch 来解决检查返回值编程的问题。
* 用 class 来解决对象的创建、复制、销毁的问题，从而可以达到在结构体嵌套时可以深度复制的内存安全问题。
* 通过重载操作符来达到操作上的泛型。（比如，消除《01 | 编程范式游记：起源》中提到的比较函数cmpFn，再比如用>>操作符消除printf()的数据类型不够泛型的问题。）
* 通过模板 template 和虚函数的多态以及运行时识别来达到更高层次的泛型和多态。
* 用 RAII、智能指针的方式，解决了 C 语言中因为需要释放资源而出现的那些非常 ugly 也很容易出错的代码的问题。
* 用 STL 解决了 C 语言中算法和数据结构的 N 多种坑。

## Generics In C++

C++ support generics with 3 main approaches:
* Class
* Template
* 虚函数和运行时类型识别


## Conclusions
* Ideally, the `algorithm` should be `decoupled` with `data type` and `data struct` (`data container`). 
* So, `generics programming` should resolve the following aspects:
  * `allgorithm` supports generics
  * `data type` supports generics ==> Template
  * `data struct`  supports generics ==> Iterator


## Questions
* How to abstract `sum` function to a `reduce` function? A: Decouple `loop` and `operation`

## Reference

1. [https://time.geekbang.org/column/article/303](https://time.geekbang.org/column/article/303)
