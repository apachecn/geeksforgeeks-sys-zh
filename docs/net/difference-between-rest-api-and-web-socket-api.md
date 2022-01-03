# 【Rest API 和 Web Socket API 的区别

> 原文:[https://www . geesforgeks . org/rest-API 和-web-socket-api 的区别/](https://www.geeksforgeeks.org/difference-between-rest-api-and-web-socket-api/)

在[物联网](https://www.geeksforgeeks.org/introduction-to-internet-of-things-iot-set-1/)中，有 2 个通信 API–

*   基于休息的通信接口
*   基于网络套接字的通信接口

网络服务可以使用 REST 原则或网络套接字协议来实现–

**1。** [**【基于 REST 的通信 API】**](https://www.geeksforgeeks.org/rest-api-introduction/)**:**
代表性状态转移(REST)是一组架构原则，通过这些原则，您可以设计专注于系统资源以及如何处理和转移资源状态的网络服务和网络 API。REST APIs 遵循请求-响应通信模型。REST 架构约束适用于分布式超媒体系统中的组件、连接器和数据元素。

**2。** [**基于网络套接字的通信接口**](https://www.geeksforgeeks.org/what-is-web-socket-and-how-it-is-different-from-the-http/) **:**
网络套接字接口允许客户端和服务器之间的双向全双工通信。它遵循独占对通信模式。此通信应用编程接口不需要为客户端和服务器之间发送的每个消息建立新的连接。一旦建立了连接，就可以不间断地连续发送和接收消息。WebSocket APIs 适用于低延迟或高吞吐量需求的物联网应用。

【Rest API 和 Web Socket API 的区别:

<figure class="table">

| 没有 | 休息应用编程接口 | websocket api |
| --- | --- | --- |
| 1. | 它是无状态协议。它不会存储数据。 | 它是有状态协议。它将存储数据。 |
| 2. | 它是单向的。只有服务器或客户端会通信。 | 它是双向的。服务器或客户端都可以接收或发送消息。 |
| 3. | 它是请求-响应模型。 | 它是全双工模式。 |
| 4. | HTTP 请求包含标题部分，标题部分。 | 适合实时应用。它没有任何开销。 |
| 5. | 将为每个 HTTP 请求建立新的 TCP 连接。 | 仅单个 TCP 连接。 |
| 6. | 横向和纵向扩展(我们可以横向和纵向添加许多资源和用户数量)。 | 只有垂直缩放(我们只能垂直添加资源)。 |
| 7. | 它依赖于 HTTP 方法来检索数据.. | 检索数据取决于 IP 地址和端口号 |
| 8. | 在消息传输方面，它比 web socket 慢。 | web socket 传输消息的速度比 REST API 快得多。 |
| 9. | 它不需要内存或缓冲区来存储数据。 | 它需要内存和缓冲区来存储数据。 |

</figure>