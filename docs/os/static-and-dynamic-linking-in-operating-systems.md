# 操作系统中的静态和动态链接

> 原文:[https://www . geesforgeks . org/静态和动态操作系统链接/](https://www.geeksforgeeks.org/static-and-dynamic-linking-in-operating-systems/)

**静态链接:**
当我们点击。exe(可执行)文件，并且它开始运行时，二进制文件的所有必要内容都已加载到进程的虚拟地址空间中。但是，大多数程序也需要运行系统库中的函数，这些库函数也需要加载。

在最简单的情况下，必要的库函数直接嵌入到程序的可执行二进制文件中。这样的程序被静态链接到它的库，静态链接的可执行代码一旦被加载就可以开始运行。

**缺点:**
生成的每个程序都必须包含完全相同的公共系统库函数的副本。就物理内存和磁盘空间使用而言，只将系统库加载到内存中一次要高效得多。动态链接允许这种单一加载发生。

**动态链接:**
每个动态链接的程序都包含一个小的、静态链接的函数，该函数在程序启动时被调用。这个静态函数只将链接库映射到内存中，并运行函数包含的代码。链接库通过读取包含在库的部分中的信息来确定程序需要的所有动态库以及这些库中所需的变量和函数的名称。

之后，它将库映射到虚拟内存的中间，并解析对这些库中包含的符号的引用。我们不知道这些共享库在内存中的实际映射位置:它们被编译成位置无关的代码(PIC)，可以在内存中的任何地址运行。

**优势:**
程序内存需求降低。一个动态链接库只被加载到内存中一次，而多个应用程序可能会同时使用一个动态链接库，从而节省内存空间。应用程序支持和维护成本也降低了。