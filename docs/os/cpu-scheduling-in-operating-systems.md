# 操作系统中的 CPU 调度

> 原文:[https://www . geesforgeks . org/CPU-操作系统调度/](https://www.geeksforgeeks.org/cpu-scheduling-in-operating-systems/)

安排流程/工作是为了按时完成工作。

下面是关于一个过程的不同时间。

> **到达时间:**进程到达就绪队列的时间。
> **完成时间:**流程完成执行的时间。
> **突发时间:**进程执行 CPU 所需的时间。
> **周转时间:**完工时间与到达时间的时间差。
> 周转时间=完成时间-到达时间
> 
> **等待时间(W.T):** 掉头时间和突发时间之间的时间差。
> 等待时间=周转时间-突发时间

**我们为什么需要排班？**
一个典型的过程涉及到 I/O 时间和 CPU 时间。在像微软操作系统这样的统一编程系统中，等待输入输出的时间被浪费了，在此期间中央处理器是空闲的。在多程序设计系统中，一个进程可以使用中央处理器，而另一个进程正在等待输入输出。这只有在进程调度的情况下才有可能。

**流程调度算法的目标**

> 最大 CPU 利用率[让 CPU 尽可能忙碌]
> CPU 的公平分配。
> 最大吞吐量【单位时间内完成执行的进程数】
> 最小周转时间【进程完成执行所花费的时间】
> 最小等待时间【进程在就绪队列中等待的时间】
> 最小响应时间【进程产生第一个响应的时间】

## **不同的调度算法**

***[【先到先得(FCFS)](https://www.geeksforgeeks.org/program-fcfs-scheduling-set-1/) :*** 根据流程到达时间进行调度的最简单调度算法。先来先服务调度算法规定先请求 CPU 的进程先分配 CPU。它是通过使用先进先出队列实现的。当一个进程进入就绪队列时，它的印刷电路板被链接到队列的尾部。当中央处理器空闲时，它被分配给队列头部的进程。然后，正在运行的进程将从队列中删除。FCFS 是一种非抢占式调度算法。

**注意:**先到先得受到[护航效果](https://www.geeksforgeeks.org/convoy-effect-operating-systems/)的影响。

***[【最短作业优先(SJF)](https://www.geeksforgeeks.org/program-shortest-job-first-sjf-scheduling-set-1-non-preemptive/) :*** 突发时间最短的进程被首先调度。如果两个过程具有相同的破裂时间，则使用 FCFS 来打破平局。它是一种非抢占式调度算法。

***最长作业优先(LJF):*** 类似于 SJF 调度算法。但是，在该调度算法中，我们优先考虑具有最长突发时间的进程。这在本质上是非抢先的，即当任何进程开始执行时，在完成执行之前不能被中断。

***[最短剩余时间优先(SRTF)](https://www.geeksforgeeks.org/program-shortest-job-first-scheduling-set-2srtf-make-changesdoneplease-review/) :*** 是 SJF 算法的抢占模式，按照最短剩余时间调度作业。

***[最长剩余时间优先(LRTF)](https://www.geeksforgeeks.org/cpu-scheduling-longest-remaining-time-first-lrtf-algorithm/) :*** 是 LJF 算法的抢占模式，我们优先选择剩余突发时间最大的进程。

***[循环调度](https://www.geeksforgeeks.org/program-round-robin-scheduling-set-1/) :*** 以循环方式为每个进程分配一个固定时间(时间段/时间片)。它是专门为分时系统设计的。就绪队列被视为循环队列。中央处理器调度程序绕过就绪队列，将中央处理器分配给每个进程，时间间隔最长为 1 个时间段。为了实现循环调度，我们将就绪队列作为进程的先进先出队列。新的进程被添加到就绪队列的尾部。中央处理器调度器从就绪队列中选择第一个进程，设置一个定时器在 1 个时间段后中断，并调度该进程。接下来会发生两件事中的一件。该进程可能具有小于 1 倍量程的中央处理器突发。在这种情况下，进程本身会主动释放 CPU。然后，调度程序将进入就绪队列中的下一个进程。否则，如果当前正在运行的进程的中央处理器突发长于 1 时间量，定时器将会关闭，并导致操作系统中断。将执行一个上下文切换，并且该进程将被放在就绪队列的尾部。然后，中央处理器调度程序将选择就绪队列中的下一个进程。

***[基于优先级的调度(非抢占式)](https://www.geeksforgeeks.org/operating-system-priority-scheduling-different-arrival-time-set-2/) :*** 在该调度中，进程根据优先级进行调度，即优先级最高的进程优先调度。如果两个进程的优先级匹配，则根据到达时间进行调度。在这里，过程饥饿是可能的。

***[最高响应率 Next (HRRN)](https://www.geeksforgeeks.org/operating-system-highest-response-ratio-next-hrrn-scheduling/) :*** 在此调度中，调度响应率最高的进程。这种算法避免了饥饿。

```
Response Ratio = (Waiting Time + Burst time) / Burst time
```

***[多级队列调度](https://www.geeksforgeeks.org/operating-system-multilevel-queue-scheduling/) :*** 根据流程的优先级，流程被放置在不同的队列中。通常，高优先级进程被放在顶层队列中。只有在顶级队列中的进程完成后，才会调度较低级别的排队进程。它会挨饿。

***[多级反馈队列调度](https://www.geeksforgeeks.org/multilevel-feedback-queue-scheduling/) :*** 它允许流程在队列之间移动。这个想法是根据进程的中央处理器突发的特征来分离进程。如果一个进程使用了太多的 CPU 时间，它就会被移到一个低优先级的队列中。

**关于调度算法的一些有用的事实:**

FCFS 会导致长时间的等待，尤其是当第一个作业占用太多的 CPU 时间时。*   **Both SJF and Shortest Remaining time first algorithms may cause starvation. Consider a situation when the long process is there in the ready queue and shorter processes keep coming.***   ****If time quantum for Round Robin scheduling is very large, then it behaves same as FCFS scheduling.*****   ******SJF is optimal in terms of average waiting time for a given set of processes,i.e., average waiting time is minimum with this scheduling, but problems are, how to know/predict the time of next job.

    **练习:**

    考虑一个需要 40 时间单位爆发时间的系统。使用了多级反馈队列调度，时间量是顶层队列的 2 个单位，并且在每一级增加 5 个单位，那么进程将在哪个队列中终止执行？*******   ******Which of the following is false about SJF?
    S1: It causes minimum average waiting time
    S2: It can cause starvation
    (A) Only S1
    (B) Only S2
    (C) Both S1 and S2
    (D) Neither S1 nor S2
    Answer (D)
    S1 is true SJF will always give minimum average waiting time.
    S2 is true SJF can cause starvation.*******   ******Consider the following table of arrival time and burst time for three processes P0, P1 and P2\. (GATE-CS-2011)

    ```
    Process   Arrival time   Burst Time
    P0            0 ms          9 ms
    P1            1 ms          4 ms
    P2            2 ms          9 ms
    ```

    使用了先发制人的最短作业优先调度算法。计划仅在流程到达或完成时执行。三个流程的平均等待时间是多少？
    (A) 5.0 毫秒
    (B) 4.33 毫秒
    (C) 6.33
    (D) 7.33
    解决方案:
    答案:–(A)
    由于就绪队列中没有其他进程，进程 P0 在 0 毫秒时被分配处理器。P0 在 1 毫秒后被抢占，因为 P1 到达 1 毫秒，而 P1 的突发时间小于 P0 的剩余时间。P1 跑了 4 英里。P2 在 2 毫秒到达，但 P1 继续，因为 P2 的爆发时间比 P1 长。P1 完成后，P0 被再次调度，因为 P0 的剩余时间小于 P2 的突发时间。
    P0 等待 4 ms，P1 等待 0 ms，P2 等待 11 ms，所以平均等待时间为(0+4+11)/3 = 5。****** *   ******Consider the following set of processes, with the arrival times and the CPU-burst times given in milliseconds (GATE-CS-2004)

    ```
      Process   Arrival Time    Burst Time
        P1          0              5
        P2          1              3
        P3          2              3
        P4          4              1
    ```

    使用抢先最短剩余处理时间优先(SRPT)算法，这些进程的平均周转时间是多少？
    (A)5.50
    (B)5.75
    (C)6.00
    (D)6.25
    答(A)
    解:
    以下为执行甘特图

    | 第一亲代 | P2 | P4 | P3 | 第一亲代 |
    | one | four | five | eight | Twelve |

    周转时间=完成时间-到达时间
    平均周转时间= (12 + 3 + 6+ 1)/4 = 5.50****** *   ******An operating system uses the Shortest Remaining Time first (SRTF) process scheduling algorithm. Consider the arrival times and execution times for the following processes:

    ```
    Process  Execution time  Arrival time
    P1             20            0
    P2             25            15
    P3             10            30
    P4             15            45
    ```

    P2 进程的总等待时间是多少？
    (A)5
    (B)15
    (C)40
    (D)55
    答案(B)
    在时间 0，P1 是唯一的进程，P1 运行 15 个时间单位。
    15 时，P2 到达，但 P1 剩余时间最短。所以 P1 又继续了 5 个时间单位。
    在时间 20，P2 是唯一的过程。所以它运行 10 个时间单位
    在时间 30，P3 是最短的剩余时间过程。所以它运行 10 个时间单位
    在时间 40，P2 运行，因为它是唯一的过程。P2 跑了 5 个时间单位。
    45 时，P3 到达，但 P2 剩余时间最短。所以 P2 又继续了 10 个时间单位。
    P2 在时间 55 完成其执行

    ```
    Total waiting time for P2 = Completion time - (Arrival time + Execution time)
                              = 55 - (15 + 25)
                              = 15
    ```

    更多问题请参考[CPU 调度小测验](https://www.geeksforgeeks.org/cpu-scheduling-gq/)。

    **参考文献:**
    [http://www . cs . UIC . edu/~ jbell/course notes/operating systems/5 _ CPU _ scheduling . html](http://www.cs.uic.edu/~jbell/CourseNotes/OperatingSystems/5_CPU_Scheduling.html)

    [http://codex . cs . Yale . edu/avi/OS-book/OS 8/OS 8c/slide-dir/pdf-dir/ch5 . pdf](http://codex.cs.yale.edu/avi/os-book/OS8/os8c/slide-dir/PDF-dir/ch5.pdf)

    如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论******