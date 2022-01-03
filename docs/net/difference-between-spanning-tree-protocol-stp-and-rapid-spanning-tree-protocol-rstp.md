# 生成树协议(STP)和快速生成树协议(RSTP)的区别

> 原文:[https://www . geesforgeks . org/生成树协议-stp 和快速生成树协议-rstp 之间的区别/](https://www.geeksforgeeks.org/difference-between-spanning-tree-protocol-stp-and-rapid-spanning-tree-protocol-rstp/)

**1。** [**生成树协议(STP)**](https://www.geeksforgeeks.org/introduction-of-spanning-tree-protocol-stp/) **:**
STP 又称生成树协议是一种第 2 层(数据链路层)协议，它运行在交换机和网桥上。STP 的 IEEE 标准是 802.1D。STP 是使用冗余交换机时用于防止环路的功能。例如，我们有三个交换机，它们都连接在一起，如果没有 STP，可能会形成一个环路，导致几个问题，如堵塞网络、广播风暴等。最终甚至会导致开关失效。

**2。** [**快速生成树协议(RSTP)**](https://www.geeksforgeeks.org/types-of-spanning-tree-protocol-stp/) **:**
快速生成树协议(RDTP)是生成树协议的增强版。RSTP 的 IEEE 标准是 802.1w，STP 和 RSTP 有很多相似之处，RSTP 向后兼容 STP。它通过阻塞不必要的端口来避免网络环路。

**STP 和 RSTP 的区别:**

<figure class="table">

| **序列号**

 | STP | **RSTP** |
| 1. | 它的 IEEE 标准是 802.1D。 | 它的 IEEE 标准是 802.1W。 |
| 2. | 在 STP 中，只有根桥发送 BPDU(网桥协议数据单元)，它由其他网桥传输。 | 在 RSTP，所有的桥都可以转发 BPDUs。 |
| 3. | STP 有三个端口角色(即根端口、指定端口、阻塞端口)。 | RSTP 有四个端口角色(即根端口、指定端口、备用端口、备份端口)。 |
| 4. | STP 有五种端口状态(即转发、学习、侦听、阻塞、禁用)。 | RSTP 有三个端口状态(即转发、学习、丢弃)。 |
| 5. | 它没有任何链接类型。 | 它有两种链接类型，即共享链接和点对点链接。 |
| 6. | STP 提供了较慢的网络收敛作为响应。 | RSTP 提供了明显更快的网络融合。 |
| 7. | STP 中使用的标志位是 TCN 的位 0(拓扑变化通知)和 TCA 的位 7(拓扑变化确认)。 | RSTP 使用的标志位是 TCN 的位 0、提案的位 1、端口角色的位 2 和位 3、学习的位 4、转发的位 5、协议的位 6 和 TCN 的位 7。 |

</figure>