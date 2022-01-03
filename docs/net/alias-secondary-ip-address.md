# 别名/二级 IP 地址

> 原文:[https://www.geeksforgeeks.org/alias-secondary-ip-address/](https://www.geeksforgeeks.org/alias-secondary-ip-address/)

在 IP 寻址的上下文中，**别名**是指在单个网络接口上创建和配置多个 [IP 地址](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/)的过程。通过使用别名 IP 地址，您可以为网络上的单个节点创建到网络的多个连接，其中每个连接都可以用于不同的目的。

**二级 IP 地址的特点:**
IP 别名让位于二级 IP 地址的新概念，这意味着您可以在拥有主 IP 地址的同一接口上配置多个二级 IP 地址。这允许您为任何网络接口指定无限数量的辅助地址，如果需要，这些辅助地址可以从虚拟机实例中分离出来。

**示例–**
在 GCP，我们可以配置一个主 CIDR 范围，同时配置一个次范围作为子网的一部分:

*   将 10.1.0.0/16 配置为主 CIDR 范围
*   将 10.2.0.0/20 配置为辅助 CIDR 范围

这里，虚拟机的主 IP 地址是从主 [CIDR 范围](https://www.geeksforgeeks.org/classless-inter-domain-routing-cidr/)分配的，而别名 IP 范围 10.2.1.0/24 是从辅助 CIDR 范围在虚拟机中分配的。

**注意–**
别名 IP 范围内的地址用作 VM 中托管的容器的 IP 地址。

**应用:**
二级 IP 地址一些最常见的应用包括:

*   第二个 IP 地址是一个很好的选择，用于在专用 IP 上托管带有 SSL 证书的网站，因为如果你使用 HTTPS，你需要每个网站一个 IP。
*   如果您希望在您的 IP 上分割资源，以便您可以应用不同的防火墙来进行访问控制或放入一些服务质量规则，那么可以将各种服务分配给不同的 IP。
*   使用辅助 IP 地址对于轻松控制流量非常有用，这取决于您如何在它们之间隔离域名/服务。

例如，如果您在同一个 VLAN 有两个 IP 子网，并且希望在一个子网耗尽时扩展它，或者希望将主机的默认网关从一个地址迁移到另一个地址，则可以为您的设备接口或 Linux 环境配置一个辅助 IP。

**优势:**

*   IP 别名的使用减少了配置多个 IP 所需的多个网卡(网络接口卡)，从而减少了配置时间和成本。
*   它在 Linux Web Servers 上设置多个虚拟站点时也非常有用，例如“Apache”，在一个子网网络上使用一个具有不同 IP 地址的网络接口，我们基本上称之为基于 IP 的虚拟主机。
*   您可以自由地将应用程序和网页整合到一台服务器上，而无需更改应用程序代码。

**缺点:**
因此，IP 别名没有缺点，它的使用完全取决于您的要求，因为您可以指定无限数量的辅助地址。但另一方面，如果您想增加主机数量，建议仅在角落情况下使用辅助 IP，因为它会产生更多的广播流量。

另外，二级地址不支持 [DHCP](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/) 。[路由器](https://www.geeksforgeeks.org/introduction-of-a-router/)会将其主接口 IP 地址插入 DHCP 请求中，远程服务器将永远看不到对辅助子网的请求。