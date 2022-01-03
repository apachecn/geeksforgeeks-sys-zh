# 防火墙方法

> 原文:[https://www.geeksforgeeks.org/firewall-methodologies/](https://www.geeksforgeeks.org/firewall-methodologies/)

防火墙是一种网络安全系统，它根据明确定义的策略来监控和采取措施(允许或拒绝流量)。它可以由单个设备、一组设备或运行在单个设备(如服务器)上的软件来执行。

思科 ASA 在市场上占有最大的份额，同时还有其他防火墙供应商，如检查点、Juniper 等。

**防火墙方法–**
可以通过某些方法实施防火墙。具体如下:

1.  **Static packet filtering –** Packet filtering is a firewall technique used to control access on the basis of source IP address, destination IP address, source port number, and destination port number. It works on layers 3 and 4 of the OSI model. Also, an ACL doesn’t maintain the state of the session. A router with ACL applied to it is an example of static packet filtering. 

    **优势–**

    *   如果管理员对网络有很好的了解，就很容易实现。

    *   它几乎可以在所有路由器上配置。

    *   它对网络性能的影响很小。

    *   大量的 ACL 很难维护。

    *   ACL 使用 IP 地址进行过滤。如果有人欺骗相同的源 IP 地址，那么 ACL 将允许这样做。

2.  **Stateful packet filtering –** 
    In stateful packet filtering, the state of the sessions is maintained i.e when a session is initiated within a trusted network, it’s the source and destination IP address, source, and destination ports, and other layer information are recorded. By default, all the traffic from an untrusted network is denied. 

    仅当交换了 IP 地址(源和目标 IP 地址)和端口号(源和目标)时，才允许此会话的回复。

    **优势–**

    *   与静态包过滤相比，本质上是动态的。

    *   不易受 IP 欺骗的影响。

    *   可以在路由器上实现。

    *   可能无法阻止应用层攻击。

    *   一些应用程序在服务器端打开动态端口，如果防火墙对此进行分析，可能会导致应用程序失败。这就是应用程序检查开始使用的地方。

3.  **Proxy firewalls –** 
    These are also known as application-layer firewalls. A proxy firewall acts as an intermediary between the original client and the server. No direct connection takes place between the original client and the server. 

    客户端必须直接与服务器建立连接才能与之通信，现在必须与代理服务器建立连接。然后，代理服务器代表客户端与服务器建立连接。现在，客户端将数据发送给代理服务器，代理服务器将数据转发给服务器。代理服务器可以运行到第 7 层(应用层)。

    **优势–**

    *   难以攻击的服务器作为代理服务器是客户端和服务器之间的中间环节。

    *   可以提供详细的日志记录。

    *   可以在普通硬件上实现。

    *   处理器密集型

    *   内存和磁盘密集型

    *   网络安全单点故障

4.  **Application inspection –** 
    These can analyze the packet up to layer 7 (deep inspection) but can’t act as a proxy server. These can deeply analyze conversations between a client and server even when the server is assigning a dynamic port to the client therefore it doesn’t fail in these cases (which can occur in a stateful firewall). 

    **优势–**

    *   可以更深入地分析服务器和客户端之间的对话。

    *   如果标准协议出现异常，它可以拒绝数据包。

5.  **Transparent firewall –** 
    By default, the firewall operates at layer 3 but the benefit of using a transparent firewall is that it can operate at layer 2\. It has 2 interfaces that will act as a bridge so can be configured through a single management IP address. Also, users accessing the network will not even know that a firewall exists. 

    使用透明防火墙的主要优点是，在我们的网络中安装防火墙时，我们不需要重新寻址我们的网络。此外，当在第 2 层运行时，它仍然可以执行诸如构建有状态数据库、应用程序检查等功能。

6.  **Network Address Translation (NAT) –** 
    NAT is implemented on a router or firewall. NAT is used to translate a private IP address into a public IP address through which we can hide our source IP address. 
    And if we are using dynamic NAT or PAT, an attacker will not be able to know that what devices are dynamically assigned which IP address from the pool. This makes it difficult to make a connection from the outside world to our private network. 
7.  **下一代防火墙–**
    NGFWs 是以软件或设备实现的第三代安全防火墙。它将静态包过滤、应用程序检查等基本防火墙属性与集成入侵防御系统等高级安全功能相结合。带有火力服务的思科 ASA 就是下一代防火墙的一个例子。