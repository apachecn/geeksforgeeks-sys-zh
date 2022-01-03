# C/c++中的加载程序

> 原文:[https://www.geeksforgeeks.org/loader-in-c-c/](https://www.geeksforgeeks.org/loader-in-c-c/)

**加载器**是**操作系统**的程序，**将可执行文件从磁盘加载到主内存中执行**。它将内存空间分配给主内存中的可执行模块，然后将控制权转移给程序的起始指令。

**示例:**

```
akash @aix(/ u / akash) #cat./ ak1.cpp
#include<stdio.h>
int main()
{
    printf("Testing of Loader !");
    return 0;
}
```

**由 xlC 编译器编译:**

> akash @ AIX(/u/akash)# XlC–o ak1 . out ./ak1 . CPP akash @ AIX(/u/akash)# ls–lrt ak1 *-rw–rw–r–1 akash dev 74 11 月 12 日 06:10 ak1 . CPP
> –rwxrwxr–x 1 akash dev 8562 11 月 12 日 06:34 ak1 . out akash @ AIX(/u/akash)#

**运行可执行文件时真正发生的事情:**同样可以使用 **strace** 命令。

> 赤色@ AIX(/u/赤色)# truss。/AK 1 . out〖t0〗执行(。/ak1.out "，0x 2 ff 20 a 00.0x 200138 a 8)argc:1
> read _ sys config(0x 0288.0x 00000010.0 xfffff 9.0x 10000000.0x 2007 bc.0x 000000 c 0.0x 06010000.0 xf076 a 0 F0)= 0x 00000000
> sbk(0x 00000000)= 0x 2009 98
> kwrite(1，“t 和 s t i n g 或 f L”-什么，19)= 19
> kfcnt(1，F_GETFL，0x 00000070)= 6710914
> kfcnt(2，F_GETFL，0x 2 ff 22 ffc)= 6710914
> _ exit(0)

显示的第一个调用是“ **execve()** ”，它实际上是加载程序。该加载程序创建的过程包括:

*   读取文件并为进程创建地址空间。
*   创建指令、数据和程序堆栈的页表条目，并初始化寄存器组。
*   然后，对程序的第一条指令执行跳转指令，这通常会导致页面错误，您的指令的第一页将被带入内存。

以下两点与加载程序无关，只是为了获得更多信息:

*   我们得到的另一个东西是带有参数值的 **kwrite** 调用，它被传递给我们程序中的 printf 函数。 **kwrite** 是一个系统调用，它实际上是从 printf 函数调用的，该函数负责向控制台显示传递给它的值。
*   我们还得到最后一条指令 **_exit(0)** 调用，这是一个 _exit 系统调用，参数状态为 0，表示返回操作系统，信号成功。从 return(0)语句调用了 This _exit。