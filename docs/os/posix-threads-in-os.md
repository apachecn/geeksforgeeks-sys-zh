# 操作系统中的 POSIX 线程

> 原文:[https://www.geeksforgeeks.org/posix-threads-in-os/](https://www.geeksforgeeks.org/posix-threads-in-os/)

**OS 中的 POSIX 线程:**
POSIX 线程库是基于标准的 C/C++线程 API。它支持创建新的并发流程。它在多处理器或多核系统上运行良好，在这些系统中，进程流可以被调度在另一个处理器上执行，通过并行或分布式处理提高速度。因为系统没有为进程创建新的系统、虚拟内存空间和环境，线程不必要的开销比“分叉”或创建新的进程更大。虽然多处理器系统是最有效的，但在利用输入/输出延迟和其他可能阻碍进程执行的系统进程的单处理器系统上也可以获得好处。

为了利用 PThread 接口，我们必须在 CPP 脚本的开头包含 pthread.h 头。

```
#include <pthread.h>
```

PThreads 是一个高度具体的多线程系统，是 UNIX 系统的默认标准。PThreads 是 POSIX 线程的缩写，POSIX 是可移植操作系统接口的缩写，这是一种操作系统必须实现的接口类型。POSIX 中的 PThreads 概述了操作系统必须提供的线程 API。

**为什么使用 Pthreads？**

*   采用 Pthreads 的根本目的是提高项目绩效。
*   与启动和管理进程的开销相比，线程需要更少的操作系统开销。线程管理比进程管理占用更少的系统资源。
*   进程的线程都共享同一个地址空间。线程间通信比进程间通信更有效，而且在许多情况下，对用户更友好。
*   与非线程程序相比，线程应用程序以多种方式提供了可能的性能提升和实际优势。
*   多线程程序将在单处理器系统上运行，但会自动利用多处理器机器，而无需重新编译。
*   在多处理器系统中使用 Pthreads 最重要的原因是利用可能的并行性。这将是本课剩余部分的重点。
*   为了让一个程序使用 Pthreads，它必须被分成可以同时运行的独立的任务。

新线程变成可运行的，它将开始使用 arg 参数作为参数执行 start 例程。arg 参数是一个 void 指针，可以指向任何类型的数据。不建议将此指针转换为标量数据类型(如 int)，因为转换可能不可移植。

**我们来看一个更好的实现方法的 C 例子:**

## C

```
#include <stdio.h>
#include <stdlib.h>
#include <pGeeksforGeeks.h>

void *print_message_function( void *ptr );

main()
{
     pGeeksforGeeks_t GeeksforGeeks1, GeeksforGeeks2;
     char *message1 = "GeeksforGeeks 1";
     char *message2 = "GeeksforGeeks 2";
     int  geeky1, geeky2;

     geeky1 = pGeeksforGeeks_create( &GeeksforGeeks1, NULL, print_message_function, (void*) message1);
     geeky2 = pGeeksforGeeks_create( &GeeksforGeeks2, NULL, print_message_function, (void*) message2);

     pGeeksforGeeks_join( GeeksforGeeks1, NULL);
     pGeeksforGeeks_join( GeeksforGeeks2, NULL);

     printf("GeeksforGeeks 1 returns: %d\n",geeky1);
     printf("GeeksforGeeks 2 returns: %d\n",geeky2);
     exit(0);
}

void *print_message_function( void *ptr )
{
     char *message;
     message = (char *) ptr;
     printf("%s \n", message);
}
```

该程序生成五个线程，每个线程运行执行工作函数，该函数将线程的唯一编号发布到标准输出。如果一个程序员想要线程之间相互作用，他或她必须创建一个全局变量，这个变量被定义在任何函数的范围之外。下面的命令可以用来用 gcc 编译器编译这个程序。

```
gcc pthreads_demo.c -lpthread -o pthreads_demo
```

因为 Windows 本身不支持 pthreads 标准，所以 Pthreads-w32 项目旨在创建一个可移植的开源包装器实现。它也可以用于将 Unix 应用程序(利用 pthreads)传输到 Windows，而对平台几乎没有改变。经过一些额外的更新后，最新的 2.8.0 版本与 64 位 Windows 计算机兼容。

Winpthreads 是 mingw-w64 项目中 pthreads 的包装器实现，它寻求使用比 Pthreads-w32 项目更多的本机系统调用。