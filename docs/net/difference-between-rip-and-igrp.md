# RIP 和 IGRP 的区别

> 原文:[https://www . geesforgeks . org/rip-and-igrp 之间的差异/](https://www.geeksforgeeks.org/difference-between-rip-and-igrp/)

**1。[路由信息协议(RIP)](https://www.geeksforgeeks.org/routing-information-protocol-rip/) :**
RIP，其中距离矢量路由协议用于数据/数据包传输。在路由信息协议(RIP)中，最大跳数是 15，因为它防止从源到目的地的路由环路。诸如水平分割、路由中毒和保持等机制被用来防止不正确或错误的路由信息。莎莉·弗洛伊德和范·雅各布森[1994]建议，如果计时器没有轻微的随机化，计时器就会同步超时。与其他路由协议相比，RIP(路由信息协议)较差，限制了规模，即网络较小。使用 RIP 的主要优势是使用 [UDP(用户数据报协议)](https://www.geeksforgeeks.org/user-datagram-protocol-udp/)。

**2。[内部网关路由协议(IGRP)](https://www.geeksforgeeks.org/difference-between-igrp-and-eigrp/) :**
IGRP，其中使用距离矢量协议(内部)在系统内交换数据。它支持每个节点的多个指标，包括延迟、负载和带宽，以便比较组合成单个指标的两条路由。IGRP 的端口号是 9，用于通信，默认情况下每 90 秒更新一次路由信息。

**RIP 和 IGRP 的区别:**

<center>

| SR.NO | 长裂口 | 内部网关路由协议(Interior Gateway Routing Protocol) |
| --- | --- | --- |
| one | RIP 代表路由信息协议。 | IGRP 代表内部网关路由协议。 |
| Two | RIP 在贝尔曼·福特算法上工作。 | IGRP 还致力于贝尔曼·福特算法。 |
| three | 它是一个行业标准的动态路由协议。 | 它是思科标准路由协议。 |
| four | 它基本上用于较小规模组织。 | 它主要用于网络中的中大型组织。 |
| five | RIP 是一种距离矢量协议。 | IGRP 也是一个距离矢量协议。 |
| six | 它允许最大跳数达到 15。 | 它允许最大跳数达到 255。 |
| seven | 它的行政距离是 120。 | 它的行政距离是 100。 |
| eight | 它不是更智能的动态路由协议。 | 它是一种比 RIP 更智能的路由协议。 |
| nine | 它根据跳数计算度量。 | 它根据带宽、负载和延迟来计算度量。 |
| Ten | RIP 路由协议在路由器中创建两个表:路由表、拓扑表。 | EIGRP 路由协议在路由器中创建三个表:邻居表、拓扑表、路由表。 |

</center>