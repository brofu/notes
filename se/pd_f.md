# Functional Programming


## Key Characters
> * stateless：函数不维护任何状态。函数式编程的核心精神是 stateless，简而言之就是它不能存在状态，打个比方，你给我数据我处理完扔出来。里面的数据是不变的。
> * immutable：输入数据是不能动的，动了输入数据就有危险，所以要返回新的数据集。

## Pros vs Cons

**Pros**
> * 没有状态就没有伤害。
> * 并行执行无伤害。
> * Copy-Paste 重构代码无伤害。
> * 函数的执行没有顺序上的问题。
> * 惰性求值。这需要编译器的支持，表达式不在它被绑定到变量之后就立即求值，而是在该值被取用的时候求值。也就是说，语句如 x:=expression; (把一个表达式的结果赋值给一个变量) 显式地调用这个表达式被计算并把结果放置到 x 中，但是先不管实际在 x 中的是什么，直到通过后面的表达式中到 x 的引用而有了对它的值的需求的时候，而后面表达式自身的求值也可以被延迟，最终为了生成让外界看到的某个符号而计算这个快速增长的依赖树。
> * 确定性。所谓确定性，就是像在数学中那样，f(x) = y 这个函数无论在什么场景下，都会得到同样的结果，而不是像程序中的很多函数那样。同一个参数，在不同的场景下会计算出不同的结果，这个我们称之为函数的确定性。所谓不同的场景，就是我们的函数会根据运行中的状态信息的不同而发生变化。

**Cons**
> * 数据复制比较严重。==> with `functional programming`, should NOT pass referenece into function?

## Key Tech Principles

下面是函数式编程用到的一些技术。

> * first class function（头等函数）函数就像变量一样来使用。函数可以像变量一样被创建、修改，并当成变量一样传递、返回，或是在函数中嵌套函数。
> * tail recursion optimization（尾递归优化) stack overflow. <sup>\[tr\]</sup>
> * map & reduce 
> * pipeline（管道）
> * recursing（递归）
> * urrying（柯里化)
> * higher order function


## Thinking Ways Of Functional Programming

> 函数式编程关注的是：describe what to do, rather than how to do it。我们把以前的过程式编程范式叫做 Imperative Programming – 指令式编程，而把函数式编程范式叫做 Declarative Programming – 声明式编程

* Map, Reduce and Filter
* pipeline model thinking

## Reference

1. [tr][tr]
2. [fp][fp]
3. [tr2][tr2]

[fp]:https://time.geekbang.org/column/article/2712
[tr]: https://en.wikipedia.org/wiki/Recursion_(computer_science)#Tail-recursive_functions]
[tr2]: https://zhuanlan.zhihu.com/p/350103441
