# 为什么 DNS 使用 UDP 而不是 TCP？

> 原文:[https://www . geesforgeks . org/为什么-DNS-使用-UDP-而不是-tcp/](https://www.geeksforgeeks.org/why-does-dns-use-udp-and-not-tcp/)

DNS 是一种应用层协议。所有应用层协议都使用两种传输层协议之一，即 UDP 和 TCP。TCP 可靠，UDP 不可靠。DNS 应该是可靠的，但是它用的是 UDP，为什么？

关于传输层上的 TCP 和 UDP，有以下有趣的事实证明了上述观点。
**1)** UDP 要快得多。TCP 很慢，因为它需要三次握手。DNS 服务器上的负载也是一个重要因素。DNS 服务器(因为它们使用 UDP)不必保持连接。
**2)** DNS 请求通常非常小，非常适合 UDP 段。
**3)** UDP 不可靠，但可靠性可以加到应用层。应用程序可以使用 UDP，并且可以通过在应用层使用超时和重新发送来变得可靠。

实际上，域名系统主要使用端口号 53 上的用户数据报协议来服务请求。DNS 查询由来自客户端的单个 UDP 请求和来自服务器的单个 UDP 回复组成。当答案的长度超过 512 字节并且客户端和服务器都支持 EDNS 时，将使用更大的 UDP 数据包。否则，将使用传输控制协议再次发送查询。TCP 也用于区域传输等任务。有些解析器实现对所有查询都使用 TCP。

https://en.wikipedia.org/wiki/Domain_Name_System#DNS_protocol_transport 

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。