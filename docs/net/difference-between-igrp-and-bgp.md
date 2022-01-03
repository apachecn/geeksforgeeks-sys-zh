# IGRP 和 BGP 的区别

> 原文:[https://www . geesforgeks . org/difference-igrp-and-BGP/](https://www.geeksforgeeks.org/difference-between-igrp-and-bgp/)

**1。内部网关路由协议(IGRP) :**
IGRP，其中使用[距离矢量协议](https://www.geeksforgeeks.org/distance-vector-routing-dvr-protocol/)(内部)在系统内交换数据。它支持每个节点的多个指标，包括延迟、负载和带宽，以便比较组合成单个指标的两条路由。IGRP 的端口号是 9，用于通信，默认情况下每 90 秒更新一次路由信息。

**2。[边界网关协议(BGP)](https://www.geeksforgeeks.org/border-gateway-protocol-bgp/) :**
在 BGP 中，使用传输控制协议。这是一种网状拓扑或设计。它通过两个独立的网络(自治系统或自治系统)交换路由信息来工作。两台路由器同意交换如何到达特定 ip 范围的信息。BGP 使用传输控制协议(TCP)端口 179。

**IGRP 和 BGP 的区别:**

<center>

| 没有。 | 内部网关路由协议(Interior Gateway Routing Protocol) | 边界网关协议(Border Gateway Protocol) |
| --- | --- | --- |
| 1. | IGRP 代表内部网关路由协议。 | BGP 代表边界网关协议。 |
| 2. | 它在贝尔曼-福特算法上有效。 | 它工作在最佳路径算法上。 |
| 3. | 它主要用于大型组织。 | 与 IGRP 相比，它基本上用于规模非常大组织。 |
| 4. | 它是距离矢量类型。 | 它是矢量状态类型。 |
| 5. | 它是内部网关协议。 | 它是外部网关协议。 |
| 6. | 它是一种智能路由协议。 | 这是一种比 IGRP 更智能的路由协议。 |
| 7. | 在 IGRP，使用互联网协议。 | 在 BGP 中，使用传输控制协议。 |
| 8. | 它的行政距离是 100。 | 其管理距离为 20(内部)和 200(外部)。 |

</center>