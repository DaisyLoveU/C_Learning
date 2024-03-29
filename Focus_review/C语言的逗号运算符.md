
## C语言中的逗号运算符  

  在 C 语言中，多个表达式可以用逗号分开，其中用逗号分开的表达式的值分别计算， 但整个表达式的值取最后一个表达式的值。  
  **注意：逗号运算的结合性是从左至右的，且逗号运算的优先级是最低的！最低！！最低！！！ **  
  

```c
#include "stdio.h"

int main()
{
    int i = 0, j = 0, k = 0;
    k = (j+2, i+5);
    printf("i = %d, j = %d, k = %d", i, j, k);
    return 0;
}
```

```
i = 0, j = 0, k = 5
```  

  
这里，k 取表达式的最后一项，即 i+5 的值  
  
下面  
```c
#include "stdio.h"

int main()
{
    int i = 0, j = 0, k = 0;
    k = j+2, i+5;
    printf("i = %d, j = %d, k = %d", i, j, k);
    return 0;
}
```

```
i = 0, j = 0, k = 2
``` 
  
这里，由于逗号分开的表达式的从左到右计算值，但是逗号运算符的优先级低于赋值运算符，所以 k 取 j+2 的值，整个逗号表达式的值仍是 i+5 的值  
  
下面再看一个关于结合性的例子  

```c
#include "stdio.h"

int main()
{
    int i = 5;
    int j = (i++, i++, i++, i++);
    printf("j = %d", j);
    return 0;
}
```
```
j = 9
```
  
这里，逗号运算符的结合性是自左向右的，所以四个 i ++ 会以此运行，最后的一个 i++ 的值赋值给 j, 即 j = 9
