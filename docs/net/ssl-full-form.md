# SSL 完全形式

> 原文:[https://www.geeksforgeeks.org/ssl-full-form/](https://www.geeksforgeeks.org/ssl-full-form/)

[SSL](https://www.geeksforgeeks.org/secure-socket-layer-ssl/) 代表**安全套接字层**。

SSL 是网景公司在网络服务器和网络浏览器之间创建加密连接的协议。术语“套接字”也指在客户机和服务器程序之间交换信息的套接字方法:在网络中或在同一设备上的进程之间。SSL 是一种行业标准，通过编码在互联网上安全可靠地传输私人信息，如信用卡号、社会安全号和登录凭据。许多网站利用它来确保客户的在线交易。

SSL 最早是安全在线交易的常用框架，最终被用于其他应用的网络传输层的安全认证和加密。SSL 混合使用公钥和私钥以及会话密钥加密来保护网络和客户端系统之间的连接，通过互联网或其他类似的 TCP/IP 网络连接在一起。用公钥编码的任何东西只能用私钥解码，反之亦然。TLS 协议是从 SSL 发展而来的，并且已经正式取代了它。

**历史:**
安全套接字层的真实实现是在网景通信公司的帮助下于 20 世纪 90 年代初开发的，以保护 [HTTP](https://www.geeksforgeeks.org/http-non-persistent-persistent-connection/) ，该协议通过互联网以简单文本的形式发送其记录。第一个发布的版本是 2.0，尽管有一些框架缺陷和协议漏洞，它还是获得了显著的地位。互联网工程任务组(IETF)在 2015 年否决了在网络上使用 SSL，此后被[传输层安全(TLS)协议](https://www.geeksforgeeks.org/transport-layer-security-tls/)取代。但是，TLS 和 SSL 不具备互操作性，TLS 与 SSL 3.0 向后兼容。

**特征:**

1.  SSL 通过以下方式保护网络连接:
    *   **机密性–**
        使用对称密钥加密技术对信息进行加密。
    *   **认证–**
        通信实体通过使用数字证书来识别自己。站点服务器的身份验证是强制的，而数据库的身份验证是可选的。
    *   **诚信–**
        保持对通信可信度的检查。
2.  无损压缩方法用于压缩碎片数据。
3.  主要为在线电子商务设计。
4.  几乎每个网络浏览器都支持。
5.  对于所有的 TCP 应用程序，SSL 都是可访问的。

**架构:**
SSL 协议在架构上被构建为一套通过 TCP / IP 的协议。SSL 协议设计通常被称为 SSL 协议栈。

SSL 协议有两个子层–

1.  **第一子层–**
    第一子层包含 SSL 协议的一部分，称为协议到 SSL 记录。该元素允许完整性和保密性设施。SSL 记录协议还处理数据检查，并将其封装在适当的报头中，以便在 TCP 协议下安全传输。
2.  **Second sub-layer –**
    Protocols for second and top layers of SSL protocol stack incorporated SSL Handshake Protocol, SSL Shift Cipher Protocol, and SSL Warning Protocol. The second layer of SSL Protocol Stack is set over SSL Record protocol and is responsible for maintaining a safe and secure connection to an application protocol such as HTTP. Three top layer stack protocols deliver customer-to-server session control, cryptographic parameter control, and secure SSL message transfer.

    **优势:**
    以下是 SSL 的优势:

    *   **加密–**
        使用 SSL 在网站上进行的数据传输经过编码，以确保敏感数据的安全。当数据被加密时，入侵者发现很难截获内部信息。
    *   **服务器真实性–**
        SSL 提供身份验证，这意味着互联网上的数据传输保证通过适当的服务器。入侵者经常冒充你的网站，集中你客户的信息。使用合适的公钥基础设施(PKI)并从可信的 SSL 供应商处接收 SSL 证书可以避免这种情况。
    *   **信任–**
        客户信任使用 SSL 的网站。这使得流量在一个站点获得。此外，如果一个网站包括在线支付并允许会员资格，信息安全措施必须到位，以保护您客户的数据。
    *   **安全性–**
        当客户收到网络钓鱼电子邮件时，它包含指向原始网站的精确副本的链接，并且当客户在网站上使用其信息时，未经授权的用户可以访问它，但是拥有 SSL 证书会取消他们的访问，从而保护客户免受未经授权的网络钓鱼电子邮件的攻击。

    **劣势:**
    以下是 SSL 的劣势:

    *   **性能–**
        当数据通过需要 SSL 的互联网门户传输时，由于加密和解密，速度会变慢。
    *   **成本因素–**
        SSL 证书相当昂贵，因为服务提供商必须支付基础设施维护费用。虽然有些托管组织确实免费提供 SSL 证书。
    *   **需要额外的凭证–**
        SSL 证书会吞噬一些额外的资源，因为数据必须编码。当使用 SSL 证书时，在大量互联网流量的情况下，网站性能的明显变化可能是一个缺点。