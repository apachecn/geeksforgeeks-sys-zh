# GATE | GATE-CS-2015(第 2 集)|第 65 题

> 原文:[https://www . geesforgeks . org/gate-gate-cs-2015-set-2-question-35/](https://www.geeksforgeeks.org/gate-gate-cs-2015-set-2-question-35/)

一个计算机系统实现一个 40 位虚拟地址，8 千字节的页面大小，和一个 128 条目的翻译后备缓冲器(TLB)，它被组织成 32 个集合，每个集合有四条路。假设 TLB 标签不存储任何进程 id。TLB 标签的最小长度(以位为单位)为 _ _ _ _ _ _
**(A)**20
**(B)**10
**(C)**11
**(D)**22

**答案:****(D)**

**解释:**

```
Total virtual address size = 40

Since there are 32 sets, set offset = 5

Since page size is 8kilobytes, word offset = 13

Minimum tag size = 40 - 5- 13 = 22
```

[本题小考](https://www.geeksforgeeks.org/operating-systems-gq/memory-management-gq/)