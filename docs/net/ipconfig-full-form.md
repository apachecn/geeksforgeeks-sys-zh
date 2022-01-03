# IPCONFIG 完整表格

> 原文:[https://www.geeksforgeeks.org/ipconfig-full-form/](https://www.geeksforgeeks.org/ipconfig-full-form/)

**IPCONFIG** 代表**互联网协议配置**。这是一个命令行应用程序，显示所有当前的 TCP/IP(传输控制协议/互联网协议)网络配置，刷新 DHCP(动态主机配置协议)和 DNS(域名服务器)。它还显示所有适配器的 IP 地址、子网掩码和默认网关。它适用于微软视窗、ReactOS 和苹果电脑。ReactOS 版本由 Ged Murphy 开发，并根据通用公共许可证获得许可。

![IPCONFIG-Full-Form](img/c8bbc27946a5ff48a92d677e01983dc3.png)

在 Windows 和 ReactOS 中，它首先强制刷新主机的 DHCP IP 地址，然后请求不同的 IP 地址。在 macOS 中，IPCONFIG 在命令行界面用于控制引导协议和 DHCP 客户端。

#### 特征

*   IPCONFIG 为 TCP/IP 的 IPv4 IP 层提供设置。
*   连接请求队列的最大长度是使用 IPCONFIG 指定的。
*   TCP/IP 的 IP 层的所有更新都是使用 IPCONFIG 完成的。
*   IPCONFIG 用于对 IPv4 数据包进行校验和处理。

#### 优势

*   它显示系统的完整配置。
*   它可以用来刷新 DHCP 租约，重新注册域名和请求新的 IP 地址。
*   它显示 DNS 解析器缓存信息，也可以刷新它们。
*   它可以显示所有允许的类 id。

#### 不足之处

*   它的效率较低，因为它使用 netlink 套接字在内核和用户之间传输信息。
*   实现是困难的，因为它是在控制台上实现的。
*   需要记忆命令，这是一项艰巨的任务。
*   初学者可能会发现很难执行，因为命令行依赖。