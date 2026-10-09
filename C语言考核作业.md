1. 指针数组：本质是数组，数组中的元素是指针
   数组指针：本质是指针，指向一个数组

   函数指针：本质是指针，指向一个函数

   指针函数：本质是函数，返回值是指针

2. do while 和 while 的区别

while 是先判断条件，再执行循环体，循环体可能一次都不执行
do while 是先执行循环体，再判断条件，循环体至少执行一次

3. for 循环执行顺序

初始化 → 条件判断 → 执行循环体 → 执行循环变量更新 → 再次判断条件

4. 为什么 switch 要加 break

break 用于跳出 switch，防止执行完当前 case 后继续执行后面的 case，避免 case 穿透

5. char *s = "hello";
   *s = 'H';

有问题，"hello" 是字符串常量，不能通过指针修改其内容，修改会产生未定义行为

6. 冒泡排序

#include <stdio.h>

int main()
{
    int a[5] = {5, 3, 8, 1, 2};
    int i, j, temp;

    for (i = 0; i < 4; i++)
    {
        for (j = 0; j < 4 - i; j++)
        {
            if (a[j] > a[j + 1])
            {
                temp = a[j];
                a[j] = a[j + 1];
                a[j + 1] = temp;
            }
        }
    }
    
    for (i = 0; i < 5; i++)
    {
        printf("%d ", a[i]);
    }
    
    return 0;
}

7. #define 和 const 的区别

#define 是预处理阶段进行文本替换，没有类型检查
const 定义的是具有具体类型的只读变量，有类型检查

8. int fun(int a)
   {
   int b = 10;
   return &b;
   }

错误：函数返回类型是 int，而&b 是地址
 9.extern 的作用

extern 用于声明其他文件中定义的全局变量或函数，实现多文件之间的数据共享

extern int a;  ： 声明 a，表示 a 在其他地方定义
int a;  ： 定义全局变量 a。

10. volatile 的作用

volatile 告诉编译器，该变量的值可能随时被外部因素改变，使用时需要重新读取，不能随意进行优化。常用于硬件寄存器、中断等

11. #include "xxx.h" 和 #include <xxx.h>

"xxx.h"：通常优先在当前目录查找，常用于自己编写的头文件
<xxx.h>：通常在系统或编译器指定的目录中查找，常用于系统和库的头文件