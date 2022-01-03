# 各种磁盘调度算法的优缺点

> 原文:[https://www . geesforgeks . org/各种磁盘调度算法的优缺点/](https://www.geeksforgeeks.org/advantages-and-disadvantages-of-various-disk-scheduling-algorithms/)

先决条件–[磁盘调度算法](https://www.geeksforgeeks.org/disk-scheduling-algorithms/)

**1。[先到先得(FCFS)](https://www.geeksforgeeks.org/fcfs-disk-scheduling-algorithms/) :**
**优势–**

1.  先来先服务算法有一个非常简单的逻辑，它按照请求到达的顺序一个接一个地执行请求。
2.  因此，先到先得非常简单，易于理解和实施。
3.  最终，在 FCFS 中，每个进程都有机会执行，因此不会出现饥饿。

**缺点–**

1.  这种调度算法是非一次性的，这意味着进程不能在执行过程中停止，而是会全程运行。
2.  FCFS 是一种非重复调度算法，队列后面的短进程必须等待前面的长进程完成
3.  FCFS 的吞吐量不是很高效。
4.  FCFS 只在输入输出效率不是最重要的小系统上实现。

**2。[最短寻道时间优先(SSTF)](https://www.geeksforgeeks.org/program-for-sstf-disk-scheduling-algorithm/) :**
**优势–**

1.  与先到先得相比，总寻道时间缩短。
2.  SSTF 提高并增加了吞吐量。
3.  SSTF 的平均等待时间和响应时间更短。

**缺点–**

1.  在 SSTF，找到最接近的请求是一项开销。
2.  远离头部的请求可能会出现饥饿。
3.  在 SSTF，响应时间和等待时间的差异很大。
4.  头部方向的频繁切换会降低算法的速度。

**3。[扫描](https://www.geeksforgeeks.org/scan-elevator-disk-scheduling-algorithms/) :**
**优势–**

1.  扫描调度算法简单，易于理解和实现。
2.  扫描算法避免了饥饿。
3.  低差异发生在等待时间和响应时间。

**缺点–**

1.  头部刚到达的气缸需要很长的等待时间。
2.  在扫描中，尽管没有需要服务的请求，磁头还是移动到磁盘的末端。

**4。 [C-SCAN](https://www.geeksforgeeks.org/c-scan-disk-scheduling-algorithm/) :**
**优势–**

1.  C-SCAN 算法是 SCAN 调度算法的继承和改进。
2.  磁头从磁盘的一端移动到另一端，同时为其间的所有请求提供服务。
3.  与扫描算法相比，在 C 扫描中，磁头刚刚访问的柱面的等待时间减少了。
4.  提供统一的等待时间。
5.  提供了更好的响应时间。

**缺点–**

1.  与扫描算法相比，C 扫描会导致更多的寻道运动。
2.  在 C-SCAN 中，与 SCAN 算法不同，即使没有剩余的请求需要处理，磁头仍然会移动到磁盘的末端。

**5。[看](https://www.geeksforgeeks.org/look-disk-scheduling-algorithm/) :**
**优势–**

1.  如果没有需要服务的请求，磁头不会像扫描算法那样移动到磁盘的末端。
2.  与扫描算法相比，性能更好。
3.  LOOK 调度算法避免了饥饿。
4.  等待时间和响应时间的差异较小。

**缺点–**

1.  存在查找结束请求的开销。
2.  海德刚参观过的钢瓶要等很长时间。

**6。 [C-LOOK](https://www.geeksforgeeks.org/c-look-disk-scheduling-algorithm/) :**
**优势–**

1.  在 C-LOOK 中，如果没有需要服务的请求，磁头不必移动到磁盘的末尾。
2.  在 C-LOOK 中，头部刚刚访问的气缸等待时间更短。
3.  与查找算法相比，C-LOOK 提供了更好的性能。
4.  饥饿在 C-LOOK 中是可以避免的。
5.  等待时间和响应时间的差异较小。

**缺点–**

1.  在 C-LOOK 中，查找最终请求的开销是存在的。