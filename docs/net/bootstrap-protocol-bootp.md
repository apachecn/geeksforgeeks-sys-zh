# 引导协议(BOOTP)

> 原文:[https://www.geeksforgeeks.org/bootstrap-protocol-bootp/](https://www.geeksforgeeks.org/bootstrap-protocol-bootp/)

**概述:**
在本文中，我们将讨论自举协议，以及它如何在维护网络上连接设备之间的协议中发挥重要作用。 [**引导协议(BOOTP)**](https://www.geeksforgeeks.org/difference-between-bootp-and-dhcp/) 是一种网络协议，网络管理人员使用该协议向该网络的每个成员提供 IP 地址，以便主服务器参与其他网络设备。

**Bootstrap 协议的重要特性:**
在这里，我们将讨论 Bootstrap 协议的特性如下。

*   引导协议(BOOTP)是一种基本协议，一旦连接到网络，它会自动为网络连接中的每个参与者提供一个唯一的 IP 地址，用于识别和身份验证。这有助于服务器加速数据传输和连接请求。
*   BOOTP 使用独特的 IP 地址算法，在几分之一秒内为网络上的每个系统提供完全不同的 IP 地址。
*   这缩短了服务器和客户端之间的连接时间。它开始下载和更新源代码的过程，即使只有很少的信息。
*   BOOTP 使用 **DHCP** (动态主机配置协议)和 **UDP** (用户数据报协议)的组合来请求和接收来自各种网络连接参与者的请求，并处理他们的响应。
*   在 BOOTP 连接中，服务器和客户端只需要一个 IP 地址和一个网关地址就可以建立成功的连接。通常，在 BOOTP 网络中，服务器和客户端共享同一个局域网，网络中使用的路由器必须支持 BOOTP 桥接。
*   具有 TCP / IP 配置的网络的一个很好的例子是引导协议网络。每当网络上的计算机向服务器请求特定请求时，BOOTP 都会使用其唯一的 IP 地址来快速解决它们。

【Bootstrap 协议与 DHCP 的区别:
[**DHCP**](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/) 网络服务器的用途比 [**BOOTP**](https://www.geeksforgeeks.org/difference-between-bootp-and-dhcp/) 网络服务器广泛得多。当用户向服务器请求特定的 IP 地址时，它可以用于该目的，并且它只给出该特定 IP 地址的响应，因此，不会浪费时间来监视其他地址。BOOTP 通过[**IPv4 地址**](https://www.geeksforgeeks.org/what-is-ipv4/) 连接使用 [**UDP**](https://www.geeksforgeeks.org/user-datagram-protocol-udp/) (用户数据报协议)来识别和认证每个网络用户。此外，BOOTP 连接有一个稳定的静态 IP 地址数据库，可以立即为客户端提供所需的 IP 地址。

**Bootstrap 协议的工作:**
在这里，我们将讨论 Bootstrap 协议的工作步骤如下。

*   一开始，每个网络参与者都没有一个 IP 地址。然后，网络管理员使用 IPv4 协议为网络上的每台主机提供一个唯一的 IP 地址。
*   客户端使用 TCP / IP 介入在其计算机系统上安装 BOOTP 网络协议，以确保在连接到该网络时与所有网络协议兼容。
*   然后，BOOTP 网络管理员发送包含有效单播地址的消息。该单播地址随后由主服务器转发给 BOOTP 客户端。

**Bootstrap 协议的用途:**
这里，我们将讨论 Bootstrap 协议的用途如下。

1.  首次启动计算机时，引导程序(BOOTP)主要用于检查网络上的系统。记录网络上每台计算机的基本输入输出系统周期，使计算机的主板和网络管理器能够在计算机启动时有效地组织数据传输。
2.  BOOTP 主要用于无盘环境，不需要介质，因为所有数据都存储在网络云中，可以高效使用。
3.  BOOTP 是客户端和服务器之间的数据传输，通过网络服务器发送和接收请求和相应的响应。
4.  BOOTP 支持使用主板和网络管理器，因此不需要云网络之外的外部存储。