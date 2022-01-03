# 操作系统中的线程状态

> 原文:[https://www . geesforgeks . org/操作系统中的线程状态/](https://www.geeksforgeeks.org/thread-states-in-operating-systems/)

当线程在系统中移动时，它总是处于五种状态之一:

```
(1) Ready
(2) Running
(3) Waiting
(4) Delayed
(5) Blocked 
```

不包括“创建”和“完成”状态。

![](img/3a08411c21d776aeccbd1ee2685cba1c.png)

1.  当要处理一个应用程序时，它会创建一个线程。
2.  然后，它被分配所需的资源(如网络)，并进入**就绪**队列。
3.  当线程调度器(类似进程调度器)给线程分配处理器时，它进入 **RUNNING** 队列。
4.  当流程需要触发一些超出其控制范围的其他事件时(就像另一个流程需要完成)，它会从 **RUNNING** 转换到 **WAITING** 队列。
5.  When the application has the capability to delay the processing of the thread, it when needed can delay the thread and put it to sleep for a specific amount of time. The thread then transitions from **RUNNING** to **DELAYED** queue.

    线程延迟的一个例子是警报的休眠。在它第一次响铃并且没有被用户关闭之后，它会在特定的时间之后再次响铃。在此期间，线程处于睡眠状态。

6.  当线程生成一个输入/输出请求，并且在完成之前不能进一步移动时，它会从 **RUNNING** 转换到 **BLOCKED** 队列。
7.  过程完成后，螺纹从**运行**过渡到**完成**。

**WAITING** 和 **BLOCKED** 转换的区别在于，在 WAITING 中，线程等待来自另一个线程的信号，或者等待另一个进程完成，这意味着突发时间是特定的。而在 BLOCKED 状态下，没有指定的时间(这取决于用户何时给出输入)。

为了成功执行所有进程，处理器需要通过**线程控制块(TCB)** 维护每个线程的信息。