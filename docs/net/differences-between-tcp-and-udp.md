# TCP 和 UDP 的区别

> 原文:[https://www . geesforgeks . org/differences-TCP 和-udp/](https://www.geeksforgeeks.org/differences-between-tcp-and-udp/)

先决条件–[传输层职责](https://www.geeksforgeeks.org/computer-network-transport-layer-responsibilities/)、 [TCP](https://www.geeksforgeeks.org/computer-network-tcp-congestion-control/) 、 [UDP](https://www.geeksforgeeks.org/computer-network-user-datagram-protocol-udp/)

<figure class="table">

| 基础 | 传输控制协议 | 用户数据报协议 |
| --- | --- | --- |
| 服务类型 | TCP 是一种面向连接的协议。面向连接意味着通信设备应该在传输数据之前建立连接，并且应该在传输数据之后关闭连接。 | UDP 是面向数据报的协议。这是因为没有打开连接、维护连接和终止连接的开销。UDP 对于广播和多播类型的网络传输是有效的。 |
| 可靠性 | TCP 是可靠的，因为它保证向目的路由器传送数据。 | 在 UDP 中无法保证向目的地传送数据。 |
| 错误检查机制 | TCP 提供了广泛的错误检查机制。这是因为它提供了流量控制和数据确认。 | UDP 只有使用校验和的基本错误检查机制。 |
| 承认 | 存在确认段。 | 没有确认段。 |
| 顺序 | 数据排序是传输控制协议的一个特征。这意味着数据包按顺序到达接收器。 | UDP 中没有数据排序。如果需要订单，必须由应用层管理。 |
| 速度 | TCP 比 UDP 相对慢。 | UDP 比 TCP 更快、更简单、更高效。 |
| 中继 | 在 TCP 中可以重传丢失的数据包，但在 UDP 中不能。 | 用户数据报协议(UDP)中没有丢失数据包的重传。 |
| 标题长度 | TCP 有一个(20-60)字节的可变长度报头。 | UDP 有一个 8 字节的固定长度报头。 |
| 重量 | TCP 很重。 | UDP 是轻量级的。 |
| 握手技术 | 使用握手，如同步、确认、同步确认 | 这是一个无连接协议，即没有握手 |
| 广播 | TCP 不支持广播。 | UDP 支持广播。 |
| 协议 | HTTP、HTTPs、FTP、SMTP 和 Telnet 都使用 TCP。 | 域名系统、DHCP、TFTP、简单网络管理协议、RIP 和网络电话都使用 UDP。 |
| 流类型 | TCP 连接是一个字节流。 | UDP 连接是消息流。 |
| 开销 | 低但高于 UDP。 | 非常低。 |

一个简单的例子来清楚地理解这些区别:
假设有两所房子，H1 和 H2，一封信必须从 H1 寄到 H2。但是在那两栋房子之间有一条河。现在我们该如何寄信？
解决方案 1:在河上打一座桥，然后就可以交付了。
解决方案 2:通过鸽子送过去。

将第一种解决方案视为 TCP。必须建立连接(桥接)才能传送数据(信件)。
数据是可靠的，因为它会直接到达另一端，不会丢失数据或出错。
第二种解决方案是 UDP。发送数据不需要连接。
与需要建立连接(桥)的 TCP 相比，这个过程更快。但是数据并不可靠:我们不知道鸽子会不会走对方向，或者它会不会在途中掉信，或者在中途遇到一些问题。

</figure>