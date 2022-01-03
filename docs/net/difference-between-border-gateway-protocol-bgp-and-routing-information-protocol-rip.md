# 边界网关协议(BGP)和路由信息协议(RIP)的区别

> 原文:[https://www . geesforgeks . org/border-gateway-protocol-BGP-and-routing-information-protocol-rip/](https://www.geeksforgeeks.org/difference-between-border-gateway-protocol-bgp-and-routing-information-protocol-rip/)

**1。[边界网关协议(BGP)](https://www.geeksforgeeks.org/border-gateway-protocol-bgp/) :**
在 BGP 中，使用传输控制协议。这是一种网状拓扑或设计。它通过两个独立的网络(自治系统或自治系统)交换路由信息来工作。两台路由器同意交换如何到达特定 IP 范围的信息。BGP 使用[传输控制协议(TCP)](https://www.geeksforgeeks.org/tcp-ip-model/) 端口 179。

**2。[路由信息协议(RIP)](https://www.geeksforgeeks.org/routing-information-protocol-rip/) :**
RIP 代表路由信息协议，其中距离矢量路由协议用于数据/数据包传输。在[路由信息协议(RIP)](https://www.geeksforgeeks.org/routing-interface-protocol-rip-v1-v2/) 中，最大跳数为 15，因为它防止了从源到目的地的路由环路。水平分割、路由中毒和保持等机制用于防止不正确或错误的路由信息。莎莉·弗洛伊德和范·雅各布森[1994]建议，在计时器没有轻微随机化的情况下，计时器是同步超时的。与其他路由协议相比，RIP(路由信息协议)较差，规模有限，即网络较小。使用 RIP 的主要优势是它使用了 UDP ( [用户数据报协议](https://www.geeksforgeeks.org/user-datagram-protocol-udp/))。

**边界网关协议(BGP)和路由信息协议(RIP)的区别:**

<center>

| 没有 | 边界网关协议 | 路由信息协议 |
| 1. | BGP 代表边界网关协议。 | RIP 代表路由信息协议。 |
| 2. | 它工作在最佳路径算法上。 | RIP 在[贝尔曼福特算法](https://www.geeksforgeeks.org/bellman-ford-algorithm-dp-23/)上工作。 |
| 3. | 与 RIP 相比，它基本上用于规模非常大的组织。 | 它基本上用于较小规模的组织。 |
| 4. | 它是一个外部网关协议。 | 它是一个行业标准的动态路由协议。 |
| 5. | 它是一种比 RIP 更智能的路由协议。 | 它不是一个非常智能的动态路由协议。 |
| 6. | 网络分为区域和表格。 | 网络分为区域、子区域、自治系统和骨干区域。 |
| 7. | 它根据跳数计算度量。 | 它根据带宽计算度量。 |
| 8. | 是混合型。 | 它是矢量状态类型。 |
| 9. | 跳数没有这样的限制。 | 它最多允许 15 跳。 |

</center>