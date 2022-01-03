# 中央处理器调度标准

> 原文:[https://www.geeksforgeeks.org/cpu-scheduling-criteria/](https://www.geeksforgeeks.org/cpu-scheduling-criteria/)

不同的 [CPU 调度算法](https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/)有不同的属性，特定算法的选择取决于各种因素。已经提出了许多比较中央处理器调度算法的标准。

标准包括以下内容:

1.  **CPU 利用率–**
    任何 CPU 调度算法的主要目标都是让 CPU 尽可能忙碌。理论上，中央处理器利用率可以在 0 到 100 的范围内，但是在实时系统中，根据系统的负载，它在 40%到 90%之间变化。

2.  **吞吐量–**
    衡量 CPU 完成的工作量的指标是单位时间内正在执行和完成的进程数。这叫做吞吐量。吞吐量可能因过程的长度或持续时间而异。

3.  **周转时间–**
    对于特定流程，一个重要标准是执行该流程需要多长时间。从流程提交到完成的时间称为周转时间。周转时间是等待进入内存、在就绪队列中等待、在 CPU 中执行以及等待 I/O 所花费的时间总和

4.  **等待时间–**
    调度算法一旦开始执行，就不会影响完成流程所需的时间。它只影响进程的等待时间，即进程在就绪队列中等待的时间。

5.  **响应时间–**
    在交互系统中，周转时间并不是最好的标准。一个过程可以相当早地产生一些输出，并在先前的结果被输出给用户的同时继续计算新的结果。因此，另一个标准是从提交请求到产生第一个响应所用的时间。这种度量称为响应时间。

有各种各样的中央处理器调度算法，例如-

*   [先到先得(FCFS)](https://www.google.com/amp/s/www.geeksforgeeks.org/program-for-fcfs-cpu-scheduling-set-1/amp/)
*   [最短工作优先(SJF)](https://www.google.com/amp/s/www.geeksforgeeks.org/program-for-shortest-job-first-or-sjf-cpu-scheduling-set-1-non-preemptive/amp/)
*   [最长作业优先(LJF)](https://www.google.com/amp/s/www.geeksforgeeks.org/longest-job-first-ljf-cpu-scheduling-algorithm/amp/)
*   [优先调度](https://www.google.com/amp/s/www.geeksforgeeks.org/program-for-priority-cpu-scheduling-set-1/amp/)
*   [循环赛(RR)](https://www.google.com/amp/s/www.geeksforgeeks.org/program-round-robin-scheduling-set-1/amp/)
*   [最短剩余时间优先(SRTF)](https://www.google.com/amp/s/www.geeksforgeeks.org/introduction-of-shortest-remaining-time-first-srtf-algorithm/amp/)
*   [最长剩余时间优先(LRTF)](https://www.google.com/amp/s/www.geeksforgeeks.org/longest-remaining-time-first-lrtf-cpu-scheduling-algorithm/amp/)