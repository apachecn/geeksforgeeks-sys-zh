# 本地广播和环回地址

> 原文:[https://www . geesforgeks . org/local-broadcast-and-loopback-address/](https://www.geeksforgeeks.org/local-broadcast-and-loopback-address/)

**[本地广播地址](https://www.geeksforgeeks.org/computer-network-difference-unicast-broadcast-multicast/) :**
本地广播地址用于与本地网络上的所有设备进行通信。它由二进制的 255.255.255.255 或 111111111 . 11111111 . 1111111111 . 1111111111 表示。
主机使用广播地址向 [DHCP(动态主机配置协议)](https://www.geeksforgeeks.org/computer-network-dynamic-host-configuration-protocol-dhcp/)服务器请求 IP 地址。主机向广播地址发送广播请求一个 IP 地址，然后 DHCP 服务器从 IP 地址池中分配一个 IP 地址。
默认情况下，本地广播地址总是被路由器和第 3 层交换机丢弃；但是可以通过配置 DHCP 转发或 DHCP 中继来覆盖这一点。

**[本地环回地址](https://practice.geeksforgeeks.org/problems/what-is-loopback-address) :**
本地环回地址用于让系统向自身发送消息，确保机器上正确安装了 TCP/IP 栈。
在 [IPv4](https://www.geeksforgeeks.org/differences-between-ipv4-and-ipv6/) 中，以十进制 127 开头或第一个八位字节中有 01111111 的 IP 地址是环回地址(127。十.十.十)。通常，127.0.0.1 用作本地环回地址。
这导致了很多潜在 IP 地址的浪费。但是在 IPv6 中::1 被用作本地环回地址，因此没有任何地址浪费。