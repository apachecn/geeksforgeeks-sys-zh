# 资源抢占的弊端

> 原文:[https://www . geeksforgeeks . org/resource-return-of-preemption/](https://www.geeksforgeeks.org/drawback-of-resource-preemption/)

我们知道，当操作系统中出现[死锁](https://www.geeksforgeeks.org/operating-system-process-management-deadlock-introduction/)时，为了消除它，我们将抢占一些进程，并将资源给予其他进程，因此每当需要抢占来消除死锁时，就会出现一些缺点:选择受害者、进程回滚和饥饿。

1.  **Select the victim:**
    First drawback is that when we want to select the resources and which process needs to be preempted, we must pre-determine the processes that in which order the processes are to use the resources to minimize the cost, so selecting a victim is a drawback during the resource preemption.
2.  **Rollback of processes:**
    Second drawback is that when we preempt one resource from the process then that time one question is raised that what should we do with that process and the only possible answer is that we should get to roll back the process and place it on some safe state and restart it. But in reality, it is very difficult to get a safe state, so the better way is to roll back completely abort the process and restart it again. It is the more effective way to roll back the process only as for as to remove the deadlock.
3.  **饥饿:**
    第三个缺点是我们如何保证饥饿不会进一步发生的是系统，也就是我们如何保证资源不会被抢占。在操作系统中，我们知道选择受害者是一个具有成本效益的过程，所以当我们选择同一个受害者作为同一个过程时，可能会发生这种情况，结果是这个过程永远不会完成，从而导致饥饿。