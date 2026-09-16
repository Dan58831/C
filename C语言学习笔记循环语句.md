# C 语言学习笔记循环

## 一、循环语句

循环语句就是让一段代码重复执行，在 C 语言中主要有：

while 循环

do...while循环

for循环

### 1. while 循环

基本格式：

```c
while(条件)
{
    循环体;
}
```

执行过程：

1. 先判断条件
2. 条件成立，执行循环体
3. 执行完以后再次判断条件
4. 条件不成立，结束循环

例如：

```c
#include <stdio.h>

int main()
{
    int i = 1;

    while(i <= 5)
    {
        printf("%d\n", i);
        i++;
    }

    return 0;
}
```

输出：12345

## 2.do...while 循环

基本格式：

```c
do
{
    循环体;
}while(条件);
```

和 while 的区别是：

do...while会先执行一次循环体，再判断条件。

例如：

```c
#include <stdio.h>

int main()
{
    int i = 1;

    do
    {
        printf("%d\n", i);
        i++;
    }while(i <= 5);

    return 0;
}
```



### 3. for 循环

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 5; i++)
    {
        printf("%d\n", i);
    }

    return 0;
}
```

执行过程大概是：

```text
i = 1
↓
判断 i <= 5
↓
执行循环体
↓
i++
↓
再次判断
```

for 循环在知道循环次数的时候比较常用

### 5. break

break的作用是 直接结束当前循环

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 10; i++)
    {
        if(i == 5)
        {
            break;
        }

        printf("%d ", i);
    }

    return 0;
}
```

输出：

1 2 3 4

当 i == 5 时执行 break，整个循环结束。



### 6. continue

continue 是跳过本次循环，直接进行下一次循环。

例如：

```c
#include <stdio.h>

int main()
{
    int i;

    for(i = 1; i <= 5; i++)
    {
        if(i == 3)
        {
            continue;
        }

        printf("%d ", i);
    }

    return 0;
}
```

输出：1 2 4 5

3 没有输出，但是循环没有结束。

break    → 结束整个循环
continue → 跳过本次循环

