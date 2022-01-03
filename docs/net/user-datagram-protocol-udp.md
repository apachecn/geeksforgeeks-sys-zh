# 用户数据报协议

> 原文:[https://www.geeksforgeeks.org/user-datagram-protocol-udp/](https://www.geeksforgeeks.org/user-datagram-protocol-udp/)

**用户数据报协议(UDP)** 是传输层协议。UDP 是互联网协议套件的一部分，称为 UDP/IP 套件。与 TCP 不同，它是一个不可靠的无连接的 T2 协议。所以，在数据传输之前不需要建立连接。

虽然传输控制协议是大多数互联网服务使用的主要传输层协议；提供有保证的交付、可靠性等等，但是所有这些服务都要花费我们额外的开销和延迟。这里，UDP 进入画面。用于实时服务，如电脑游戏、语音或视频通信、现场会议；我们需要 UDP。由于需要高性能，UDP 允许丢弃数据包，而不是处理延迟的数据包。UDP 中没有错误检查，所以也节省了带宽。
用户数据报协议(UDP)在延迟和带宽方面都更高效。

**UDP 报头–**

UDP 报头是一个 8 字节的固定和简单的报头，而对于 TCP 来说，它可能从 20 字节到 60 字节不等。前 8 个字节包含所有必要的报头信息，其余部分由数据组成。UDP 端口号字段均为 16 位长，因此端口号的范围定义为 0 到 65535；端口号 0 被保留。端口号有助于区分不同的用户请求或进程。

![](img/30287f15f86b80ef473ac7c04dc0ddac.png)

1.  **源端口:**源端口是一个 2 字节长的字段，用于标识源的端口号。
2.  **目的端口:**这是一个 2 字节长的字段，用于标识目的数据包的端口。
3.  **长度:**长度是 UDP 的长度，包括报头和数据。这是一个 16 位字段。
4.  **校验和:**校验和是 2 字节长的字段。它是 UDP 报头、来自 IP 报头的信息的伪报头和数据的 1 的补码和的 16 位 1 的补码，在末尾用零个八位字节填充(如果需要)以形成两个八位字节的倍数。

**注意–**与 TCP 不同，在 UDP 中校验和计算不是强制性的。UDP 不提供错误控制或流量控制。因此，UDP 依赖于 IP 和 ICMP 进行错误报告。

**UDP 的应用:**

*   当数据量较少时，用于简单的请求-响应通信，因此不太关心流量和错误控制。
*   它是一个适合多播的协议，因为 UDP 支持分组交换。
*   UDP 用于一些路由更新协议，如 RIP(路由信息协议)。
*   通常用于不能容忍接收消息各部分之间不均匀延迟的实时应用。
*   以下实现使用 UDP 作为传输层协议:
    *   网络时间协议
    *   域名服务
    *   BOOTP，DHCP。
    *   网络新闻协议
    *   每日协议报价
    *   TFTP，RTSP，RIP。
*   应用层可以通过 UDP 完成一些任务
    *   traceroute
    *   记录路线
    *   时间戳
*   UDP 从网络层获取数据报，附加其报头，并将其发送给用户。所以，它工作得很快。
*   实际上，如果去掉校验和字段，UDP 就是一个空协议。
    1.  降低对计算机资源的要求。
    2.  使用多播或广播传输时。
    3.  实时数据包的传输，主要在多媒体应用中。

1.  [GATE CS 2013，第 12 题](https://www.geeksforgeeks.org/gate-gate-cs-2013-question-12/)
2.  [GATE CS 2012，问题 65](https://www.geeksforgeeks.org/gate-gate-cs-2012-question-22-2/)
3.  [GATE CS 2007，第 20 题](https://www.geeksforgeeks.org/gate-gate-cs-2007-question-20/)
4.  [GATE CS 2005，问题 23](https://www.geeksforgeeks.org/gate-gate-cs-2005-question-23/)
5.  [GATE IT 2008，问题 66](https://www.geeksforgeeks.org/gate-gate-it-2008-question-66/)
6.  [GATE Mock 2015，问题 5](https://www.geeksforgeeks.org/gate-gate-cs-2015-mock-test-question-5/)