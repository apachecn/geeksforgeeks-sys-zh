# TCP 定时器

> 原文:[https://www.geeksforgeeks.org/tcp-timers/](https://www.geeksforgeeks.org/tcp-timers/)

TCP 使用几个计时器来确保在通信过程中不会遇到过度的延迟。这些计时器中有几个是优雅的，处理的问题在第一次分析时并不明显。TCP 使用的每一个计时器都将在下面的章节中讨论，这些章节揭示了它在确保数据从一个连接正确发送到另一个连接中的作用。

**TCP 实现使用四个定时器–**

1.  **重传定时器–**为了重传丢失的数据段，TCP 使用重传超时(RTO)。当 TCP 发送一个数据段时，计时器开始计时，并在收到确认时停止计时。如果计时器超时，将发生超时，并重新传输数据段。RTO(重传超时为 1 RTT)要计算重传超时，我们首先需要计算 RTT(往返时间)。
    T3】RTT 三型–
    *   **测量的 RTT 时间(RTTm)–**测量的路段往返时间是该路段到达目的地并被确认所需的时间，尽管确认可能包括其他路段。
    *   **平滑 RTT(RTTs)–**是 RTTm 的加权平均值。RTTm 很可能会发生变化，其波动如此之大，以至于无法使用单次测量来计算 RTO。

```
Initially -> No value
After the first measurement -> RTTs=RTTm
After each measurement -> RTTs= (1-t)*RTTs + t*RTTm
Note: t=1/8 (default if not given)
```

*   **偏离 RTT(RTTd)–**大多数实现并不单独使用 RTTs，所以 RTT 偏离也是为了找出 RTO。

```
Initially -> No value
After the first measurement -> RTTd=RTTm/2
After each measurement -> RTTd= (1-k)*RTTd + k*(RTTm-RTTs)
Note: k=1/4 (default if not given)
```

1.  **持久定时器–**为了处理零窗口大小的死锁情况，TCP 使用持久定时器。当发送的 TCP 收到窗口大小为零的确认时，它会启动一个持续计时器。当持续计时器关闭时，发送的 TCP 发送一个称为探测的特殊段。该段仅包含 1 字节的新数据。它有一个序列号，但它的序列号永远不会被确认；它甚至在计算其余数据的序列号时被忽略。探测导致接收的 TCP 重新发送丢失的确认。
2.  **保持活动计时器–**保持活动计时器用于防止两个 TCP 之间长时间的空闲连接。如果客户端打开与服务器的 TCP 连接，传输一些数据并保持静默，客户端将崩溃。在这种情况下，连接将永远保持打开状态。所以使用了保活定时器。每次服务器收到客户端的消息时，都会重置该计时器。超时时间通常为 2 小时。如果服务器在 2 小时后没有收到客户端的消息，它会发送一个探测段。如果在 10 次探测(每次间隔 75 秒)后没有响应，它会假设客户端关闭并终止连接。
3.  **Time Wait Timer –** This timer is used during [tcp connection termination](https://www.geeksforgeeks.org/computer-network-tcp-connection-termination/). The timer starts after sending the last Ack for 2nd FIN and closing the connection.

    *TCP 连接关闭后，仍在网络中传输的数据报可能会尝试访问关闭的端口。静默计时器旨在防止刚刚关闭的端口再次快速重新打开并接收这些最后的数据报。*

    **静默定时器**通常被设置为最大段生存期的两倍(与 IP 报头中的生存时间字段的值相同)，以确保所有仍然去往该端口的段都已被丢弃。

**参考–**
[TCP 定时器–Que10](http://www.ques10.com/p/9848/explain-tcp-timers-1/)

本文由 [**SHAURYA UPPAL**](https://www.linkedin.com/in/shaurya-uppal-3b7a6373/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。