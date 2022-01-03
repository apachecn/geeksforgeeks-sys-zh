# ARP 和 RARP 的区别

> 原文:[https://www . geesforgeks . org/ARP 和-rarp 之间的区别/](https://www.geeksforgeeks.org/difference-between-arp-and-rarp/)

先决条件–[ARP、反向 ARP(RARP)、反向 ARP(InARP)、代理 ARP 和无偿 ARP](https://www.geeksforgeeks.org/computer-network-arp-reverse-arprarp-inverse-arpinarp-proxy-arp-gratuitous-arp/)
在 **[地址解析协议(ARP)](https://www.geeksforgeeks.org/computer-network-arp-works/)** 中，获取接收方的 MAC 地址。通过 ARP，(32 位)IP 地址映射成(48 位)MAC 地址。

而在**反向地址解析协议**中，IP 地址是通过服务器获取的。通过 RARP，(48 位)MAC 地址的 48 位映射成(32 位)IP 地址。

![](img/203bb2582ed70a520b2bc49e518e82ce.png)

让我们看看 ARP 和 RARP 的区别:

| S.NO | 空袭预防措施 | 怪怪的 |
| 1. | ARP 代表地址解析协议。 | 而 RARP 代表反向地址解析协议。 |
| 2. | 通过 ARP，(32 位)IP 地址映射成(48 位)MAC 地址。 | 而通过 RARP，48 位的(48 位)媒体访问控制地址被映射成(32 位)IP 地址。 |
| 3. | 在 ARP 中，使用广播媒体访问控制地址。 | 而在 RARP 中，使用的是广播 IP 地址。 |
| 4. | 在 ARP 中，ARP 表由本地主机管理或维护。 | 而在 RARP 中，RARP 表由 RARP 服务器管理或维护。 |
| 5. | 在地址解析协议中，获取接收方的媒体访问控制地址。 | While in RARP, IP address is fetched.s
 |
| 6. | 在 ARP 中，ARP 表使用 ARP 回复来更新。 | 而在 RARP 中，RARP 表使用 RARP 回复来配置 IP 地址。 |
| 7. | 主机和路由器使用 ARP 来知道网络中其他主机和路由器的 MAC 地址。 | 而 RARP 则由设施较少的小用户使用。 |