# Decorator Pattern

## With Python

## With Golang

A common decorator

```
Decorator(decoPtr, fn interface{}) (err error) {
    var decoratedFunc, targetFunc reflect.Value
 
    decoratedFunc = reflect.ValueOf(decoPtr).Elem()
    targetFunc = reflect.ValueOf(fn)
 
    v := reflect.MakeFunc(targetFunc.Type(),
        func(in []reflect.Value) (out []reflect.Value) {
            fmt.Println("before")
            out = targetFunc.Call(in)
            fmt.Println("after")
            return
        })
 
    decoratedFunc.Set(v)
    return
}

```

## Reference
1. [dg][dg]
2. [rf][rf]

[dg]: https://time.geekbang.org/column/article/2723
[rf]: https://go.dev/blog/laws-of-reflection
