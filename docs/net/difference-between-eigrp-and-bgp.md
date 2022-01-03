# 【EIGRP 和 BGP 的区别

> 原文:[https://www . geesforgeks . org/EIGRP 和-bgp 之间的差异/](https://www.geeksforgeeks.org/difference-between-eigrp-and-bgp/)

**1。[增强型内部网关路由协议(EIGRP)](https://www.geeksforgeeks.org/eigrp-fundamentals/) :**
如果相邻路由器位于同一区域，则 EIGRP 用于将信息从一台路由器共享给相邻路由器。它也是一个复杂的协议，但可以进行配置，使其在小型和大型网络中轻松工作。它也是一种混合协议，因为它使用了[距离矢量路由](https://www.geeksforgeeks.org/distance-vector-routing-dvr-protocol/)和[链路状态路由协议](https://www.geeksforgeeks.org/unicast-routing-link-state-routing/)的特性。

**2。[边界网关协议(BGP)](https://www.geeksforgeeks.org/border-gateway-protocol-bgp/) :**
在 BGP 中，使用传输控制协议。这是一种网状拓扑或设计。它通过两个独立的网络(自治系统或自治系统)交换路由信息来工作。两台路由器同意交换如何到达特定 ip 范围的信息。BGP 使用[传输控制协议(TCP)](https://www.geeksforgeeks.org/tcp-and-udp-in-transport-layer/) 端口 179。

**EIGRP 和 BGP 的区别:**

<center>

| SR.NO | 加强型内部网关路由协议 | 边界网关协议(Border Gateway Protocol) |
| --- | --- | --- |
| 1. | EIGRP 代表增强型内部网关路由协议。 | BGP 代表边界网关协议。 |
| 2. | 它工作在对偶距离矢量算法上。 | 它工作在最佳路径算法上。 |
| 3. | 它主要用于大型组织。 | 与 EIGRP 相比，它基本上用于规模非常大组织。 |
| 4. | 是混合型。 | 它是矢量状态类型。 |
| 5. | 它是内部网关协议。 | 它是外部网关协议。 |
| 6. | 它是一种智能路由协议。 | 它是一种比 EIGRP 更智能的路由协议。 |
| 7. | 在 EIGRP 中，使用互联网协议。 | 在 BGP 中，使用传输控制协议。 |
| 8. | 其管理距离为 90(内部)和 170(外部)。 | 其管理距离为 20(内部)和 200(外部)。 |

</center>