# 操作系统|第 7 集

> 原文:[https://www.geeksforgeeks.org/operating-systems-set-7/](https://www.geeksforgeeks.org/operating-systems-set-7/)

GATE CS 考试中提出了以下问题。
 **1)让在用户和内核执行模式之间切换的时间为 T1，而在两个进程之间切换的时间为 T2。以下哪一项是正确的？(GATE CS 2011)**
(A)t1>t2
(B)t1 = T2
(C)t1<T2(D)关于 t1 和 T2 的关系没什么好说的回答:- (C)流程切换涉及模式切换。上下文切换只能在内核模式下发生。

**2) A)系统使用 FIFO 策略进行页面替换。它有 4 个页面框架，没有页面加载开始。系统首先以某种顺序访问 100 个不同的页面，然后以相反的顺序访问同样的 100 个页面。会出现多少页面错误？(GATE CS 2010)** 
(A)196
(B)192
(C)197
(D)195

回答(A)
访问 100 页会导致 100 页错误。当以相反的顺序访问这些页面时，前四次访问不会导致页面错误。对页面的所有其他访问都将导致页面错误。所以页面错误总数将是 100 + 96。

**3)以下哪种说法是正确的？(GATE CS 2010)
一、最短剩余时间优先调度可能造成饥饿
二。抢先调度可能导致饥饿
三。循环赛在响应时间方面优于 FCFS**
(A)I 只
(B) I 和 III 只
(C) II 和 III 只
(D) I、II 和 III

答案(四)

I)最短剩余时间优先调度是最短作业调度的抢先版。它可能会导致饥饿，因为较短的进程可能会不断到来，而较长的 CPU 突发进程永远不会得到 CPU。
二)抢占可能导致饥饿。如果使用基于优先级的抢占调度，那么低优先级的进程可能永远得不到 CPU。
三)循环调度提高了响应时间，因为所有进程在指定时间后都会获得 CPU。

**4)考虑流程 P1 和 P2 在需要时访问其关键部分所使用的方法，如下所示。共享布尔变量 S1 和 S2 的初始值是随机分配的。**

```
Method Used by P1
while (S1 == S2) ;
Critica1 Section
S1 = S2;

Method Used by P2
while (S1 != S2) ;
Critica1 Section
S2 = not (S1);

```

**以下哪一项陈述描述了所获得的特性？(GATE CS 2010)**
(A)互斥但不进步
(B)进步但不互斥
(C)既不互斥也不进步
(D)既互斥又进步

答(A)
很容易观察到，上述解满足互斥要求，S1 不等于 S2 P1 才能进入临界区，S1 等于 S2 P2 才能进入临界区。
不满足进度要求。让我们首先看看进度需求的定义。
*进度要求:*如果在其关键部分没有进程正在执行，并且存在一些希望进入其关键部分的进程，那么接下来将进入关键部分的进程的选择不能无限期推迟。
如果 P1 或 P2 想重新进入临界区，那么即使临界区有其他进程在运行，他们也不能。

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见[门角](http://geeksquiz.com/gate-corner-2/)。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论。