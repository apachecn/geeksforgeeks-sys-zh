# 线程上下文切换和进程上下文切换的区别

> 原文:[https://www . geesforgeks . org/线程上下文切换和进程上下文切换的区别/](https://www.geeksforgeeks.org/difference-between-thread-context-switch-and-process-context-switch/)

一个[程序](https://www.geeksforgeeks.org/difference-between-program-and-process/)是一组旨在执行特定任务的指令。因此，程序是一个被动的实体。

正在执行(正在运行)的程序称为[进程](https://www.geeksforgeeks.org/introduction-of-process-management/)。
因此，过程是一个活跃的实体。当一个程序运行时，它可能包含相应运行的各种线程。在单线程进程中，线程本身就是进程。而在多线程进程中，我们需要在不同的线程之间切换来执行我们的程序。

**1。[线程切换](https://www.geeksforgeeks.org/threads-and-its-types-in-operating-system/) :**
线程切换是同一进程中从一个线程到另一个线程的一种上下文切换。线程切换效率很高，成本也低得多，因为它只涉及到身份和资源的切换，比如程序计数器、寄存器和堆栈指针。线程到线程切换的成本与进入和退出内核的成本差不多。

**2。[进程切换](https://www.geeksforgeeks.org/introduction-of-process-management/) :**
进程切换是[上下文切换](https://practice.geeksforgeeks.org/problems/what-is-context-switching)的一种类型，在这里我们将一个进程切换到另一个进程。它涉及到所有流程资源与新流程所需资源的切换。这意味着切换内存地址空间。这包括内存地址、页表和内核资源，以及处理器中的缓存。

**线程上下文切换和进程上下文切换的区别:**

<center>

| 号码 |

</center>

线程上下文切换进程上下文切换1.当中央处理器保存线程的当前状态并切换到同一进程的另一个线程时，就会发生 TCS。当操作系统的调度程序保存运行程序的当前状态(包括印刷电路板的状态)并切换到另一个程序时，就会发生印刷电路板。2.TCS 帮助 CPU 同时处理多个线程。PCS 包括加载新程序的状态以供其执行。3.TCS 不涉及内存地址空间的切换。处理器帐户保存的所有内存地址。PCS 涉及内存地址空间的切换。处理器帐户的所有内存地址都会被刷新。4.处理器的高速缓存和转换后备缓冲器保持它们的状态。处理器的缓存和 TLB 被刷新。5.尽管 TCS 涉及寄存器和堆栈指针的切换，但它并不承担改变地址空间的成本。因此效率更高。PCS 涉及改变地址空间的巨大成本。因此效率较低。6.TCS 稍微快一点，便宜一点。PCS is relatively slower and costlier.