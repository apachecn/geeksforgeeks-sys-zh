# 同步中的优先级继承协议(PIP)

> 原文:[https://www . geesforgeks . org/priority-inheritation-protocol-pip-in-synchronization/](https://www.geeksforgeeks.org/priority-inheritance-protocol-pip-in-synchronization/)

先决条件–[进程同步介绍](https://www.geeksforgeeks.org/introduction-of-process-synchronization/)
**优先级继承协议(PIP)** 是一种用于在不同任务之间共享关键资源的技术。这允许在不同的之间共享关键资源，而不会出现无限的优先级反转。

**PIP 的基本概念:**
PIP 的基本概念是当一个任务经过优先级反转时，通过优先级继承机制增加具有关键资源的低优先级任务的优先级。它允许该任务尽可能早地使用关键资源，而无需先占。它避免了无边界的优先级反转。

**画中画工作:**

*   当几个任务在等待相同的关键资源时，当前持有该关键资源的任务在所有等待相同关键资源的任务中被赋予最高优先级。
*   现在，在具有关键资源的较低优先级任务被赋予最高优先级之后，中等优先级任务不能抢占该任务。这有助于避免无限优先级反转。
*   当在所有任务中被赋予最高优先级的任务完成作业并释放关键资源时，它将恢复到其原始优先级值(可能更小或相等)。
*   如果一个任务持有多个关键资源，那么在释放一个关键资源之后，它就不能回到它原来的优先级值。在这种情况下，它继承了等待相同关键资源的所有任务中的最高优先级。

```
If the critical resource is free then
       allocate the resource
If the critical resource is held by higher priority task then
       wait for the resource
If the critical resource is held by lower priority task
     {    
       lower priority task is provided the highest priority
       other tasks wait for the resource
     } 
```

**PIP 的优势:**
优先级继承协议具有以下优势:

*   它允许不同优先级的任务共享关键资源。
*   优先级继承协议最突出的优点是避免了无边界的优先级反转。

**PIP 的缺点:**
优先级继承协议有两个可能出现的主要问题:

*   **Deadlock –**
    There is possibility of deadlock in the priority inheritance protocol.

    比如有两个任务 T <sub>1</sub> 和 T <sub>2</sub> 。假设 T <sub>1</sub> 的优先级高于 T <sub>2</sub> 。T <sub>2</sub> 先开始运行，持有关键资源 CR <sub>2</sub> 。

    之后，T <sub>1</sub> 到达，抢占 T <sub>2</sub> 。T <sub>1</sub> 持有关键资源 CR <sub>1</sub> ，同时也试图持有由 T <sub>2</sub> 持有的 CR <sub>2</sub> 。现在 T <sub>1</sub> 块和 T <sub>2</sub> 按照 PIP 继承 T <sub>1</sub> 的优先级。T <sub>2</sub> 开始执行，现在 T <sub>2</sub> 试图持有 CR <sub>1</sub> ，该 CR 由 T <sub>1</sub> 持有。

    于是，T <sub>1</sub> 和 T <sub>2</sub> 都陷入了僵局。

*   **Chain Blocking –**
    When a task goes through priority inversion each time it needs a resource then this process is called chain blocking.

    比如有两个任务 T <sub>1</sub> 和 T <sub>2</sub> 。假设 T <sub>1</sub> 的优先级高于 T <sub>2</sub> 。T <sub>2</sub> 持有关键资源 CR <sub>1</sub> 和 CR <sub>2</sub> 。T <sub>1</sub> 到达并请求 CR <sub>1</sub> 。T <sub>2</sub> 根据画中画进行优先级反转。

    现在，T <sub>1</sub> 请求 CR <sub>2</sub> ，再次 T <sub>2</sub> 根据 PIP 进行优先级反转。

    因此，持有关键资源的多个优先级反转会导致链阻塞。