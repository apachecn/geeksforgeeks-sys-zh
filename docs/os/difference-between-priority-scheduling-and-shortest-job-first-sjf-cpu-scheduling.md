# 优先级调度和最短作业优先(SJF) CPU 调度的区别

> 原文:[https://www . geesforgeks . org/优先级调度和最短作业优先调度的区别/](https://www.geeksforgeeks.org/difference-between-priority-scheduling-and-shortest-job-first-sjf-cpu-scheduling/)

**1。[优先级调度算法](https://www.google.com/amp/s/www.geeksforgeeks.org/priority-cpu-scheduling-with-different-arrival-time-set-2/amp/) :**
优先级调度算法根据进程的优先级执行进程。每个进程被分配一个优先级，具有最高优先级的进程首先被执行。优先级可以在内部定义，也可以在外部定义。内部优先级由系统根据所需资源数量、所需时间等决定。而外部优先级是基于工作需要的时间、为完成的工作支付的金额或过程的重要性。优先级调度可以是抢占式的，也可以是非抢占式的。

**注–**

*   如果两个进程具有相同的优先级，则使用 FCFS 断开连接。
*   在抢占模式下，最高优先级进程的等待时间始终为零，而在非抢占模式下，等待时间可能不为零。

**劣势:**
主要问题是[饥饿](https://www.geeksforgeeks.org/starvation-and-aging-in-operating-systems/)或者无限期封锁。在进程流中，系统可能会一直执行高优先级的进程，而低优先级的进程永远不会被执行。

**2。[最短作业优先(SJF)](https://www.geeksforgeeks.org/program-for-shortest-job-first-or-sjf-cpu-scheduling-set-1-non-preemptive/) :**
最短作业优先(SJF)调度算法基于进程的突发时间。进程根据其突发时间被放入就绪队列。该算法首先处理突发时间最少的进程。仅比较那些在该时间之前存在或已经到达的进程的突发时间。它本质上也是非先发制人的。其抢先版称为[最短剩余时间优先(SRTF)算法](https://www.geeksforgeeks.org/introduction-of-shortest-remaining-time-first-srtf-algorithm/)。

该算法的主要优点是，它为给定的一组进程提供了最小的等待时间，从而减少了平均等待时间。这种算法的缺点是长进程可能永远不会被系统处理，并且可能在队列中停留很长时间，导致进程饥饿。

**注意–**
如果两个进程具有相同的突发时间，则使用 FCFS 断开连接，即先到达的进程先被处理。

最短作业优先(SJF)和优先级调度算法的区别如下:

<center>

| 最短工作优先(SJF) | 优先调度 |
| --- | --- |
| 最短作业优先(SJF)根据突发时间(即突发时间的升序)执行流程。 | 优先级调度根据进程的优先级执行进程，即按照优先级的降序。首先执行优先级较高的进程。 |
| SJF 也是非抢占式的，但它的抢占式版本也被称为最短剩余时间优先(SRTF)算法。 | 优先级调度本质上是先占和不先占的。 |
| 给定进程集的平均等待时间最短。 | 没有平均等待时间和响应时间的概念。 |
| SJF 的真正困难是知道下一个 CPU 请求或突发的长度。 | 它很容易实现，最适合实时操作系统。 |
| 长进程可能永远不会被执行，系统可能会继续执行短进程。 | 进程阻塞的问题可以通过老化来解决，老化意味着在固定的时间间隔后，将进程的优先级逐渐增加固定的数量。 |

</center>