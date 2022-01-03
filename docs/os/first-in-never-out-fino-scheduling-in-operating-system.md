# 操作系统中的先进先出(FINO)调度

> 原文:[https://www . geesforgeks . org/fino-in-never-out-fino-scheduling-in-operating-system/](https://www.geeksforgeeks.org/first-in-never-out-fino-scheduling-in-operating-system/)

**先进先出(FINO)** 调度是一种处理数据结构的有趣技术，其中主要组件没有被处理，或者我们说没有一个组件被处理，所有组件都被永久保留。

在应用科学中，FINO 可能是一种幽默的编程调度算法，与传统的先进先出(FIFO)和后进先出(LIFO)算法相矛盾。

这种调度算法的工作方式是，所有进入的进程都被永久阻止或阻塞。无论计划了多少任务，或者队列中随时有多少任务，实际上都不会发生任何任务

FINO 最早出现在 Signetics 25120 只写内存笑话数据表中，这是一家美国电子制造商，成立于 1961 年，专门用于制造集成电路，是一种幽默的调度算法，一旦进入队列，请求将永远无法得到处理。

**实施 FINO :**

```
// C++ program to demonstrate working of FINO
// using Queue interface in C++

#include <bits/stdc++.h>
using namespace std;
int main()
{
    queue<int> q;
    int t
            cin
        >> t;
    for (int x = 0; x < t; x++)
        q.push(x);
    return 0;
}
```

**FINO 用在哪里？**

*   在操作系统中，内存泄漏是一种资源泄漏，当操作系统错误地管理内存分配时，不再需要的内存不会被释放。而有状态的 FINO 队列就是用来实现这样的*内存泄漏*。
*   **In write only memory (WOM) –**
    Write-only memory (WOM) is fictional computer memory, just opposite of read-only memory (ROM).Technically, WOM is memory device which can be written but never read.

    在早期阶段，数据只能被写入而不能被读取的存储电路没有实际用途，概念多次被用作失败存储设备的双关语或滑稽笑话。直到 1972 年 Signetics 首次使用只写存储器。该公司出版了一些只写记忆(WOM)理论和文献，因为室内滑稽的结果，这通常是在工业中引用，软件工程词汇的主要部分，并包括在最佳恶作剧的集合。

*   位桶还与先进先出缓冲区和只写内存相关。在计算科学与技术中，比特桶是所有丢失的计算机化数据都去的地方，在传输中丢失，计算机崩溃。据说所有这些数据都到了比特桶，计算机上丢失数据的神秘地方。
*   FINO queue is used in black hole in computer networks also. In computer science and networking, black holes refer to virtual places in computer network where incoming and/or outgoing traffic is silently thrown away or dropped, without informing source that data did not reach its intended recipient and all of this, idea and implementation of black hole is based on FINO.