# 优先级反转:管他呢！

> 原文:[https://www . geesforgeks . org/priority-inversion-什么鬼/](https://www.geeksforgeeks.org/priority-inversion-what-the-heck/)

让我们首先把“优先级反转”放在大局的背景下，即它从何而来。

在操作系统中，任务调度是一个重要的概念。有多种调度方法，如先到先得、循环调度、基于优先级的调度等。每种调度方法都有其优缺点。正如您可能已经猜到的，优先级反转属于基于优先级的调度。基本上，当操作系统使用基于优先级的调度时，有时会出现这个问题。在基于优先级的调度中，不同的任务被赋予不同的优先级，以便较高优先级的任务可以在可能的情况下干预较低优先级的任务。

因此，在基于优先级的调度中，如果较低优先级的任务(L)正在运行，并且如果较高优先级的任务(H)也需要运行，则较低优先级的任务(L)将被较高优先级的任务(H)抢占。现在，假设优先级较低和较高的任务都需要共享一个公共资源(比如访问同一个文件或设备)来完成各自的工作。在这种情况下，由于存在资源共享并且需要任务同步，因此可以使用几种方法/技术来处理这种情况。为了我们关于优先级反转的主题，让我们提到一个同步方法，比如互斥。简单回顾一下互斥体，任务在进入临界区(CS)之前获取互斥体，在退出临界区(CS)之后释放互斥体。在 CS 中运行时，任务访问这个公共资源。更多细节可以参考[这里的](https://www.geeksforgeeks.org/g-fact-70/)。现在，假设 L 和 H 共享一个公共的临界区，即这个临界区需要相同的互斥体。

接下来讨论优先级反转，让我们检查一些场景。
1) L 正在运行但不在 CS；h 需要跑；h 抢占 L；h 开始运行；h .放弃或释放控制权；L 恢复并开始运行
2) L 在 CS 中运行；h 需要跑但不在 CS；h 抢占 L；h 开始运行；h 放弃控制权；l 恢复并开始跑步。
3) L 在 CS 运行；h 也需要在 CS 中运行；h 等待 L 从 CS 出来；l 出自 CS；h 进入 CS 开始运行

请注意，上述场景没有显示任何优先级反转的问题(甚至场景 3 也没有)。基本上，只要低优先级任务没有在共享 CS 中运行，高优先级任务就可以抢占它。但是如果 L 在共享 CS 中运行，H 也需要在 CS 中运行，H 就要等到 L 从 CS 中出来。这个想法是 CS 应该足够小，这样就不会导致 L 在 CS 的时候 H 等待很长时间。这就是为什么编写 CS 代码需要仔细考虑的原因。在上述任何一种情况下，优先级反转(即优先级反转)都没有发生，因为任务正在按照设计运行。

现在让我们添加另一个中等优先级的任务，比如 M。现在任务优先级的顺序是 L < M < H。在我们的示例中，M 不共享同一个关键部分(CS)。在这种情况下，以下任务运行顺序将导致“优先级反转”问题。

4) L 在 CS 中运行；h 也需要在 CS 中运行；h 等待 L 从 CS 出来；m 中断 L，开始运行；m 运行到完成并放弃控制权；l 恢复并开始运行直至 CS 结束；h 进入 CS 开始运行。
注意，L 和 H 都不与 m 共享 CS。

这里我们可以看到 M 的运行延迟了 L 和 H 的运行，准确的说是 H 优先级更高，没有和 M 共享 CS；但是 H 必须等待 M。这就是基于优先级的调度没有像预期的那样工作的地方，因为 M 和 H 的优先级颠倒了，尽管没有共享任何 CS。这个问题叫做优先级反转。这就是优先级反转！在具有基于优先级的调度的系统中，较高优先级的任务可能面临这个问题，并且它可能导致意外的行为/结果。在通用操作系统中，它会导致性能下降。在 RTOS，这可能会导致更严重的后果。最著名的“优先级反转”问题发生在火星探路者号上。

如果我们有问题，必须有一个解决方案。对于优先级反转，也有不同的解决方案，如优先级继承等。这将是我们的下一篇文章🙂

但对于住院患者来说，[这个](https://www.geeksforgeeks.org/whats-difference-priority-inversion-priority-inheritance/)暂时可以参考。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。