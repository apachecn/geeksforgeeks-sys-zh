# 为什么网飞的流媒体视频使用的是 TCP 而不是 UDP？

> 原文:[https://www . geeksforgeeks . org/为什么网飞使用 tcp 而不是 udp 来传输视频/](https://www.geeksforgeeks.org/why-does-netflix-use-tcp-but-not-udp-for-streaming-video/)

**概述:**
在本文中，我们将讨论网飞在其平台上使用哪些技术来流式传输在线电影和网络系列。网飞是一家基于美国订阅的流媒体服务提供商公司。它以基于客户购买的订阅的在线视频、网络系列和电影流而闻名。在线流媒体服务基本上有两种技术——UDP 和 TCP。

[**UDP–用户数据报协议**](https://www.geeksforgeeks.org/user-datagram-protocol-udp/) **:**

*   在消耗大量数据的网站上，它在计算机网络中起到了加快网络效率的重要作用。
*   此外，UDP 不如 TCP 安全，但另一方面，它非常快。
*   从技术上讲，UDP 独立于源和目的地，使用“三次握手技术”进行端到端的数据包传输
*   UDP 的主要目的是实现快速可靠的互联网应用使用和数据传输，不需要数据验证和安全服务。
*   UDP 具有非常少的带宽和延迟，这使得它即使在极好的网络连接中也能工作。
*   当大量用户在特定时间访问信息时，因此我们需要管理流量并显示对他们查询的响应，我们在游戏、视频流、在线会议等领域使用 UDP。

[**TCP–传输控制协议**](https://www.geeksforgeeks.org/services-and-segment-structure-in-tcp/) **:**

*   TCP 的基本用途是将数据包从服务器传送到目标计算机。
*   TCP 利用 IP 的开销来确保大容量互联网连接，并以正确的顺序传输它们，而且它们以相同的顺序交付。
*   TCP 在数据消费应用程序的延迟和数据波动方面存在滞后。
*   TCP 最重要的特点是它保持了对数据安全和验证选项的高度关注。
*   当 UDP 发送不安全的数据包进程对进程消息时，TCP 使用主机对主机消息来实现安全的环境网络。
*   TCP 对于在线流媒体服务是可靠的，因为客户的数据是完全安全的，并保存在安全的手中。
*   TCP 启用 IP 报头，以便以有序的方式生成无错误和无损坏的数据，这样接收器就不会面临任何问题。

**为什么网飞使用 TCP 而不是 UDP :**
网飞使用 TCP 是因为 TCP 对时间非常敏感，不需要端口转发。它有助于实现网络的全部带宽。我们可以在 TCP 中一次压缩更多的数据，并且重新加载的数据包不会造成问题。它还确保了更高的视频质量和更少的网络拥塞问题。TCP 使用端到端连接减少了缓冲和实时流问题。像网飞这样的在线流媒体服务甚至在观众观看之前就开始关注预取和缓冲。TCP 的在线拥塞控制试图通过同时创建不同的链路来转移流量。它还确保在恶意软件或数据包重传失败的情况下进行错误恢复和问题识别。使用 TCP 最重要的原因是很容易监控源和接收器之间的带宽，并据此调整流式节目的视频质量。