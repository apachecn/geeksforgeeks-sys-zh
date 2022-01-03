# 获取 CSMA/光盘频道

> 原文:[https://www.geeksforgeeks.org/acquiring-channel-in-csma-cd/](https://www.geeksforgeeks.org/acquiring-channel-in-csma-cd/)

[CSMA/光盘](https://www.geeksforgeeks.org/collision-detection-csmacd/)代表载波侦听多路访问/冲突检测。在 CSMA/光盘中，碰撞发生的范围是 0 到 PT(传播时间)，碰撞检测的范围是 0 到 2xPT。

**要点:**

*   如果检测到的冲突小于 2xPT，或者在 2xPT 的最坏情况下，基站停止传输伪数据，并应用指数回退算法。该算法基本适用于故障情况。
*   如果在小于 2xPT 或最差情况下为 2xPT 时未检测到冲突，则在 2xPT 时，站确认其已获取信道或捕获了信道。
*   检测到碰撞的最大时间是 2xPT。
*   获取通道的最短时间为 2xPT。

我们知道 2xPT 是获取任何频道的最短时间。现在，在下面的例子中，我们将找到*最小帧大小*来获取或捕获通道。

**程序:**

*   **步骤-1:** 首先计算传输时间(TT)。在这里，TT 将是 2xPT
*   **步骤-2:** 对于 PT 的计算，给出了电缆长度和介质速度，并使用基本公式计算 PT。
*   **步骤-3:** 现在，我们将使用 TT 找到帧大小，并使用传输时间的基本公式找到带宽(BW)。

以上过程可以用下面的例子来说明。

**示例:**
在给定的 CSMA/CD 或以太网或总线拓扑结构
中，
带宽(BW) = 10 Mbps
电缆长度(l)= 200 m
介质速度(v)= 2×10^8 m/s

```
Here, TT = 2 x PT
Formula for propagation time is: PT = length of cable/velocity of medium
Hence, PT = 200 / (2 x 10^8) = 1/10^6 sec.
Then, TT = 2 x (1/10^6) = 2/10^6 sec
We know that, TT = Frame Size / Band width
Then, Frame Size = TT x Band width
                 = 2 / 10^6 x 10 x 10 ^6
                 = 20 bits

```

于是，闵。获取信道的帧大小为 20 位。

**往年 GATE 提问:**
[https://www . geesforgeeks . org/GATE-GATE-cs-2003-question-83/](https://www.geeksforgeeks.org/gate-gate-cs-2003-question-83/)
[https://www . geesforgeeks . org/GATE-GATE-it-2005-question-71/](https://www.geeksforgeeks.org/gate-gate-it-2005-question-71/)