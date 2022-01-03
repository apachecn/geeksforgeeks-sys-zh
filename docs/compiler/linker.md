# 左

> 原文:[https://www.geeksforgeeks.org/linker/](https://www.geeksforgeeks.org/linker/)

先决条件–[编译器设计简介](https://www.geeksforgeeks.org/introduction-compiler-design/)
链接器是系统中的一个程序，它有助于将程序的目标模块链接到一个目标文件中。它执行链接的过程。链接器也称为链接编辑器。链接是将代码和数据收集和维护到一个文件中的过程。链接器还将特定模块链接到系统库中。它以汇编程序中的目标模块为输入，形成一个可执行文件作为加载程序的输出。

当源代码被翻译成机器代码时，链接在编译时执行，当程序被加载器加载到内存中时，链接在加载时执行。链接在编译程序的最后一步执行。

> 源代码->编译器->汇编器->目标代码->链接器->可执行文件->加载器

链接有两种类型:
**1。静态链接–**
在源程序编译时执行。链接是在静态链接中执行之前执行的。它收集可重定位的对象文件和命令行参数，并生成可以加载和运行的完全链接的对象文件。

静态链接器执行两个主要任务:

*   **符号分辨率–**它将每个符号引用与一个符号定义相关联。每个符号都有预定义的任务。
*   **重定位–**它重定位代码和数据部分，并修改对重定位的存储器位置的符号引用。

链接器将程序中使用的所有库例程复制到可执行映像中。因此，它需要更多内存空间。因为它运行时不要求系统上有库。所以，它更快，更便携。没有失败的机会，错误的机会更少。

**2。动态链接–**动态链接在运行期间执行。这种链接是通过在可执行映像中放置可共享库的名称来实现的。出错和失败的几率更大。它需要较少的内存空间，因为多个程序可以共享库的单个副本。

在这里，我们可以执行代码共享。这意味着我们在程序中多次使用同一个对象。每个模块与具有相同对象的其他模块共享一个对象的信息，而不是将相同的对象一次又一次地链接到库中。链接所需的共享库存储在虚拟内存中，以节省内存。在这个链接中，我们也可以重新定位代码，以保证代码的平稳运行，但是所有的代码都是不可重定位的。它在运行时修复地址。