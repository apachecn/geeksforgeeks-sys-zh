# 操作系统|第 12 集

> 原文:[https://www.geeksforgeeks.org/operating-systems-set-12/](https://www.geeksforgeeks.org/operating-systems-set-12/)

GATE CS 2007 考试提出了以下问题。

**1)考虑具有 16 个表面、每个表面 128 个磁道和每个磁道 256 个扇区的磁盘组。512 字节的数据以位串行方式存储在一个扇区中。磁盘组的容量和指定磁盘中特定扇区所需的位数分别是:**
(A) 256 兆字节，19 位
(B) 256 兆字节，28 位
(C) 512 兆字节，20 位
(D) 64 兆字节，28 位

答案(A)
磁盘容量= 16 个表面×128 个磁道×256 个扇区×512 字节= 256 兆字节。
要计算访问一个扇区所需的位数，我们需要知道扇区的总数。扇区总数= 16 个表面×128 个磁道×256 个扇区= 2^19
因此访问一个扇区所需的位数是 19。

**2)组 1 包含一些 CPU 调度算法，组 2 包含一些应用。将组 1 中的条目与组 2 中的条目进行匹配。**

```
     Group I                          Group II
(P) Gang Scheduling              (1) Guaranteed Scheduling
(Q) Rate Monotonic Scheduling    (2) Real-time Scheduling
(R) Fair Share Scheduling        (3) Thread Scheduling
```

(一)P–3 Q–2 R–1
(二)P–1 Q–2 R–3
(三)P–2 Q–3 R–1
(四)P–1 Q–3 R–2

对于调度相关线程或进程在不同处理器上同时运行的并行系统，回答(A)
[联动调度](http://en.wikipedia.org/wiki/Gang_scheduling)。
[速率单调调度](http://en.wikipedia.org/wiki/Rate-monotonic_scheduling)用于具有静态优先级调度类的实时操作系统。静态优先级是根据作业的周期持续时间分配的:周期持续时间越短，作业的优先级越高。
[公平份额调度](http://en.wikipedia.org/wiki/Fair-share_scheduling)是一种调度策略，其中 CPU 使用率在系统用户或组之间平均分配，而不是在进程之间平均分配。它也被称为保证调度。

**3)操作系统使用最短剩余时间优先(SRT)进程调度算法。考虑以下流程的到达时间和执行时间** :

```
Process  Execution time  Arrival time
P1             20            0
P2             25            15
P3             10            30
P4             15            45
```

**流程 P2 的总等待时间是多少？**
(甲)5
(乙)15
(丙)40
(丁)55

答案(B)
在时间 0，P1 是唯一的进程，P1 运行了 15 个时间单位。
15 时，P2 到达，但 P1 剩余时间最短。所以 P1 又继续了 5 个时间单位。
时间 20 时，P2 是唯一的进程。所以它运行了 10 个时间单位
在时间 30，P3 是最短的剩余时间过程。因此它运行 10 个时间单位
在时间 40，P2 运行，因为它是唯一的过程。P2 跑了 5 个时间单位。
45 时，P3 到达，但 P2 剩余时间最短。所以 P2 又继续了 10 个时间单位。
P2 在时间 55 完成其执行

```
Total waiting time for P2 = Complition time - (Arrival time + Execution time)
                          = 55 - (15 + 25)
                          = 15 
```

**请参见**[**GATE Corner**](http://geeksquiz.com/gate-corner-2/)**查看往年所有论文/解答/说明、教学大纲、重要日期、笔记等。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论