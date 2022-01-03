# 虚拟专用网络的类型及其协议

> 原文:[https://www . geesforgeks . org/虚拟专用网络的类型-vpn 及其协议/](https://www.geeksforgeeks.org/types-of-virtual-private-network-vpn-and-its-protocols/)

虚拟专用网代表[虚拟专用网络(VPN)](https://www.geeksforgeeks.org/virtual-private-network-vpn-introduction/) ，允许用户通过互联网安全、私密地连接到专用网络。虚拟专用网创建一个加密的连接，称为虚拟专用网隧道，所有互联网流量和通信都通过这个安全的隧道。

虚拟专用网络基本上有两种类型:

1.  **Remote Access VPN:**
    Remote Access VPN permits a user to connect to a private network and access all its services and resources remotely. The connection between the user and the private network occurs through the Internet and the connection is secure and private. Remote Access VPN is useful for home users and business users both.

    一个公司的员工，当他/她不在办公室时，使用虚拟专用网络连接到他/她的公司的专用网络，并远程访问专用网络上的文件和资源。虚拟专用网的私人用户或家庭用户，主要使用虚拟专用网服务绕过互联网上的区域限制，访问被阻止的网站。意识到互联网安全的用户也使用虚拟专用网服务来增强他们的互联网安全和隐私。

2.  **Site to Site VPN:**
    A Site-to-Site VPN is also called as Router-to-Router VPN and is commonly used in the large companies. Companies or organizations, with branch offices in different locations, use Site-to-site VPN to connect the network of one office location to the network at another office location.

    *   **基于内部网的虚拟专用网:**当同一公司的几个办公室使用站点到站点的虚拟专用网类型连接时，称为基于内部网的虚拟专用网。
    *   **基于外联网的 VPN:** 当公司使用站点到站点的 VPN 类型连接到另一家公司的办公室时，称为基于外联网的 VPN。

    基本上，站点到站点 VPN 在地理位置较远的办公室的网络之间创建一个想象中的桥梁，并通过互联网将它们连接起来，维持网络之间的安全和私有通信。在站点到站点虚拟专用网中，一台路由器充当虚拟专用网客户端，另一台路由器充当虚拟专用网服务器，因为它是基于路由器到路由器的通信。当两台路由器之间的身份验证通过后，通信才开始。

**虚拟专用网络(VPN)协议类型:**

1.  **Internet Protocol Security (IPSec):**
    Internet Protocol Security, known as IPSec, is used to secure Internet communication across an IP network. IPSec secures Internet Protocol communication by verifying the session and encrypts each data packet during the connection.

    IPSec 以两种模式运行:

    *   ㈠运输方式
    *   ㈡隧道模式

    传输模式的工作是加密数据包中的消息，隧道模式加密整个数据包。IPSec 还可以与其他安全协议一起使用，以改进安全系统。

2.  **Layer 2 Tunneling Protocol (L2TP):**
    L2TP or Layer 2 Tunneling Protocol is a tunneling protocol that is often combined with another VPN security protocol like IPSec to establish a highly secure VPN connection. L2TP generates a tunnel between two L2TP connection points and IPSec protocol encrypts the data and maintains secure communication between the tunnel.
3.  **Point–to–Point Tunneling Protocol (PPTP):**
    PPTP or Point-to-Point Tunneling Protocol generates a tunnel and confines the data packet. Point-to-Point Protocol (PPP) is used to encrypt the data between the connection. PPTP is one of the most widely used VPN protocol and has been in use since the early release of Windows. PPTP is also used on Mac and Linux apart from Windows.
4.  **SSL and TLS:**
    SSL (Secure Sockets Layer) and TLS (Transport Layer Security) generate a VPN connection where the web browser acts as the client and user access is prohibited to specific applications instead of entire network. Online shopping websites commonly uses SSL and TLS protocol. It is easy to switch to SSL by web browsers and with almost no action required from the user as web browsers come integrated with SSL and TLS. SSL connections have “https” in the initial of the URL instead of “http”.
5.  **OpenVPN:**
    OpenVPN 是一种开源 VPN，通常用于创建点对点和站点到站点的连接。它使用基于 SSL 和 TLS 协议的传统安全协议。
6.  **安全外壳(SSH):**
    安全外壳或 SSH 生成数据传输所通过的虚拟专用网隧道，并确保该隧道是加密的。SSH 连接由 SSH 客户端生成，数据通过加密隧道从本地端口传输到远程服务器。