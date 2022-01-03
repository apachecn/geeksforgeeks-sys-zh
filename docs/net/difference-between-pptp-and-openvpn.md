# PPTP 和 OpenVPN 的区别

> 原文:[https://www . geesforgeks . org/difference-PPTP-and-openvpn/](https://www.geeksforgeeks.org/difference-between-pptp-and-openvpn/)

先决条件–[虚拟专用网络类型](https://www.geeksforgeeks.org/types-of-virtual-private-network-vpn-and-its-protocols/)
**1。[点对点隧道协议(PPTP)](https://www.geeksforgeeks.org/pptp-full-form/) :**
PPTP 是微软推出的。这是一组实现虚拟专用网络的通信规则，允许组织通过隧道扩展其专用网络到公共互联网。它能够通过创建基于 TCP / IP 的网络(如虚拟专用网络)来创建从远程客户端到私有企业网络的数据传输的安全路由。

PPTP 提供以下优势–

*   低硬件成本
*   安全增强
*   低传输成本
*   降低管理费用

**2。**
OpenVPN 是由 James Yonan 推出的。它是用于实现虚拟专用网连接的最先进、更可靠、更流行的开源软件应用程序。

它更灵活，用于–

*   您想要高安全性的高级解决方案
*   您需要特殊的功能，例如特定的隧道
*   Internet provider blocked you or you want to ignore restrictive firewalls.

    **PPTP 和 OpenVPN 的区别:**

    | S.NO | PPTP | OpenVPN |
    | --- | --- | --- |
    | 1. | 这是一种有助于实现虚拟专用网络的协议。 | 而 OpenVPN 是一个开源软件解决方案，有助于实现 VPN。 |
    | 2. | 微软引进了 PPTP。 | 而它是由一个叫詹姆斯·约南的人写的。 |
    | 3. | 与 OpenVPN 相比，PPTP 的速度非常快。 | 而它相对较慢。 |
    | 4. | 在 PPTP，使用 GRE 协议和端口号 1723。 | 虽然端口号 1194 用于此，但它可以更改为任何人。 |
    | 5. | 与 OpenVPN 相比，PPTP 在不稳定的网络连接上不太可靠。 | 而 OpenVPN 在不稳定的网络连接上相对更可靠。 |
    | 6. | 与 OpenVPN 相比，PPTP 不容易恢复。 | 相对而言，它很容易恢复。 |
    | 7. | PPTP 有一些主要的安全弱点。 | 而在 OpenVPN 中，没有这种已知的主要弱点。 |
    | 8. | 防火墙很容易封锁 PPTP。 | 而它可以通过在某个已知端口号(如 443)上安装一个端口来绕过多个防火墙。 |
    | 9. | PPTP 在世界范围内使用较少。 | 而 OpenVPN 的应用更为广泛。 |