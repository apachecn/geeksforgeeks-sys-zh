# 【Kerberos 和 SSL 的区别

> 原文:[https://www . geeksforgeeks . org/Kerberos 和 ssl 的区别/](https://www.geeksforgeeks.org/difference-between-kerberos-and-ssl/)

**1。[Kerberos](https://www.geeksforgeeks.org/kerberos/):**
Kerberos 是一种计算机网络认证系统，用于用户登录系统时的信息认证。Kerberos 基于[对称密钥加密](https://www.geeksforgeeks.org/difference-between-symmetric-and-asymmetric-key-encryption/)，并依赖于可靠的第三方，在身份验证阶段使用私钥加密。为增强身份验证的安全性，开发了不同版本的 Kerberos。Kerberos 通常在微软产品中实现，如 Windows 2000、Windows XP 和更高版本的 Windows。

**2。[安全套接字层(SSL)](https://www.geeksforgeeks.org/secure-socket-layer-ssl/) :**
SSL 是一种加密协议，在非安全网络中提供安全传输。SSL 需要证书，并使用[公钥加密](https://www.geeksforgeeks.org/public-key-encryption/)。SSL 不直接使用任何端口，它工作在 TCP 协议上，通过 [TCP](https://www.geeksforgeeks.org/tcp-and-udp-in-transport-layer/) 使用任何端口。SSL 在网络环境的不同应用中实现，如网页浏览、消息传递、电子邮件和其他协议，如 [FTP](https://www.geeksforgeeks.org/file-transfer-protocol-ftp-in-application-layer/) 。

**Kerberos 和 SSL 的区别**

<center>

| 没有。 | 麻省理工学院开发的安全认证系统 | 加密套接字协议层 |
| --- | --- | --- |
| 1. | Kerberos 是一个开源软件，提供免费服务。 | SSL 不提供免费服务，因为它是专利。 |
| 2. | Kerberos 通常在微软产品中实现，如 Windows 2000、Windows XP 和更高版本的 Windows。 | SSL 在网页浏览、消息传递和其他协议中实现，如 FTP。 |
| 3. | Kerberos 依赖于可靠的第三方。 | SSL 是异步的，因为它依赖于证书。 |
| 4. | Kerberos 使用私钥加密。 | 而 SSL 使用公钥加密。 |
| 5. | Kerberos 最适合万维网。 | SSL 对于网络环境来说是合适且有效的。 |
| 6. | 在 kerberos 中，通过禁用身份验证服务器上的任何用户来实现密钥取消。 | 在 SSL 中，撤销服务器控制记录用于密钥取消的坏证书。 |

</center>