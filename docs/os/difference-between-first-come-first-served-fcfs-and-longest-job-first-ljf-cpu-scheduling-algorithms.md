# 先到先得(FCFS)和最长作业优先(LJF) CPU 调度算法之间的差异

> 原文:[https://www . geeksforgeeks . org/先来先服务-FCFS-和最长作业-优先-ljf-CPU-调度-算法之差/](https://www.geeksforgeeks.org/difference-between-first-come-first-served-fcfs-and-longest-job-first-ljf-cpu-scheduling-algorithms/)

**1。[先到先得(FCFS)](https://www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/) :**
先到先得(FCFS)是最简单的算法类型。这是一种非抢占式算法，即进程一旦开始执行就不会被中断。FCFS 是在先进先出队列的帮助下实现的。流程按照到达时间的顺序被放入就绪队列。最先到达的进程成为队列的头，而后面到达的其他进程被添加到队列的后面。在先来先服务(FCFS)算法中，先到达的进程在 CPU 空闲时首先被发送给 CPU 执行。

这种算法的主要缺点是平均等待时间往往相当长。这也导致了[护航效果](https://www.geeksforgeeks.org/convoy-effect-operating-systems/)。这导致设备或中央处理器利用率较低，效率较低。

**2。最长作业优先(LJF) :**
最长作业优先(LJF)基于进程的突发时间。进程根据其突发时间被放入就绪队列。在该算法中，首先处理突发时间最大的进程。仅比较那些在该时间之前存在或已经到达的进程的突发时间。它本质上也是非先发制人的。其抢先版被称为[最长剩余时间优先(LRTF)算法](https://www.google.com/amp/s/www.geeksforgeeks.org/longest-remaining-time-first-lrtf-cpu-scheduling-algorithm/amp/)。

该算法的主要缺点是，对于给定的一组流程，它给出了非常高的平均等待时间和平均周转时间，因此降低了系统的有效性。

**注意–**
如果两个进程具有相同的突发时间，则使用 FCFS 断开连接，即先到达的进程先被处理。

先到先得(FCFS)和最长作业优先(LJF)调度算法的区别如下:

<center>

| 先到先得 | 最长工作优先(LJF) |
| --- | --- |
| 先到先得(FCFS)按照进程到达的顺序执行进程，即先到达的进程先执行。 | 最长作业优先(LJF)根据突发时间执行进程，即按照突发时间的降序。 |
| FCFS 本质上是非抢先的。 | LJF 也是非抢先的，但是它的抢先版本也被称为最长剩余时间优先(LRTF)算法。 |
| FCFS 导致进程等待时间很长，从而增加了平均等待时间。 | 给定流程集的平均等待时间和平均周转时间非常长。 |
| FCFS 算法在任何系统中都是最容易实现的。 | LJF 算法很难实现。 |
| 一个进程可能需要等待很长时间才能被执行，这取决于最先到达的进程的突发时间。 | 短进程可能永远不会被执行，系统可能会继续执行较长的进程。在多用户系统的情况下，这可能会导致用户觉得他的工作没有完成。 |
| FCFS 导致设备和 CPU 利用率降低，从而降低系统效率。 | LJF 导致非常低的处理速度，从而由于大的平均等待时间和周转时间而降低了系统的效率。 |
| FCFS 导致最小的开销。 | 在 LJF 的情况下，应该记录经过的时间，这会导致处理器上更多的开销，从而降低系统的吞吐量。 |

</center>