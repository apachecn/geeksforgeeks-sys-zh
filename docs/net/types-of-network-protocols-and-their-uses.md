# 网络协议的类型及其用途

> 原文:[https://www . geesforgeks . org/网络协议类型及其用途/](https://www.geeksforgeeks.org/types-of-network-protocols-and-their-uses/)

网络协议是一组公认的规则，用于管理网络中不同设备之间的数据通信。它决定了沟通的内容、沟通的方式以及沟通的时间。它允许连接的设备相互通信，而不考虑内部和结构差异。

### **协议类型**

协议可以大致分为三大类-

1.  [communication]
2.  [management]
3.  safe

### **1。通信**

通信协议对于网络的运行非常重要。它们非常重要，没有它们就不可能有计算机网络。这些协议正式规定了数据传输的规则和格式。这些协议处理语法、语义、错误检测、同步和身份验证。

**通信协议示例:**

1.  **HTTP:** 它是一种第 7 层协议，旨在两个或多个系统之间传输超文本。HTTP 在客户机-服务器模式下工作，网络上的大多数数据共享都是通过使用 HTTP 来完成的。
2.  **TCP:** 它通过使用顺序确认来规划可靠的流传递。它是一种面向连接的协议，即它在发送任何数据之前在应用程序之间建立连接。它用于通过网络进行通信。它有许多应用，如电子邮件、文件传输协议、流媒体等。
3.  **UDP:** 这是一种无连接协议，用于布局基本但不可靠的消息服务。它没有增加流量控制、可靠性或错误恢复功能。在不要求可靠性的情况下，UPD 可以发挥作用。当我们想要更快的传输时，它被用于多播和广播连接等。
4.  **BGP:** 它是一种路由协议，控制数据包如何通过独立系统中的路由器一个或多个由单个组织运行的网络，并连接到不同的网络。它将一个局域网的端点与其他局域网连接起来，还将不同局域网中的端点相互连接起来。
5.  **ARP:** ARP 是一种协议，有助于将逻辑地址映射到本地网络中确认的物理地址。为了映射和维护这些逻辑和物理地址之间的相关性，使用了一个称为 ARP 缓存的表。
6.  **IP:** 它是一种协议，数据通过该协议从一台主机通过互联网发送到另一台主机。它用于寻址和路由数据包，以便它们能够到达目的地。
7.  **DHCP:** 它是一种网络管理协议，用于在 IP 网络上自动配置设备的方法。DHCP 服务器自动为网络上的设备分配一个 IP 地址和各种其他配置更改，以便它们可以与其他 IP 网络通信。它还允许设备使用各种服务，如 NTP、DNS 或任何其他基于 TCP 或 UDP 的协议。

### **2。管理**

这些协议有助于描述用于监控、维护和管理计算机网络的程序和策略。这些协议还有助于通过网络传达这些要求，以确保稳定的通信。网络管理协议也可用于排除主机和客户端之间的连接故障。

**管理协议示例:**

1.  **ICMP:** It is the Layer 3 protocol used by network devices to forward operation information and error messages. It is used to report congestion, network errors, diagnostic purposes and timeouts.
2.  **SNMP:** It is a layer 7 protocol for managing nodes on IP networks. SNMP protocol has three main components, namely SNMP agent, SNMP manager and managed devices. SNMP agent has local knowledge of management details, and it translates these details into a form compatible with SNMP manager. The manager presents the data obtained from the SNMP agent, which helps to monitor network failures, network performance and troubleshooting.
3.  **gopher:** It is a file retrieval protocol that provides some descriptions for downloadable files to facilitate file management, retrieval and search. All files are arranged hierarchically on the remote computer. This is an ancient protocol, and it is not often used now.
4.  **FTP:** FTP is a client/server protocol used to move files to or from the host. It allows users to download files, programs, web pages and other things available on other services.
5.  **POP3:** It is a protocol for local mail clients to obtain e-mail from remote e-mail servers through TCP/IP connection. E-mail servers hosted by Internet service providers also use POP3 protocol to save and receive e-mails for their users. Eventually, these users will use email client software to check their mailboxes on remote servers and download their emails. After the email client downloads the email, it usually deletes it from the server.
6.  **Telnet:** It is a protocol that allows users to connect to remote computer programs and use it, that is, it is designed for remote connection. Telnet creates a connection between the host and the remote endpoint to enable the remote session.

### **3。安全**

这些协议保护数据在网络上的传输。这些协议还决定了网络如何保护数据免受任何未经授权的提取或查看数据的尝试。这些协议确保没有未经授权的设备、用户、服务可以访问网络数据。这些协议主要依靠加密来保护数据。

**安全协议示例:**

1.  **SSL:** A network security protocol mainly used to protect sensitive data and ensure the security of Internet connection. SSL allows server-to-server and client-to-server communication. All data transmitted through SSL is encrypted, thus preventing any unauthorized person from accessing it.
2.  **https:** is the secure version of HTTP; This protocol ensures secure communication between two computers, one of which sends requests through a browser and the other one gets data from a web server.
3.  **TSL:** It is a security protocol designed for data security and privacy on the Internet. Its function is to encrypt and check the integrity of data, that is, whether the data has been tampered with or not and to verify the identity. It is usually used for encrypted communication between the server and the network application, just like the web browser that loads the website, and it can also be used for encryption of messages, e-mails and VoIP.