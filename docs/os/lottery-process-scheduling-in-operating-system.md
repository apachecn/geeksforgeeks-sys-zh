# 操作系统中的抽奖进程调度

> 原文:[https://www . geesforgeks . org/彩票-操作系统中的进程调度/](https://www.geeksforgeeks.org/lottery-process-scheduling-in-operating-system/)

**先决条件–**[CPU 调度](https://www.geeksforgeeks.org/gate-notes-operating-system-process-scheduling/)、[进程管理](https://www.geeksforgeeks.org/gate-notes-operating-system-process-management-introduction/)
**抽奖调度**是进程调度的类型，与其他调度有些不同。进程是以随机方式调度的。抽奖调度可以是**抢先或非抢先**。它还解决了饥饿问题。给每个进程至少一张彩票保证了它在每个调度操作中被选中的概率非零。

在这个调度中，每个进程都有一些票证，调度器挑选一个随机票证，拥有该票证的进程是赢家，它在一个时间片内执行，然后调度器挑选另一个票证。这些票据代表流程的份额。具有较高数量票据的进程给它更多的机会被选择执行。

**示例–**如果我们有两个流程 A 和 B，在总共 100 张票中分别有 60 张和 40 张票。A 的 CPU 份额是 60%，B 的是 40%。这些份额是概率计算的，而不是确定的。

**解释–**

1.  我们有两个流程 A 和 B。A 有 60 张票(票号 1 到 60)，B 有 40 张票(票号 61 到 100)。
2.  调度程序选择一个从 1 到 100 的随机数。如果拣货号从 1 到 60，则执行 A，否则执行 B。
3.  调度程序挑选的 10 张票的示例可能如下所示–

    ```
    Ticket number -  73 82 23 45 32 87 49 39 12 09.
    Resulting Schedule -  B  B  A  A  A  B  A  A  A  A.

    ```

4.  a 执行 7 次，B 执行 3 次。如你所见，甲占 70%的 CPU，乙占 30%，这和我们需要的不一样，因为我们需要甲有 60%的 CPU，乙应该有 40%的 CPU。出现这种情况是因为股票是以概率计算的，但从长远来看(即，当所选的门票数量超过 100 或 1000 张时)，我们可以获得大约。甲和乙分别为 60 和 40。

**操纵票据的方式–**

*   **票币–**
    调度器以一种货币给不同的用户一定数量的票，用户可以以不同的货币给这些进程。例如，两个用户 A 和 B 分别被给予 100 和 200 张票。用户 A 正在运行两个进程，并以 A 自己的货币给每个进程 50 张票。B 正在运行 1 个进程，并以 B 的货币给它所有 200 张票。现在，在调度时，每个进程的票据都被转换为全球货币，即 A 进程将有 50 张票据，B 进程将有 200 张票据，调度是在此基础上进行的。
*   **转移票证–**
    一个进程可以将其票证传递给另一个进程。
*   **门票膨胀–**
    通过这种技术，流程可以暂时增加或减少其拥有的门票数量。

**参考资料–**
[彩票调度–维基百科](https://en.wikipedia.org/wiki/Lottery_scheduling)
[eecs.berkeley.edu](https://people.eecs.berkeley.edu/~brewer/cs262/Lec-scheduling.pdf)

本文由 **Ashish Sharma** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。