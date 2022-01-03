# 操作系统中的线程

> 原文:[https://www.geeksforgeeks.org/thread-in-operating-system/](https://www.geeksforgeeks.org/thread-in-operating-system/)

**什么是线？**
线程是进程内的执行路径。一个进程可以包含多个线程。
**为什么多线程？**
一种螺纹也称为轻量化工艺。其思想是通过将一个进程划分为多个线程来实现并行。例如，在浏览器中，多个选项卡可以是不同的线程。MS Word 使用多个线程:一个线程格式化文本，另一个线程处理输入等。多线程的更多优势在下面讨论
**进程 vs 线程？**
主要区别是同一个进程内的线程运行在共享内存空间，而进程运行在独立的内存空间。
线程不像进程那样相互独立，因此线程与其他线程共享它们的代码段、数据段和操作系统资源(比如打开的文件和信号)。但是，像进程一样，线程有自己的程序计数器(PC)、寄存器组和堆栈空间。
***螺纹相对于工艺的优势***
*1。响应性:*如果进程被分成多个线程，如果一个线程完成了它的执行，那么它的输出可以立即返回。

*2。更快的上下文切换:*线程之间的上下文切换时间比进程上下文切换要短。进程上下文切换需要更多的 CPU 开销。

*3。多处理器系统的有效利用:*如果我们在单个进程中有多个线程，那么我们可以在多个处理器上调度多个线程。这将使流程执行更快。

*4。资源共享:*像代码、数据和文件这样的资源可以在一个进程中的所有线程之间共享。
注意:堆栈和寄存器不能在线程间共享。每个线程都有自己的堆栈和寄存器。

*5。通信:*多线程之间的通信更容易，因为线程共享公共地址空间。在过程中，我们必须遵循一些特定通信技术来进行两个过程之间的通信。

*6。系统吞吐量增强:*如果一个进程被划分为多个线程，每个线程函数被认为是一个作业，那么单位时间内完成的作业数量就会增加，从而提高系统的吞吐量。
**螺纹类型**
螺纹有两种。
用户级线程
内核级线程
更多详情请参考[用户线程 vs 内核线程](https://www.geeksforgeeks.org/difference-between-user-level-thread-and-kernel-level-thread/)。

下面是往年在线程上的 gate 问题:
[https://www . geesforgeeks . org/gate-gate-cs-2011-question-16/](https://www.geeksforgeeks.org/gate-gate-cs-2011-question-16/)
[https://www . geesforgeeks . org/gate-gate-cs-2007-question-17/](https://www.geeksforgeeks.org/gate-gate-cs-2007-question-17/)
T7】https://www . geesforgeeks . org/gate-cs-2014-set-1-question-30/【T8

**参考:**
[C 中多线程](https://www.geeksforgeeks.org/multithreading-c-2/)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。