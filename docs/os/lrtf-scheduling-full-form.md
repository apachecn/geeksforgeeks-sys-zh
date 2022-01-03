# LRTF 调度全表

> 原文:[https://www.geeksforgeeks.org/lrtf-scheduling-full-form/](https://www.geeksforgeeks.org/lrtf-scheduling-full-form/)

**LRTF** 代表**最长剩余时间第一**。在 LRTF 调度算法中，具有最高突发时间的作业首先被分配 CPU。我们定期监控突发时间，并将最高突发时间进程分配给中央处理器。这是最长作业优先算法的抢先模式。

![LRTF-Full-Form](img/82222aa9620f0bf61d1d938ede64fc7e.png)

[LRTF](https://www.geeksforgeeks.org/longest-remaining-time-first-lrtf-cpu-scheduling-algorithm/) 是一种抢占式调度算法，比 LJF 增加了一个开销，因为 OS 经常监视 READY 队列中进程的 CPU 时间，并在必要时执行上下文切换。所有进程几乎同时完成执行，而不管它们的突发大小如何。

#### 特征

*   最长剩余时间优先是一种 CPU 调度算法，用于系统地确定所有传入进程中首先执行的进程。
*   它遵循先发制人的方法，即只为固定的时间段分配中央处理器。
*   进程选择的标准是最高的突发大小，并且该进程一直运行到固定的切片。选择过程再次发生。
*   这不是最佳调度算法，因为平均等待时间很长。

#### 优势

*   LRTF 算法简单，易于实现。
*   几乎所有的过程都在最长的作业完成时完成。
*   没有饥饿，因为所有进程都获得了公平的 CPU 份额。

#### 不足之处

*   上下文切换消耗了可用于执行进程的 CPU 宝贵时间。
*   较小的进程需要等待 CPU 完成较大的突发大小进程。
*   即使每个进程的突发时间少得多，平均等待时间和平均周转时间也高得多。