# 地址绑定及其类型

> 原文:[https://www . geesforgeks . org/address-binding-and-its-type/](https://www.geeksforgeeks.org/address-binding-and-its-types/)

在本文中，我们将借助一个示例及其类型(如编译时、加载时和执行时地址绑定)来介绍地址绑定。我们一个一个来讨论。

**地址绑定:**
程序指令和数据与实际物理内存位置的关联称为地址绑定。为了更好地理解，让我们考虑下面给出的例子。

考虑一个程序，P1 有这样的指令集，I1，I2，I3，I4 和程序计数器值分别是 10，20，30，40。

```
Program P1
I1 --> 10 
I2 --> 20 
I3 --> 30 
I4 --> 40

Program Counter = 10, 20, 30, 40

```

![](img/47c0734980cdc02a84da1181137f44ec.png)

**地址绑定类型:**

地址绑定分为以下三种类型。

1.  [编译时地址绑定](https://www.geeksforgeeks.org/difference-between-compile-time-and-load-time-address-binding/)
2.  [加载时间地址绑定](https://www.geeksforgeeks.org/difference-between-compile-time-and-load-time-address-binding/)
3.  [执行时间地址绑定](https://www.geeksforgeeks.org/difference-between-compile-time-and-execution-time-address-binding/)

**编译时地址绑定:**

*   如果编译器负责执行地址绑定，那么它被称为编译时地址绑定。
*   这将在将程序加载到内存之前完成。
*   编译器需要与操作系统内存管理器交互来执行编译时地址绑定。

**加载时间地址绑定:**

*   它将在程序加载到内存后完成。
*   这种类型的地址绑定将由操作系统内存管理器(即加载程序)完成。

**执行时间或动态地址绑定:**

*   即使将程序加载到内存后，它也会被推迟。
*   在程序执行之前，程序会一直改变内存中的位置。
*   处理器在程序执行时完成的地址绑定的动态类型。

**注:**
大部分操作系统实际上实现了动态加载、动态链接、动态地址绑定。比如——Windows、Linux、Unix 都是流行的操作系统。