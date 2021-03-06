# SCTP 完整版

> 原文:[https://www.geeksforgeeks.org/sctp-full-form/](https://www.geeksforgeeks.org/sctp-full-form/)

SCTP 代表**流控制传输协议**。

它是计算机网络中面向连接的协议，提供全双工关联，即在网络中已建立连接的两个端点之间同时传输多个数据流。它有时被称为下一代传输控制协议或传输控制协议，SCTP 使它更容易支持互联网上的电话交谈。电话交谈需要在两端同时传输语音和其他数据，SCTP 协议使建立可靠的连接变得更加容易。

SCTP 还旨在使通过无线网络建立连接和管理多媒体数据传输变得更加容易。SCTP 是一个标准协议(RFC 2960)，由互联网工程任务组(IETF)开发。

**SCTP 特色:**

1.  **多属性单播–**
    它是一种点对点协议，可以使用不同的路径到达终端主机。
2.  **可靠传输–**
    它使用 SACK 和校验和来检测损坏、损坏、丢弃、复制和重新排序的数据。它类似于 TCP，但是 SCTP 在数据重新排序方面效率更高。
3.  **面向消息–**
    每个消息都可以被框架化，我们可以保持数据流的顺序和结构上的标签。为此，在 TCP 中，我们需要一个不同的抽象层。
4.  **多归位–**
    它可以在两个端点之间建立多条连接路径，不需要依靠 IP 层进行恢复。

**SCTP 优势:**

1.  这是一种全双工连接，即用户可以同时发送和接收数据。
2.  它允许半封闭连接。
3.  消息的边界得到维护，应用程序不必拆分消息。
4.  它同时具有 TCP 和 UDP 协议的特性。
5.  It doesn’t rely on IP layer for resilience of paths.

    **SCTP 的劣势:**

    1.  一个关键的挑战是它需要改变节点上的传输堆栈。
    2.  需要修改应用程序以使用 SCTP，而不是 TCP/UDP。
    3.  需要修改应用程序来处理多个并发流。