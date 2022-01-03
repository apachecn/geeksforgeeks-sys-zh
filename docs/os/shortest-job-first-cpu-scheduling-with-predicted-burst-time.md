# 预测突发时间最短的作业优先 CPU 调度

> 原文:[https://www . geesforgeks . org/最短作业优先 cpu 调度预测突发时间/](https://www.geeksforgeeks.org/shortest-job-first-cpu-scheduling-with-predicted-burst-time/)

**先决条件–**[中央处理器调度](https://www.geeksforgeeks.org/gate-notes-operating-system-process-scheduling/)、[SJF–设置 1(非优先)](https://www.geeksforgeeks.org/program-shortest-job-first-sjf-scheduling-set-1-non-preemptive/)、[设置 2(优先)](https://www.geeksforgeeks.org/program-shortest-job-first-scheduling-set-2srtf-make-changesdoneplease-review/)

**最短作业优先(SJF)** 是一种优化的调度算法，因为它给出了最大吞吐量和最小平均等待时间(WT)以及周转时间(TAT)，但它实际上是不可实现的，因为进程的突发时间无法提前预测。

我们可能不知道下一个 CPU 突发的长度，但我们可能能够预测它的值。我们预计下一个中央处理器突发的长度将与前一个相似。通过计算下一个中央处理器突发长度的近似值，我们可以选择预测的中央处理器突发最短的进程。

有两种方法可以预测过程的突发时间:

**1。静态方法–**我们可以通过两个因素来预测突发时间:

*   **进程大小–**
    假设我们有一个大小为 200 KB 的进程 P <sub>旧的</sub>已经执行，其突发时间为 20 个时间单位，现在假设我们有一个大小为 201 KB 的新进程 P <sub>新的</sub>尚未执行。
    我们将已经执行的工艺 P <sub>旧的</sub>的爆发时间与新工艺的爆发时间几乎相同，作为新工艺 P <sub>新的</sub>。
*   **Process type –**
    We can predict Burst-Time depending on the Type of Process. Operating System process(like scheduler, dispatcher, segmentation, fragmentation) are faster than User process( Gaming, application softwares ). Burst-Time for any New O.S process can be predicted from any old O.S process of similar type and same for User process.

    **注意–**静态的突发时间预测方法不可靠，因为它总是预测不正确。

    **2。动态方法–**让 t <sub>i</sub> 为 i <sup>第</sup>次过程的实际爆发时间，τ<sub>n+1</sub>为 n+1 <sup>次</sup>次过程的预测爆发时间。

    *   **简单平均值–**给定 n 个过程(P <sub>1</sub> ，P <sub>2</sub> … P <sub>n</sub> )

        ```
        Τn+1 = 1/n(Σi=1 to n ti)
        ```

    *   **Exponential average (Aging) –**

        ```
        Τn+1 = αtn + (1 - α)Τn
        ```

        其中α =是平滑因子，0 <= α <= 1，

        t <sub>n</sub> =第 n <sup>次</sup>过程的实际爆发时间，
        τ<sub>n</sub>=第 n <sup>次</sup>过程的预测爆发时间。

        通用术语，

        ```
        αtn + (1 - α)αtn-1 + (1 - α)2αtn-2...+ (1 - α)jαtn-j...+ (1 - α)n+1Τ0 
        ```

        **τ<sub>0</sub>**是一个常数或整体系统平均值。

    **平滑因子(α)–**它控制我们预测中最近和过去历史的相对权重。

    *   如果α = 0，τ<sup>n+1</sup>=τ<sup>n</sup>，即初始预测突发时间的值没有变化。
    *   如果α = 1，τ<sup>n+1</sup>= t<sup>n</sup>即新过程的预测爆发时间将始终根据第 n <sup>次</sup>过程的实际爆发时间而变化。
    *   如果α = 1/2，最近和过去的历史被同等加权。

    **示例–**
    计算指数平均，T1 = 10，α = 0.5，算法是 SJF，以前的运行为 8、7、4、16。
    (a)9
    (b)8
    (c)7.5
    (d)无

    **解释:**
    最初 T1 = 10，α = 0.5，给出的运行时间是 8、7、4、16，因为这是最短的作业优先，
    所以这些进程可能的服务顺序是 4、7、8、16，因为 SJF 是一种非抢占式技术。
    所以，用公式:T2 = α*t1 + (1-α)T1
    所以我们有，
    T2 = 0.5*4 + 0.5*10 = 7，这里 t1 = 4 和 T1 = 10
    T3 = 0.5*7 + 0.5*7 = 7，这里 t2 = 7 和 T2 = 7
    T4 = 0.5*8 + 0.5*7 = 7.5，这里 t3 = 8 和 T3 = 7
    所以未来对第四次过程的预测将是

    本文由**雅什辛拉**供稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。