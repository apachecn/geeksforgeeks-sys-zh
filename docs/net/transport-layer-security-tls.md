# 传输层安全性(TLS)

> 原文:[https://www.geeksforgeeks.org/transport-layer-security-tls/](https://www.geeksforgeeks.org/transport-layer-security-tls/)

传输层安全性(TLS)旨在提供传输层安全性。TLS 源自一个名为[安全服务层(SSL)](https://www.geeksforgeeks.org/secure-socket-layer-ssl/) 的安全协议。TLS 确保没有第三方可以窃听或篡改任何消息。

TLS 有几个好处:

*   **加密:**
    TLS/SSL 可以帮助使用加密保护传输的数据。
*   **互操作性:**
    TLS/SSL 适用于大多数网络浏览器，包括微软的 Internet Explorer，也适用于大多数操作系统和网络服务器。
*   **算法灵活性:**
    TLS/SSL 为安全会话期间使用的身份验证机制、加密算法和哈希算法提供操作。
*   **易于部署:**
    许多应用程序临时在 windows server 2003 操作系统上运行 TLS/SSL。
*   **易用性:**
    因为我们在应用层下实现 TLS/SSL，所以它的大部分操作对客户端来说是完全不可见的。

**TLS 的工作:**
客户端连接服务器(使用 [TCP](https://www.geeksforgeeks.org/tcp-ip-model/) ，客户端会有事。客户端发送规格号:

1.  SSL/TLS 的版本。
2.  它想使用哪种密码套件、压缩方法。

服务器检查它们都支持的最高 SSL/TLS 版本，从其中一个客户端选项中选择一个密码套件(如果它支持一个)，并可选地选择一种压缩方法。完成基本设置后，服务器提供其证书。该证书必须由客户端本身或客户端信任的一方信任。验证证书并确定这个服务器真的是他声称的那个人(而不是中间的人)之后，交换一个密钥。这可以是一个公共密钥，“PreMasterSecret”，也可以是一个密码套件。

服务器和客户端现在都可以计算对称加密的密钥。握手完成，两台主机可以安全通信。结束连接。TCP 连接双方都将知道连接被不正确地终止。这种连接不会因为中断而受损。