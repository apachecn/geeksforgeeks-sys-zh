# 操作系统多线程的好处

> 原文:[https://www . geesforgeks . org/操作系统多线程的好处/](https://www.geeksforgeeks.org/benefits-of-multithreading-in-operating-system/)

先决条件–[操作系统-线程](https://www.geeksforgeeks.org/operarting-system-thread/)
多线程编程的优势可以分为四大类:

1.  **Responsiveness –**
    Multithreading in an interactive application may allow a program to continue running even if a part of it is blocked or is performing a lengthy operation, thereby increasing responsiveness to the user.

    在非多线程环境中，服务器监听某个请求的端口，当请求到来时，它会处理该请求，然后继续监听另一个请求。处理请求所花费的时间使得其他用户不必要地等待。相反，更好的方法是将请求传递给工作线程，并继续监听端口。

    例如，多线程网络浏览器允许用户在一个线程中进行交互，而视频被加载到另一个线程中。因此，用户可以继续查看网页的某些部分，而不是等待整个网页加载。

2.  **Resource Sharing –**
    Processes may share resources only through techniques such as-
    *   信息传递
    *   共用存储器

    程序员必须明确地组织这些技术。但是，默认情况下，线程共享其所属进程的内存和资源。
    共享代码和数据的好处是，它允许应用程序在同一地址空间内有多个活动线程。

3.  **经济–**
    从时间和空间的角度来看，为流程创建分配内存和资源是一项成本高昂的工作。
    由于线程与其所属的进程共享内存，因此创建和上下文切换线程更加经济。一般来说，创建和管理进程所花费的时间要比线程多得多。
    例如，在 Solaris 中，创建进程比创建线程慢 30 倍，上下文切换慢 5 倍。
4.  **可扩展性–**
    在多处理器架构的情况下，多编程的好处大大增加，在多处理器架构中，线程可能在多个处理器上并行运行。如果只有一个线程，那么就不可能将进程分成不同处理器可以执行的更小的任务。
    单线程进程只能在一个处理器上运行，不管有多少处理器可用。
    多 CPU 机器上的多线程增加了并行性。

参考资料-亚伯拉罕·西尔伯沙茨、彼得·加尔文和格雷格·加涅的操作系统概念