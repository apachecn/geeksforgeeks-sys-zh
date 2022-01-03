# 控制平面和数据平面的区别

> 原文:[https://www . geesforgeks . org/控制平面和数据平面的区别/](https://www.geeksforgeeks.org/difference-between-control-plane-and-data-plane/)

先决条件–[路由器简介](https://www.geeksforgeeks.org/introduction-of-a-router/)和[路由类型](https://www.geeksforgeeks.org/types-of-routing/)

**1。控制平面:**
在路由中，控制平面是指确定使用哪条路径发送数据包或帧的所有功能和过程。控制平面负责填充路由表、绘制网络拓扑、转发表，从而启用数据平面功能。这意味着路由器做出决定。在一行中，可以说它负责如何转发数据包。

**2。数据平面:**
In Routing 数据平面是指基于控制平面逻辑将数据包/帧从一个接口转发到另一个接口的所有功能和过程。路由表、转发表和路由逻辑构成了数据平面功能。数据平面数据包通过路由器，帧的传入和传出是基于控制平面逻辑完成的。意味着在单行中，可以说它负责将数据包从源移动到目的地。它也被称为转发平面。

**控制平面和数据平面的区别:**

<center>

| 没有。 | 制导机 | 数据平面 |
| 01. | 控制平面是指确定使用哪条路径发送数据包或帧的所有功能和过程。 | 数据平面是指基于控制平面逻辑将数据包/帧从一个接口转发到另一个接口的所有功能和过程。 |
| 02. | 它负责建立和维护 IP 路由表。 | 它负责转发实际的 IP 数据包。 |
| 03. | 控制平面负责如何转发数据包。 | 负责将数据包从源移动到目的地的数据平面。 |
| 04. | 控制平面独立执行其任务。 | 数据平面根据控制平面执行其任务。 |
| 05. | 总的来说，我们可以说，在控制平面上，我们学到了什么以及如何做到这一点。 | 一般来说，我们可以说在数据平面中，实际任务是基于所学知识来执行的。 |
| 06. | 路由器处理控制平面数据包以更新路由表。 | 转发平面/数据平面基于控制平面的构建逻辑来转发分组。 |
| 07. | 包括[生成树协议(STP)](https://www.geeksforgeeks.org/types-of-spanning-tree-protocol-stp/) 、
[地址解析协议(ARP)](https://www.geeksforgeeks.org/how-address-resolution-protocol-arp-works/) 、
[路由信息协议(RIP)](https://www.geeksforgeeks.org/routing-information-protocol-rip/) 、[动态主机配置协议(DHCP)](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/) 等。 | 它包括减少生存时间(TTL)，重新计算
[IP 报头校验和](https://www.geeksforgeeks.org/calculation-of-tcp-checksum/)等。 |
| 08. | 控制平面数据包由路由器本身在本地发起。 | 数据平面包通过路由器。 |
| 09. | 控制平面充当数据转发的决策者。 | 数据平面在数据转发中充当决策实施者。 |
| 10. | 路由在控制平面中执行。 | 切换在数据平面中执行。 |

</center>