# 不可路由地址空间

> 原文:[https://www.geeksforgeeks.org/non-routable-address-space/](https://www.geeksforgeeks.org/non-routable-address-space/)

IPv4 标准不支持每个人都有足够的 IP 地址，即 IPv4 地址现在正在耗尽。为了防止 IPv4 耗尽，1996 年发布了 RFC1918(征求意见稿)，它概述了自治系统中任何人都可以使用的网络，称为**不可路由地址空间**。

RFC1918 定义的 IP 地址范围为–

*   10\. 0\. 0\. 0/8 (range: 10.0.0.0–10.255.255.255)
*   12.16.0.0/12 (range: 172.16.0.0–172.31.255.255)
*   92.168.0.0/16 (range: 192

这些 IP 地址是为专用网络保留的，内部网关协议将在网络内路由这些地址空间。不可路由的地址空间允许节点在同一网络上相互通信。由于每台计算机不必连接到互联网上的每台其他计算机，因此不可路由的地址空间可以在各种专用网络中本地使用。

即使计算机必须与另一台计算机通信，而不是在同一网络上，也使用[网络地址转换(NAT)](https://www.geeksforgeeks.org/network-address-translation-nat/) ，其中一个或多个本地 IP 地址被转换为一个或多个全局 IP 地址。由于 NAT 等技术，不可路由的地址空间现在正在使用。在 IPv6 成为 IPv4 地址耗尽的解决方案之前，不可路由的地址空间和 NAT 将有助于防止全球范围内的 IP 地址冲突。

**优势:**

1.  Help to save IPv4 address space.
2.  An extra layer of security, because external gateway routers cannot access these networks. Therefore, the network is protected from malicious software and viruses.
3.  Data protection and privacy-because data can only be accessed inside the network. This is a good thing for small businesses that handle large amounts of data and sensitive information.

**劣势:**

1.  End-to-end IP tracing is lost. It becomes difficult to troubleshoot the network from the remote site.
2.  Isolation: nodes inside the private network cannot be reached by nodes outside the network.
3.  Due to the nonstandard configuration and setting of network interfaces, the maintenance requirements of private networks are higher.

私有 IP 网络由安全性和数据隐私比公共 IP 地址更重要的组织使用。现在，不可路由的地址空间和网络地址转换是节省 IPv4 地址空间的首选，因为 IPv4 地址正在耗尽。