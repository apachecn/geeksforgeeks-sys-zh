# SCTP 和 UDP 的区别

> 原文:[https://www . geesforgeks . org/difference-SCTP-and-UDP/](https://www.geeksforgeeks.org/difference-between-sctp-and-udp/)

**1。[流控制传输协议(SCTP)](https://www.geeksforgeeks.org/sctp-full-form/) :**
SCTP 是计算机网络中面向连接的协议，它提供全双工关联，即在网络中已建立连接的两个端点之间同时传输多个数据流。

**2。[用户数据报协议(UDP)](https://www.geeksforgeeks.org/user-datagram-protocol-udp/) :**
UDP 是一种传输层协议。UDP 是互联网协议套件的一部分，称为 UDP/IP 套件。与 TCP 不同，它是一种不可靠且无连接的协议。因此，没有必要在数据传输之前建立连接。UDP 套接字是数据报套接字的一个例子。

**SCTP 和 UDP 的区别:**

<center>

| 参数 | SCTP 议定书 | UDP 协议 |
| 可达性检查 | 我们可以在 SCTP 进行可达性检查。 | UDP 中没有可达性检查。 |
| 多数据流 | SCTP 支持多数据流。 | UDP 不支持多数据流。 |
| 数据传送 | 数据传输在 SCTP 更为现实。 | UDP 中没有可靠的数据传输。 |
| 选择性确认 | SCTP 有选择性的反垄断法。 | UDP 中没有选择性确认。 |
| 多宿主 | SCTP 支持多宿主。 | UDP 不支持多宿主。 |
| 面向连接 | SCTP 协议是面向连接的。 | UDP 协议不是面向连接的。 |
| 部分数据传输 | SCTP 有部分数据传输。 | UDP 中没有部分数据传输。 |
| 有序数据交付 | SCTP 有数据交付订单。 | UDP 不支持有序数据传递。 |

</center>