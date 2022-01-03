# SSH 和 SSL 的区别

> 原文:[https://www . geesforgeks . org/ssh 和 ssl 的区别/](https://www.geeksforgeeks.org/difference-between-ssh-and-ssl/)

**1。[安全外壳(SSH)](https://www.geeksforgeeks.org/difference-ssh-telnet/) :**
它是一种加密网络协议，用于通过互联网访问网络设备和服务器。SSH 协议是由 SSH 通信安全有限公司开发的。SSH 允许我们通过网络安全地登录到另一台计算机，在远程机器上执行命令，并通过网络将文件从一台机器传输到另一台机器。

**2。[安全套接字层(SSL)](https://www.geeksforgeeks.org/ssl-full-form/) :**
这是一种在非安全网络中提供安全传输的网络协议。SSL 需要证书，使用[公钥加密](https://www.geeksforgeeks.org/introduction-to-sshsecure-shell-keys/)。SSL 在网络环境的各种操作中实现，如网页浏览、消息传递、电子邮件和其他协议，如 [FTP](https://www.geeksforgeeks.org/file-transfer-protocol-ftp-in-application-layer/) 。

**SSH 和 SSL 的区别:**

<center>

| S.No | 嘘 | 加密套接字协议层 |
| --- | --- | --- |
| 1. | 它是加密隧道协议，并有一个用户名/密码认证系统。 | 它没有像 SSH 那样的用户名/密码认证系统。 |
| 2. | 它在 22 号端口工作。 | 它在端口号 443 上工作。 |
| 3. | 这完全取决于网络隧道。 | 它是异步的，因为它依赖于证书。 |
| 4. | 它适用于服务器和客户端身份验证过程的三阶段过程。 | 而 SSL 通常在 X.509 数字证书上工作，用于服务器和客户端身份验证。 |
| 5. | 它通过互联网加密两台计算机之间的通信。 | 它加密浏览器和服务器之间的通信。 |
| 6. | 对于在互联网上安全地执行命令来说，这是适当且有效的。 | 它最适合安全地传输关键数据，如信用卡和银行业务。 |
| 7. | 它通过使用对称密钥算法来提供数据机密性。 | 它采用对称和非对称加密算法的组合来提供数据隐私。 |

</center>