# 数据报传送协议(DDP)

> 原文:[https://www . geesforgeks . org/data pack-delivery-protocol-DDP/](https://www.geeksforgeeks.org/datagram-delivery-protocol-ddp/)

**数据报传递协议(DDP)** 是 AppleTalk 的成员(AppleTalk 是最初为苹果电脑创建的一组局域网通信协议。)网络协议套件，处理通过 AppleTalk 网络进行的套接字到套接字数据报传递。

**应用:**
任何可以容忍丢包的应用都可以使用 DDP。AppleTalk 的所有应用程序级协议都建立在 DDP 之上。

**它是如何工作的？**
DDP 的主要功能是传输和接收。

*   **传输—** 从上层套接字客户端接收的数据附加 DDP 头，然后转发到数据链路层协议。
*   **接收—** 从数据链路层接收的数据帧将被检查并转发到相应的套接字。

**优点和缺点:**
DDP 是[无连接协议](https://www.geeksforgeeks.org/difference-between-connection-oriented-and-connection-less-services/)，它关注与建立和断开连接相关的较少处理。因此，它比添加这些服务的高级协议更快。该协议非常适合不需要可靠数据传输的应用。

其他需要无缝流量的应用也可以在[网络层](https://www.geeksforgeeks.org/design-issues-in-network-layer/)使用 DDP。但是，任何上层协议都需要确保可靠性。