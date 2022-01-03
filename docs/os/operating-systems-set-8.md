# 操作系统|第 8 集

> 原文:[https://www.geeksforgeeks.org/operating-systems-set-8/](https://www.geeksforgeeks.org/operating-systems-set-8/)

GATE 2009 CS 考试提出了以下问题。

**1)在以下哪种页面替换策略中，可能会出现 Belady 异常？**
(甲)先进先出
(乙)最佳
(丙)LRU
(丁)MRU

答案(A)
Belady 的异常证明，在使用先进先出(FIFO)页面替换算法的同时，增加页面帧数时，有可能出现更多的页面错误。
参见[维基页面](http://en.wikipedia.org/wiki/B%C3%A9l%C3%A1dy's_anomaly)了解页面错误随着页面框架数量增加的示例。

**2)页表每个条目的基本内容是/是**
(A)虚拟页码
(B)页框号
(C)虚拟页码和页框号
(D)访问权限信息

答案(B)
页表条目必须包含页框号。虚拟页码通常用作页表中的索引，以获得相应的页框编号。详见[本](http://codex.cs.yale.edu/avi/os-book/OS8/os8e/slide-dir/PDF-dir/ch8.pdf)。

**3)考虑一个有 4 种资源类型的系统 R1 (3 个单位)、R2 (2 个单位)、R3 (3 个单位)、R4 (2 个单位)。使用非抢占式资源分配策略。在任何给定的情况下，如果一个请求不能完全满足，它就不被接受。如果独立执行，P1、P2 和 P3 的三个流程要求提供以下信息来源。**

```
Process P1: 
t=0: requests 2 units of R2 
t=1: requests 1 unit of R3 
t=3: requests 2 units of R1 
t=5: releases 1 unit of R2    
        and 1 unit of R1\. 
t=7: releases 1 unit of R3 
t=8: requests 2 units of R4 
t=10: Finishes

Process P2: 
t=0: requests 2 units of R3 
t=2: requests 1 unit of R4 
t=4: requests 1 unit of R1 
t=6: releases 1 unit of R3 
t=8: Finishes

Process P3: 
t=0: requests 1 unit of R4 
t=2: requests 2 units of R1 
t=5: releases 2 units of R1 
t=7: requests 1 unit of R2 
t=8: requests 1 unit of R3 
t=9: Finishes

```

**如果三个进程都从时间 t=0 开始并发运行，下列哪个陈述是正确的？**
(A)所有进程都将结束，没有任何死锁
(B)只有 P1 和 P2 会陷入死锁。
(丙)只有 P1 和 P3 会陷入僵局。
(D)三个进程都将处于死锁状态

回答(A)
我们可以应用下面的死锁检测算法，看到没有进程无限期等待一个资源。死锁检测算法见[本](http://codex.cs.yale.edu/avi/os-book/OS8/os8c/slide-dir/PPTX-dir/ch7.pptx)。

**4)考虑一个有 100 个柱面的磁盘系统。访问柱面的请求按以下顺序发生:
4、34、10、7、19、73、2、15、6、20
假设磁头当前位于柱面 50，如果从一个柱面移动到相邻的柱面需要 1 毫秒，并且使用最短寻道时间优先策略，满足所有请求需要多长时间？**
(A)95 毫秒
(B)119 毫秒
(C)233 毫秒
(D)276 毫秒

答案(B)
4、34、10、7、19、73、2、15、6、20
由于使用最短寻道时间优先策略，磁头将首先移动到 34。这个动作会导致 16*1 毫秒，34 之后，头部会移动到 20，这将导致 14*1 毫秒，以此类推。因此，按照以下顺序访问柱面 34、20、19、15、10、7、6、4、2、73，总时间将为(16 + 14 + 1 + 4 + 5 + 3 + 1 + 2 + 2 + 71)*1 = 119 毫秒。

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见[门角](http://geeksquiz.com/gate-corner-2/)。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论。