# RIP 和 EIGRP 的区别

> 原文:[https://www . geesforgeks . org/rip-and-EIGRP 之差/](https://www.geeksforgeeks.org/difference-between-rip-and-eigrp/)

**1。[路由信息协议(RIP)](https://www.geeksforgeeks.org/routing-information-protocol-rip/) :**
在 RIP 中，[距离矢量路由(DVR)协议](https://www.geeksforgeeks.org/distance-vector-routing-dvr-protocol/)用于数据/数据包传输。在路由信息协议(RIP)中，最大跳数是 15，因为它防止从源到目的地的路由环路。诸如水平分割、路由中毒和保持等机制被用来防止不正确或错误的路由信息。莎莉·弗洛伊德和范·雅各布森[1994]建议，如果计时器没有轻微的随机化，计时器就会同步超时。与其他路由协议相比，RIP 性能差，网络规模小。使用 RIP 的主要优势是它使用了 [UDP(用户数据报协议)](https://www.geeksforgeeks.org/user-datagram-protocol-udp/)。

**2。[增强型内部网关协议(EIGRP)](https://www.geeksforgeeks.org/eigrp-fundamentals/) :**
EIGRP 代表允许路由器与同一区域内的相邻路由器共享信息。不是将全部信息发送到相邻路由器，而是共享所需的信息，这减少了工作量和需要传输的数据量。它由 CISCO 系统设计，只能在 CISCO 路由器中使用，但在 2013 年成为开源，因此可以在其他路由器中使用。邻居表和拓扑表由 EIGRP 维护。

**RIP 和 EIGRP 的区别:**

<center>

| SR.NO | 长裂口 | 加强型内部网关路由协议 |
| --- | --- | --- |
| 1. | RIP 代表路由信息协议。 | EIGRP 代表增强型内部网关路由协议。 |
| 2. | RIP 在贝尔曼·福特算法上工作。 | EIGRP 工作在 DUAL(扩散更新算法)算法上。 |
| 3. | 它是一个行业标准的动态路由协议。 | 它是思科标准路由协议。 |
| 4. | 它基本上用于较小规模组织。 | 与 RIP 相比，它基本上用于更大规模组织。 |
| 5. | RIP 是一种距离矢量协议。 | EIGRP 源自集成网关路由协议。 |
| 6. | 它允许最大跳数达到 15。 | 它允许最大跳数达到 255。 |
| 7. | 它的行政距离是 120。 | 它的行政距离是 90。 |
| 8. | 它不是更智能的动态路由协议。 | 它是一种比 RIP 更智能的路由协议。 |
| 9. | 它根据跳数计算度量。 | 它根据带宽和延迟来计算度量。 |
| 10. | RIP 路由协议在路由器中创建两个表:路由表和拓扑表。 | EIGRP 路由协议在路由器中创建三个表:邻居表、拓扑表和路由表。 |

</center>