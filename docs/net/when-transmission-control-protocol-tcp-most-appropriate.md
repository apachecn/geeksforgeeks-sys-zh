# 传输控制协议(TCP)什么时候最合适？

> 原文:[https://www . geeksforgeeks . org/when-transmission-control-protocol-TCP-最合适/](https://www.geeksforgeeks.org/when-transmission-control-protocol-tcp-most-appropriate/)

[TCP(传输控制协议)](https://www.geeksforgeeks.org/tcp-ip-model/)是传输层的协议。TCP 是一种面向连接、可靠和安全的协议。为了提供可靠的服务，TCP 实现了错误控制、拥塞控制和流量控制。

**TCP 提供的服务:**

*   **处理通信的过程–**
    使用端口号实现。
*   **流传递服务–**
    它允许发送进程以字节流的形式传递数据。
*   **全双工服务–**
    它执行多路复用和解复用。
*   **可靠协议–**
    它使用确认机制来检查和检测数据的到达。
*   **面向连接的服务。**

TCP 使用“后退”和“选择性数据和选择性重复”协议进行可靠的数据传输。TCP 使用两种类型的确认，如下所示

1.  [累计确认(返回-否)](https://www.geeksforgeeks.org/difference-between-go-back-n-and-selective-repeat-protocol/)
2.  [选择性确认(选择性协议)](https://www.geeksforgeeks.org/sliding-window-protocol-set-3-selective-repeat/)

**TCP 的特点:**

**1。流量控制–**
流量控制由 TCP 提供。发送方发送的数据量由接收方控制。这样做是为了防止接收器数据过载。TCP 使用面向字节的流量控制。

**2。错误控制–**
传输层需要可靠，因为底层协议 IP 不可靠。可靠性可以通过误差控制来实现。传输层的错误控制包括:

1.  检测并丢弃损坏的数据包。
2.  跟踪丢失和丢弃的数据包。
3.  识别重复数据包并丢弃它们。
4.  缓冲乱序数据包，直到丢失的数据包到达。

错误控制包括发送和接收传输层。

**3。拥塞控制–**
如果网络负载大于网络容量，就会发生网络拥塞。发送方发送的数据量不是由接收方接收的，而是由网络的拥塞程度决定的。TCP 考虑了网络中的拥塞。

什么时候使用传输控制协议最合适？
因此，**当**需要可靠性时，以及当我们必须发送少量数据并期待其立即响应时，TCP 是最合适的。