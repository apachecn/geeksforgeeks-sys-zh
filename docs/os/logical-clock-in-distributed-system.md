# 分布式系统中的逻辑时钟

> 原文:[https://www . geesforgeks . org/logical-clock in-distributed-system/](https://www.geeksforgeeks.org/logical-clock-in-distributed-system/)

**逻辑时钟** 指的是在分布式系统中的所有机器上实现一个协议，以便机器能够在某个虚拟时间跨度内保持事件的一致顺序。逻辑时钟是一种在分布式系统中捕捉时间和因果关系的机制。分布式系统可能没有物理上同步的全局时钟，因此逻辑时钟允许在这样的系统中对来自不同进程的事件进行全局排序。

**例:**
如果我们到外面去，那么我们已经做了一个完整的计划，我们必须先去哪个地方，然后再去哪个地方，以此类推。我们不会先去第二名，再去第一名。我们总是维护之前计划的程序或组织。同样，我们应该有组织地在我们的电脑上一个接一个地进行操作。

假设我们在一个分布式系统中有 10 多台电脑，每台电脑都在做自己的工作，但是我们如何让它们一起工作。对此有一个解决方案，即逻辑时钟。

**方法-1:**
要跨进程排序事件，请尝试一种方法同步时钟。

这意味着如果一台电脑的时间是下午 2:00，那么每台电脑的时间应该是相同的，这是完全不可能的。不是每个时钟都能同时同步。那我们就不能遵循这个方法。

**方法-2:**
另一种方法是为事件分配时间戳。

考虑到这个例子，这意味着如果我们把第一名指定为 1，第二名指定为 2，第三名指定为 3，以此类推。然后我们总是知道第一名永远是第一名，然后就这样。同样，如果我们给每台电脑一个单独的号码，那么它的组织方式将是第一台电脑先完成它的过程，然后是第二台，以此类推。

但是，时间戳只有服从因果关系才会起作用。

**什么是因果关系？**
因果关系完全基于发生在关系之前。

*   Only when two events A and B occur one after another, a single PC is selected, and then TS(A) < TS(B). If the time stamp of A is 1, then the time stamp of B should be greater than 1, which only happens before the relationship occurs.
*   Take two personal computers, P1 event A(PC. 1) and P2 event B(PC. 2), and the condition is TS(A) < TS(B). For example, suppose you send a message to someone at 2:00:00 pm, and the other person receives it at 2:00:02 pm. Then obviously, TS (sender) < TS (receiver).

**源自关系发生之前的属性–**

*   **传递关系–**
    如果，TS(A) < TS(B)和 TS(B) < TS(C)，那么 TS(A) < TS(C)
*   **因果有序关系–**
    a->b，这意味着 a 发生在 b 之前，如果 a 有任何变化，它肯定会反映在 b 身上。
*   **并发事件–**
    这意味着不是每个进程都一一发生，有些进程是同时发生的，即 A || B