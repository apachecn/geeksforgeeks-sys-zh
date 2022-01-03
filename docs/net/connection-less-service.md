# 无连接服务

> 原文:[https://www.geeksforgeeks.org/connection-less-service/](https://www.geeksforgeeks.org/connection-less-service/)

无连接服务是一种在数据通信中使用的技术，用于在第 4 层，即[开放系统互连模型](https://www.geeksforgeeks.org/layers-of-osi-model/)的传输层发送或传输数据或消息。此服务不需要发送方或源与接收方或目的地之间的会话连接。发送方开始向目的地传输或发送数据或消息。

换句话说，我们可以说无连接服务仅仅意味着节点可以向其接收者传输或发送数据包或消息，即使没有与接收者的会话连接。信息在没有事先安排的情况下发送或传输。这通常是因为错误处理协议允许并允许纠正错误，就像请求重传一样。

在这种服务中，网络每次向发送方发送一个数据包，与其他数据包无关。但是网络没有任何状态信息来确定或识别分组是否是其他分组流的一部分。甚至网络也没有任何关于用户将传输的流量的知识和信息。在这种情况下，每个数据包都有源地址或目的地址，并独立地从源路由到目的地。

因此，数据包或消息可能通过不同的路径到达目的地。数据包也称为数据报。它也类似于邮政服务，因为它也携带完整的目的地地址，信息将被发送。数据也在一个方向上从源发送到目的地，而不检查目的地是否仍然存在，或者接收者或目的地是否准备接受消息。

**无连接协议:**
这些协议只是允许在进程之间没有任何链接的情况下传输数据。一些数据包在传输过程中也可能丢失。无连接服务的一些协议如下:

*   **Internet Protocol (IP) –**
    This protocol is connectionless. In this protocol, all packets in IP network are routed independently. They might not go through same route.
*   **[User Datagram Protocol (UDP)](https://www.geeksforgeeks.org/user-datagram-protocol-udp/) –**
    This protocol does not establish any connection before transferring data. It just sends data that’s why UDP is known as connectionless.
*   **[Internet Control Message Protocol (ICMP)](https://www.geeksforgeeks.org/internet-control-message-protocol-icmp/) –**
    ICMP is called connectionless simply because it does not need any hosts to handshake before establishing any connection.
*   **互联网分组交换(IPX)–**
    IPX 被称为无连接，因为它不需要在数据包或消息从一个系统传输到另一个系统时保持任何一致的连接。

**无连接服务的类型:**

<center>

| 服务 | 例子 |
| 不可靠的数据报 | 电子垃圾邮件等。 |
| 确认数据报 | 挂号邮件、短信以及投递报告等。 |
| 请求回复 | 来自远程数据库的查询等。 |

</center>

**优势:**

*   它非常快，并且还允许多播和广播操作，其中类似的数据在单次传输中被传输到不同的接收者。
*   通过在应用程序协议中实现纠错，可以减少任何错误的影响。
*   这项服务非常简单，开销也很低。
*   在网络层，主机软件要简单得多。
*   此服务不需要身份验证。
*   有些应用程序甚至不需要数据包或数据的顺序传递。例子包括分组语音等。

**缺点:**

*   与面向连接的服务相比，这种服务不太可靠。
*   它不保证数据包不会丢失、出错、错误传送、重复或无序传送。
*   他们更倾向于网络拥塞。