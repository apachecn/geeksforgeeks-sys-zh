# 操作系统中的线程及其类型

> 原文:[https://www . geeksforgeeks . org/操作系统中的线程及其类型/](https://www.geeksforgeeks.org/threads-and-its-types-in-operating-system/)

线程是进程中的单个序列流。线程具有与进程相同的属性，因此它们被称为轻量进程。线程一个接一个地执行，但给人一种好像它们是并行执行的错觉。每个线程都有不同的状态。每个线程都有

1.  一个程序计数器

2.  寄存器组

3.  一个堆栈空间

线程并不是相互独立的，因为它们共享代码、数据、操作系统资源等。

**线程和进程之间的相似性–**

*   一次只有一个线程或进程处于活动状态

*   在过程中，两者都按顺序执行

*   两者都可以创建子代

**线程和进程之间的差异–**

*   线程不是独立的，进程才是。

*   线程被设计成相互辅助，进程可以做也可以不做

**螺纹类型:**

1.  **User Level thread (ULT) –** 
    Is implemented in the user level library, they are not created using the system calls. Thread switching does not need to call OS and to cause interrupt to Kernel. Kernel doesn’t know about the user level thread and manages them as if they were single-threaded processes. 

    **ULT 优势–**

    *   可以在不支持多线程的操作系统上实现。

    *   简单的表示，因为线程只有程序计数器，寄存器组，堆栈空间。

    *   创建简单，因为没有内核的干预。

    *   线程切换很快，因为不需要进行操作系统调用。

    *   线程和内核之间没有或很少协调。

    *   如果一个线程导致页面错误，整个进程就会阻塞。

2.  **Kernel Level Thread (KLT) –** 
    Kernel knows and manages the threads. Instead of thread table in each process, the kernel itself has thread table (a master one) that keeps track of all the threads in the system. In addition kernel also maintains the traditional process table to keep track of the processes. OS kernel provides system call to create and manage threads. 

    **KLT 优势–**

    *   由于内核对系统中的线程有充分的了解，调度程序可能会决定给有大量线程的进程更多的时间。

    *   适用于经常阻塞的应用程序。

    *   缓慢而低效。

    *   它需要线程控制块，所以这是一个开销。

**总结:**

1.  每个 ULT 都有一个使用线程表跟踪线程的进程。

2.  每个 KLT 都有线程表和进程表。