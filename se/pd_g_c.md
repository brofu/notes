# How does C support generics

C has `type system`. And C supports generics by `void *` or `#define`

## Examples

```
// void *

viod swap(void* x, void* y, size_t size)
{
  char tmp[size]
  memcpy(tmp, y, size) //why memcpy
  memcpy(y, x, size)
  memcpy(x, tmp, size)
}
```
<center>Example. Generics by `void *` </center>


```
#define swap(x, y, size) {\
  char temp[size]; \
  memcpy(temp, &y, size); \
  memcpy(&y,   &x, size); \
  memcpy(&x, temp, size); \
}
```
<center>Example. Generics by `define` </center>

## Problems
There are several problems with these 2 implementations.


## More Stories

What about more complex situation? Let's check a `seach` function

```
// Search an element from an integer array

int search(int* a, size_t size, int target) {
  for(int i=0; i<size; i++) {
    if (a[i] == target) {
      return i;
    }
  }
  return -1;
}
```
<center>`search` function based on int and int array </center>


How to make this function support `generics`? To do this, we need consider 2 aspects:
  * Abstract data `Type` and
  * Abstract `operations` based on `Type`

For example:
  * We need to abstract the `Type` of the elements and the `operations` (here, we need abstract the `Equal` operation) based on the type. 
  * We need to abstract the `data containers` (instead of only `array`), and the `iteration operation` based on the containers

With this, the final solution would be like:
```
// Search an element from an integer array
// Version supports generics
int search(void* a, size_t size, void* target, size_t elemet_size, int(*cmpFn)(void*, void*)) {
  for (int i = 0; i < size; i ++) {
    if(cmpFn((unsigned char*)a + size_t * i, target) == 0) {
      return i;
    }
  }
  return -1
{

// More examples about `element type` and `operations`

// int
int int_cmp(int* x, int* y) {
  return *x - *y
}

// str
int str_cmp(char* x, char* y) {
  return strcmp(x, y)
}

// Or a struct
typedef struct _account {
  char name[10];
  char id[20];
} Account;
int account_cmp(Account* x, Account* y) {
  int n = strcmp(x->name, y->name);
  if (n != 0) return n;
  return strcmp(x->id, y->id);
}

```
<center><b>search</b> function PARTLY supports generics</center>

Actually, there are still problems with this version. For example,
  * The abstraction of `data container` is NOT implemented.
  * TBD


## Conclusions
* C 面向过程 `programmming generic`
* C is bad at `generics`
* To support `generics`, we need to abstract 2 aspects:
  * `data type` and `operations` based on them
  * `data struct` (also known as `data container`) and `operations` based on them

