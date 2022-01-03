# 多级队列调度(MLQ)和最长作业优先(LJF)的区别

> 原文:[https://www . geeksforgeeks . org/difference-multi-level-queue-scheduling-mlq-和-最长-job-first-ljf/](https://www.geeksforgeeks.org/difference-between-multi-level-queue-scheduling-mlq-and-longest-job-first-ljf/)

**1。[多级队列调度(MLQ)](https://www.google.com/amp/s/www.geeksforgeeks.org/multilevel-queue-mlq-cpu-scheduling/amp/) :**
只有一个队列调度所有进程是相当困难的。这是使用多级队列调度的地方。在这种情况下，根据进程的属性，如系统进程、输入输出进程等，进程被分为不同的类别。因此，我们得到了 n 类进程的“n”个队列。每个队列都被分配了优先级，并且可以使用自己的调度算法，这使得同时使用许多调度算法变得方便。一般来说，队列的最高层具有最高优先级，当我们移动到较低层时，优先级会降低。如果上层具有相对于下层的绝对优先权，那么它是不可抢占的，否则如果时间片被划分在不同的队列中，那么它在本质上变成可抢占的。

*   **优势–**
    这个算法的主要优势是我们可以使用各种算法，比如 FCFS、SJF、LJF 等。同时在不同的队列中。
*   **缺点–**
    最底层的进程遭遇饥饿问题。

**2。[最长作业优先(LJF)](https://www.google.com/amp/s/www.geeksforgeeks.org/longest-job-first-ljf-cpu-scheduling-algorithm/amp/) :**
最长作业优先是一种非抢占式调度算法。该算法基于进程的突发时间。根据突发时间，即突发时间的降序，进程被放入就绪队列。顾名思义，该算法是基于这样一个事实，即首先处理突发时间最长的进程。只有那些在此之前已经到达系统的进程才被认为是突发时间。其抢先版称为[最长剩余时间优先(LRTF)算法](https://www.google.com/amp/s/www.geeksforgeeks.org/longest-remaining-time-first-lrtf-cpu-scheduling-algorithm/amp/)。

**注意–**
如果两个进程具有相同的突发时间，则使用 FCFS 断开连接，即先到达的进程先被处理。

**缺点–**

*   对于给定的一组进程，该算法给出了非常高的平均等待时间和平均周转时间。
*   这可能导致车队效应。
*   一个短的进程可能永远不会被执行，系统可能会继续执行更长的进程。
*   它降低了处理速度，从而降低了系统的效率和利用率。

**最长作业优先(LJF)和多级队列调度(MLQ)的区别:**

<center>

| 没有 | 最长工作优先(LJF) | 多级队列(MLQ) |
| --- | --- | --- |
| 1. | 它根据突发时间执行进程，即按照突发时间的降序。 | 进程的执行取决于该进程所属的特定队列级别的优先级。进程的进一步选择是基于特定队列中使用的算法类型。 |
| 2. | 它是非抢占式的，但它的抢占式版本也被称为最短剩余时间优先(SRTF)算法。 | 它可以是先发制人的，也可以是不先发制人的，这取决于具体情况。 |
| 3. | 给定进程集的平均等待时间相当长，这降低了系统的效率。 | 没有平均等待时间和响应时间的概念，因为它完全取决于在多级队列的各个级别中使用的算法。 |
| 4. | 长进程可能永远不会被执行，系统可能会继续执行短进程。 | 这会导致多级队列中较低级别的进程饥饿。 |

</center>