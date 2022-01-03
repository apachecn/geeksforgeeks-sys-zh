# 静态和动态范围

> 原文:[https://www.geeksforgeeks.org/static-and-dynamic-scoping/](https://www.geeksforgeeks.org/static-and-dynamic-scoping/)

程序区域中变量 x 的**作用域**，其中 x 的使用指的是它的声明。确定作用域的基本原因之一是保持程序不同部分的变量彼此不同。由于只有少量的短变量名，并且程序员共享关于变量命名的习惯(例如，数组索引的 I)，在任何中等大小的程序中，相同的变量名将在多个不同的作用域中使用。
范围界定一般分为两类:
**1。**静态范围
**2。**动态范围
**静态范围:**
静态范围也叫**词法范围**。在这个作用域中，变量总是引用它的顶层环境。这是程序文本的一个属性，与运行时调用堆栈无关。静态作用域还使模块化代码的制作变得更加容易，因为程序员只需查看代码就可以计算出作用域。相反，动态范围要求程序员预测所有可能的动态上下文。
在包括 C、C++和 Java 在内的大多数编程语言中，变量始终是静态(或词汇)范围的，即变量的绑定可以由程序文本决定，并且独立于运行时函数调用堆栈。
例如，下面程序的输出是 10，即 f()返回的值不依赖于谁在调用它(Like g()调用它，并且有一个值为 20 的 x)。f()始终返回全局变量 x 的值。

## C

```
// A C program to demonstrate static scoping.
#include<stdio.h>
int x = 10;

// Called by g()
int f()
{
   return x;
}

// g() has its own variable
// named as x and calls f()
int g()
{
   int x = 20;
   return f();
}

int main()
{
  printf("%d", g());
  printf("\n");
  return 0;
}
```

输出:

```
10
```

总而言之，在静态范围中，编译器首先在当前块中搜索，然后在全局变量中搜索，然后在连续更小的范围中搜索。
**动态范围:**
在动态范围中，全局标识符是指与最近的环境相关联的标识符，在现代语言中并不常见。用技术术语来说，这意味着每个标识符都有一个绑定的全局堆栈，并且在最近的绑定中搜索标识符的出现。
简单来说，在动态范围中，编译器首先搜索当前块，然后依次搜索所有调用函数。

## C

```
// Since dynamic scoping is very uncommon in
// the familiar languages, we consider the
// following pseudo code as our example. It
// prints 20 in a language that uses dynamic
// scoping.  

int x = 10;

// Called by g()
int f()
{
   return x;
}

// g() has its own variable
// named as x and calls f()
int g()
{
   int x = 20;
   return f();
}

main()
{
  printf(g());
}
```