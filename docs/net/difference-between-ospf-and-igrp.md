# OSPF 和 IGRP 的区别

> 原文:[https://www . geeksforgeeks . org/区别-OSPF-和-igrp/](https://www.geeksforgeeks.org/difference-between-ospf-and-igrp/)

**1。[开放最短路径优先(OSPF)](https://www.geeksforgeeks.org/open-shortest-path-first-ospf-protocol-states/) :**
OSPF 采用链路状态路由算法。使用路由器中可用的链路状态信息，它构建拓扑，其中拓扑确定用于路由决策的路由表。它支持[变长子网掩码](https://www.geeksforgeeks.org/introduction-of-variable-length-subnet-mask-vlsm/)和[无类域间路由](https://www.geeksforgeeks.org/classless-inter-domain-routing-cidr/)寻址模型。由于它使用了迪克斯特拉算法，它为每条路线计算[最短路径树](https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/)。OSPF(开放最短路径优先)的主要优点是它自己处理错误检测，并在广播域中使用多播寻址进行路由。

**2。[内部网关路由协议(IGRP)](https://www.geeksforgeeks.org/difference-between-igrp-and-eigrp/) :**
IGRP 使用距离矢量协议(内部)在系统内交换数据。它支持每个节点的多个指标，包括延迟、负载和带宽，以便比较组合成单个指标的两条路由。IGRP 的端口号是 9，用于通信，默认情况下每 90 秒更新一次路由信息。

**OSPF 和 IGRP 的区别:**

<center>

| SR.NO | 开放式最短路径优先(Open Shortest Path First Interior Gateway Protocol) | 内部网关路由协议(Interior Gateway Routing Protocol) |
| --- | --- | --- |
| 1. | OSPF 代表开放最短路径优先。 | IGRP 代表内部网关路由协议。 |
| 2. | OSPF 研究迪克斯特拉算法。 | IGRP 致力于贝尔曼·福特算法。 |
| 3. | 这是一个链路状态协议。 | 这是一个距离矢量协议。 |
| 4. | 它主要用于网络中较大规模的组织。 | 它主要用于网络中的中大型组织。 |
| 5. | 跳数没有这样的限制。 | 它允许最大跳数达到 255。 |
| 6. | 这是一种比 IGRP 更智能的路由协议。 | 它不是更智能的路由协议。 |
| 7. | OSPF 路由协议在路由器中创建三个表:
邻居表、数据库表、路由表。 | IGRP 路由协议在路由器中创建三个表:
邻居表、拓扑表、路由表。 |
| 8. | 它的管理距离是 110。 | 它的行政距离是 100。 |
| 9. | 这是一个行业标准的路由协议。 | 它是思科标准路由协议。 |
| 10. | 它根据带宽来计算度量。 | 它根据带宽、负载和延迟来计算度量。 |

</center>