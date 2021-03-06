# 昌迪-米斯拉-哈斯分布式死锁检测算法

> 原文:[https://www . geesforgeks . org/chandy-misra-haass-distributed-死锁检测-算法/](https://www.geeksforgeeks.org/chandy-misra-haass-distributed-deadlock-detection-algorithm/)

**Chandy-Misra-Haas 的分布式死锁检测算法**是一种检测分布式系统死锁的边缘追逐算法。

在边缘追踪算法中，死锁检测使用了一种称为*探测*的特殊消息。一个*探测器*是一个三元组 *(i，j，k)* ，表示进程 P <sub>i</sub> 已经启动死锁检测，并且该消息正由进程 P <sub>j</sub> 的归属站点发送到进程 P <sub>k</sub> 的归属站点。

探测信息沿着 WFG 的边缘循环，以探测一个周期。当被阻止的进程收到探测消息时，它会沿着其在 WFG 的传出边缘转发探测消息。如果由进程 P <sub>i</sub> 发起的探测消息返回到自身，则进程 P <sub>i</sub> 宣布死锁。

**算法中使用的其他术语:**

1.  **依赖过程:**
    一个过程 P <sub>i</sub> 据说依赖于某个其他过程 P <sub>j</sub> ，如果存在一个过程 P <sub>i</sub> ，P <sub>i1</sub> ，P <sub>i2</sub> ，P <sub>i3</sub> …，P <sub>im</sub> ，P <sub>j</sub> 的序列，那么在该序列中，除了 P <sub>之外的每个过程</sub> 
2.  **局部依赖过程:**
    如果过程 P <sub>i</sub> 依赖于过程 P <sub>j</sub> 并且两者都在同一位置，则过程 P <sub>i</sub> 被称为局部依赖于某个其他过程 P <sub>j</sub> 。

**数据结构:**
一个布尔数组，**从属 <sub>i</sub>** 。最初，**dependent<sub>I</sub>【j】**对于 I 和 j 的所有值都为假，如果过程 P <sub>j</sub> 依赖于过程 P <sub>i</sub> ，则<sub>I</sub>【j】为真。

**算法:**

**发送探针的过程:**

1.如果进程 P <sub>i</sub> 局部依赖于自身，则声明死锁。

2.否则，对于所有 P <sub>j</sub> 和 P <sub>k</sub> 检查以下情况:

*   **(一)。**过程 P <sub>i</sub> 局部依赖于过程 P <sub>j</sub>
*   **(b)。**进程 P <sub>j</sub> 正在等待进程 P <sub>k</sub>
*   **(c)。**工序 P <sub>j</sub> 和工序 P <sub>k</sub> 在不同的场地。

如果上述所有条件都成立，将探头(I，j，k)发送到工艺 P <sub>k</sub> 的原位。

**在流程 P <sub>k</sub> 主场收到探头(I，j，k)时:**

1.过程 P <sub>k</sub> 检查以下条件:

*   **(一)。**进程 P <sub>k</sub> 被阻塞。
*   **(b)。**从属 <sub>k</sub> 【我】是*假*。
*   **(c)。**流程 P <sub>k</sub> 尚未回复流程 P <sub>j</sub> 的所有请求

如果上述所有条件都成立，则:

1.将从属<sub>k</sub>【I】设置为真。
2。现在，如果 k == i 那么，宣布 P <sub>i</sub> 陷入僵局。
3。否则，对于所有 P <sub>m</sub> 和 P <sub>n</sub> 检查以下情况:

*   **(一)。**过程 P <sub>k</sub> 局部依赖于过程 P <sub>m</sub>
*   **(b)。**过程 P <sub>m</sub> 正在等待过程 P <sub>n</sub> 并且
*   **(c)。**工序 P <sub>m</sub> 和工序 P <sub>n</sub> 在不同的场地。

4.如果满足上述条件，将探头(I，m，n)发送到过程 P <sub>n</sub> 的原位。

因此，*探测*消息沿着事务等待(TWF)图的边缘传播，并且当*探测*消息返回到其启动过程时，则表示已经检测到死锁。

**性能:**

*   算法最多需要交换 *m(n-1)/2* 个消息来检测死锁。这里，m 是进程数，n 是站点数。
*   检测死锁的延迟为 *O(n)* 。

**优势:**

*   不需要特殊的数据结构。死锁检测过程中使用了一个探测消息，该消息非常小，只包含 3 个整数和一个依赖于*的二维布尔数组*。
*   在每个站点，只需要很少的计算，并且开销也很低
*   与其他死锁检测算法不同，该算法不需要构造任何图或传递，也不需要将图信息传递给其他站点。
*   算法不报告任何假死锁(也称为幻像死锁)。

**缺点:**
分布式检测算法的主要缺点是所有站点可能不知道死锁中涉及的进程，这使得解决变得困难。此外，证明算法的正确性也很困难。