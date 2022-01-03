# 【EIGRP 和 OSPF 的区别

> 原文:[https://www . geesforgeks . org/difference-EIGRP-and-OSPF/](https://www.geeksforgeeks.org/difference-between-eigrp-and-ospf/)

[EIGRP](https://www.geeksforgeeks.org/eigrp-fundamentals/) 代表增强型内部网关路由协议。如果相邻路由器位于同一个区域，它用于将信息从一台路由器共享给相邻路由器。它也是一个复杂的协议，但可以进行配置，使其在小型和大型网络中轻松工作。它也是一种混合协议，因为它使用了[距离矢量路由](https://www.geeksforgeeks.org/computer-network-routing-protocols-set-1-distance-vector-routing/)和[链路状态路由协议](https://www.geeksforgeeks.org/unicast-routing-link-state-routing/)的特性。

[OSPF](https://www.geeksforgeeks.org/open-shortest-path-first-ospf-protocol-fundamentals/) 首先代表开放最短路径。这可以在各种网络中使用和部署。这是一种无类路由协议，也有助于[变长子网掩码(VLSM)](https://www.geeksforgeeks.org/introduction-of-variable-length-subnet-mask-vlsm/) 和不连续网络。

【EIGRP 和 OSPF 的区别:

<center>

| 没有。 | 比较 | 加强型内部网关路由协议 | 开放式最短路径优先(Open Shortest Path First Interior Gateway Protocol) |
| 1. | 代表 | 增强型内部网关协议。 | 首先打开最短路径。 |
| 2. | 协议类型 | 混血儿。 | 链接状态。 |
| 3. | 行政距离 | 90(内部)170(外部)。 | One hundred and ten |
| 4. | 算法 | 对偶距离向量。 | 迪克斯特拉链接状态。 |
| 5. | 标准-基于 | 思科专有。 | IETF 开放标准。 |
| 6. | 路由度量 | 带宽、可靠性、负载和延迟的组合。 | 接口带宽。 |
| 7. | 中央处理器要求 | 更低的中央处理器和内存需求。 | 需要很高的 CPU 和内存。 |
| 8. | 易于实施 | 简单，但不提供自动汇总。 | 复杂。 |

</center>