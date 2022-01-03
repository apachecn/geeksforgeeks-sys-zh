# 各种 CPU 调度算法的优缺点

> 原文:[https://www . geesforgeks . org/各种 cpu 调度算法的优缺点/](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-various-cpu-scheduling-algorithms/)

[CPU 调度](https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/)，涉及到很多不同的调度算法，各有利弊。

**1。[先到先得(FCFS)](https://www.geeksforgeeks.org/first-come-first-serve-cpu-scheduling-non-preemptive/) :**

*   Advantages-
    1.  Easy to understand.
*   Disadvantages–

1.  执行时间较少的流程会受到影响，即等待时间通常很长。
2.  倾向于中央处理器绑定进程，而不是输入/输出绑定进程。
3.  这里，第一个进程将首先获得中央处理器，其他进程只有在当前进程完成执行后才能获得中央处理器。现在假设第一个进程的突发时间比较大，其他进程的突发时间比较少，那么这些进程就要多等一些不必要的时间，这样就会导致*多等一些平均等待时间*，也就是[传达效果](https://www.geeksforgeeks.org/convoy-effect-operating-systems/)。
4.  这种效果会降低中央处理器和设备的利用率。
5.  FCFS 算法对于分时系统来说特别麻烦，在分时系统中，每个用户定期获得一份 CPU 是很重要的。

**2。[最短工作优先(SJF)【先发制人且非先发制人】](https://www.geeksforgeeks.org/program-for-shortest-job-first-or-sjf-cpu-scheduling-set-1-non-preemptive/) :**

*   Advantages-
    1.  The shortest job is favored.
    2.  It is provably optimal because it gives the minimum average waiting time of a given process set.
*   Disadvantages–
    1.  If a shorter process keeps coming, SJF may lead to hunger. This problem is solved by aging.
    2.  It can't be implemented at the short-term CPU scheduling level.

**3。[循环调度(RR)](https://www.geeksforgeeks.org/round-robin-scheduling-with-different-arrival-times/) :**

*   Advantages-
    1.  Each process gets an equal share of CPU.
    2.  RR is circular in nature, so there is no hunger.
*   Disadvantages–
    1.  Setting the range too short will increase the overhead and reduce the CPU efficiency, but setting it too long may result in poor response to short processes.
    2.  The average waiting time under RR policy is often longer.

**4。[基于优先级的(PB)](https://www.geeksforgeeks.org/program-for-priority-cpu-scheduling-set-1/?ref=rp) :**

*   Advantages-

1.  这提供了一个很好的机制，可以精确定义每个过程的相对重要性。

*   Disadvantages –
    1.  如果高优先级进程占用了大量的 CPU 时间，低优先级进程可能会挨饿并被无限期推迟。进程从未被安排运行的情况称为<u>饥饿</u>。
    2.  另一个问题是决定哪个进程获得分配给它的优先级。

    **5。[多级队列调度(MQS)](https://www.geeksforgeeks.org/multilevel-queue-mlq-cpu-scheduling/) :**

    *   Advantages-
        1.  Various processes can be individually scheduled.
            *   System–-FCFS
            *   Interaction–-SJF
            *   Batch processing–RR
            *   Student–PB

    1.  The lowest process faces the problem of hunger.

    **6。[多级反馈队列调度(MFQS)](https://www.geeksforgeeks.org/multilevel-feedback-queue-scheduling-mlfq-cpu-scheduling/) :**

    *   Advantages-
        1.  Low scheduling overhead.
        2.  Allow aging, so there is no hunger.
    *   Disadvantages–
        1.  Not flexible.
        2.  It also needs some means to take values for all parameters to define the optimal scheduler, so it is also the most complicated of <u>.</u>