# 【FCFS 和 SJF CPU 调度算法的区别

> 原文:[https://www . geesforgeks . org/difference-FCFS-and-sjf-CPU-调度-算法/](https://www.geeksforgeeks.org/difference-between-fcfs-and-sjf-cpu-scheduling-algorithms/)

**1。[先到先得(FCFS)](https://www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/) :**
先到先得(FCFS)是最简单的算法类型。这是一种非抢占式算法，即进程一旦开始执行就不会被中断。FCFS 是在先进先出队列的帮助下实现的。流程按照到达时间的顺序被放入就绪队列。最先到达的进程成为队列的头，而后面到达的其他进程被添加到队列的后面。在先来先服务(FCFS)算法中，先到达的进程在 CPU 空闲时首先被发送给 CPU 执行。

这种算法的主要缺点是平均等待时间往往相当长。这也导致了[护航效果](https://www.geeksforgeeks.org/convoy-effect-operating-systems/)。这导致较低的设备或 CPU 利用率和较低的效率。

**2。[最短作业优先(SJF)](https://www.geeksforgeeks.org/program-for-shortest-job-first-or-sjf-cpu-scheduling-set-1-non-preemptive/) :**
最短作业优先(SJF)调度算法基于进程的突发时间。进程根据其突发时间被放入就绪队列。该算法首先处理突发时间最少的进程。仅比较那些在该时间之前存在或已经到达的进程的突发时间。它本质上也是非先发制人的。其抢先版称为[最短剩余时间优先(SRTF)算法](https://www.geeksforgeeks.org/introduction-of-shortest-remaining-time-first-srtf-algorithm/)。

该算法的主要优点是，它为给定的一组进程提供了最小的等待时间，从而减少了平均等待时间。这种算法的缺点是长进程可能永远不会被系统处理，并且可能在队列中停留很长时间，导致进程饥饿。

**注意–**
如果两个进程具有相同的突发时间，则使用 FCFS 断开连接，即先到达的进程先被处理。

先到先得(FCFS)和最短作业优先(SJF)调度算法的区别如下:

<center>

| 先到先得 | 最短工作优先(SJF) |
| --- | --- |
| 先到先得(FCFS)按照进程到达的顺序执行进程，即先到达的进程先执行。 | 最短作业优先(SJF)根据突发时间(即突发时间的升序)执行流程。 |
| FCFS 本质上是非抢先的。 | SJF 也是非抢占式的，但它的抢占式版本也被称为最短剩余时间优先(SRTF)算法。 |
| FCFS 导致进程等待时间很长，从而增加了平均等待时间。 | 给定进程集的平均等待时间最短。 |
| FCFS 导致车队效应。 | 它不会导致车队效应。 |
| FCFS 算法在任何系统中都是最容易实现的。 | SJF 的真正困难是知道下一个 CPU 请求或突发的长度。 |
| 一个进程可能需要等待很长时间才能被执行，这取决于最先到达的进程的突发时间。 | 长进程可能永远不会被执行，系统可能会继续执行短进程。 |
| FCFS 会降低设备和 CPU 利用率，从而降低系统效率。 | 由于平均等待时间较短，SJF 系统的效率较高。 |
| FCFS 导致最小的开销。 | 在 SJF 的情况下，应该记录经过的时间，这导致处理器上的更多开销。 |

</center>