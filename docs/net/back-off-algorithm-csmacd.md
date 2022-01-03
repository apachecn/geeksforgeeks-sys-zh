# CSMA/光盘退避算法

> 原文:[https://www.geeksforgeeks.org/back-off-algorithm-csmacd/](https://www.geeksforgeeks.org/back-off-algorithm-csmacd/)

先决条件–[CSMA/光盘基础](https://www.geeksforgeeks.org/computer-networks-gate-notes-set-1-data-link-layer/)、[CSMA/光盘碰撞检测](https://www.geeksforgeeks.org/collision-detection-csmacd/)
退避算法是一种**碰撞解决**机制，用于随机接入媒体访问控制协议(CSMA/光盘)。这种算法通常在以太网中用于调度冲突后的重新传输。

如果两个站点之间发生冲突，它们可能会在冲突后尽快重启传输。这将总是导致另一个冲突，并形成一个无限循环的冲突，导致死锁。为了防止这种情况，使用了退避算法。

让我们考虑一个场景，两个站点 A 和 B 传输一些数据:

![](img/7bcc4798c34e0b0317e3cb257d6f567a.png)

发生冲突后，时间被划分为长度等于 2t 的离散时隙( **T <sub>时隙</sub>T3)，其中 T 是网络中的最大传播延迟。**

冲突中涉及的站点从集合 K 中随机选择一个整数，即{0，1}。这个集合称为竞争窗口。如果源因选择了相同的整数而再次冲突，争用窗口大小将加倍，变为{0，1，2，3}。现在，第二次冲突中涉及的源从集合{0，1，2，3}中随机选择一个整数，并等待该数量的时隙，然后重试。在尝试传输之前，他们会监听信道，只有在信道空闲时才会传输。这会导致在竞争窗口中选择最小整数的源成功传输其帧。

因此，退避算法为参与冲突的站定义了一个*等待时间*，即站应该等待多长时间来重新传输。

```
Waiting time = back–off time
Let n = collision number or re-transmission serial number. 
Then, 
Waiting time = K * Tslot
where K = [0, 2n – 1 ]  

```

**示例–**

**情况-1 :**
假设 2 个站点 A 和 B 同时开始传输数据(数据包 1)，那么就会发生冲突。因此，它们两个数据(数据包 1)的冲突号 n = 1。现在，两个站都从集合 K 中随机选择一个整数，即{0，1}。

![](img/5d1700b3a7bcc44ac69d5eed339655d9.png)

*   **When both A and B choose K = 0**
    –> Waiting time for A = 0 * T<sub>slot</sub> = 0
    Waiting time for B = 0 * T<sub>slot</sub> = 0

    因此，两个站点将同时传输，因此会发生冲突。

*   **当 A 选择 K = 0，B 选择 K = 1 时**
    –>A = 0 * T<sub>槽</sub>= 0
    B = 1 * T<sub>槽</sub> = T <sub>槽</sub>的等待时间

因此，甲发送数据包，乙等待时间 T <sub>时隙</sub>发送，甲获胜。

*   **When A chooses K = 1 and B chooses K = 0**
    –> Waiting time for A = 1 * T<sub>slot</sub> = T<sub>slot</sub>
    Waiting time for B = 0 * T<sub>slot</sub> = 0

    因此，B 发送数据包，A 等待时间 T <sub>时隙</sub>进行发送，因此 B 获胜。

*   **When both A and B choose K = 1**
    –> Waiting time for A = 1 * T<sub>slot</sub> = T<sub>slot</sub>
    Waiting time for B = 1 * T<sub>slot</sub> = T<sub>slot</sub>

    因此，两者将等待相同的时间 T <sub>时隙</sub>然后传输。因此，会发生碰撞。

```
Probability that A wins = 1/4
Probability that B wins = 1/4
Probability of collision  = 2/4

```

**情况-2 :**
假设 A 在情况 1 中获胜并传输其数据(数据包 1)。现在，一旦 B 发送它的包 1，A 就发送它的包 2。因此，会发生碰撞。现在，冲突号 n 对于 A 的数据包 2 变为 1，对于 B 的数据包 1 变为 2。
对于 A 的数据包 2，K = {0，1}
对于 B 的数据包 1，K = {0，1，2，3}

![](img/12414b8dddf91c1e404f8b520fcfadaf.png)

```
Probability that A wins = 5/8
Probability that B wins = 1/8
Probability of collision  = 2/8

```

因此，与情况 1 相比，碰撞的概率降低了。

**优势–**

*   碰撞概率呈指数下降。

**缺点–**

*   **捕捉效果:**赢一个的站继续赢。
*   仅适用于 2 个电台或主机。

**GATE 练习题–**

1.  [GATE-CS-2004 |第 90 题](https://www.geeksforgeeks.org/gate-gate-cs-2004-question-54/)
2.  [GATE-CS-2016(第 2 集)|第 34 题](https://www.geeksforgeeks.org/gate-gate-cs-2016-set-2-question-34/)
3.  [GATE-IT-2004 |问题 85](https://www.geeksforgeeks.org/gate-gate-it-2004-question-85/)