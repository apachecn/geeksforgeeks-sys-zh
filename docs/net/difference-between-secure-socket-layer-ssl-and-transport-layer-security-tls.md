# 安全套接字层(SSL)和传输层安全性(TLS)的区别

> 原文:[https://www . geeksforgeeks . org/secure-socket-layer-SSL-and-transport-layer-security-TLS/](https://www.geeksforgeeks.org/difference-between-secure-socket-layer-ssl-and-transport-layer-security-tls/)

SSL 代表[安全套接字层](https://practice.geeksforgeeks.org/problems/what-is-ssl)，而 TLS 代表[传输层](https://www.geeksforgeeks.org/computer-network-transport-layer-responsibilities/)安全。安全套接字层和传输层安全性都是用于提供网络浏览器和网络服务器之间安全性的协议。

安全套接字层和传输层安全性的主要区别在于。在 SSL(安全套接字层)中，消息摘要用于创建主秘密，并提供基本的安全服务，即**认证**和**保密**。而在传输层安全中，伪随机函数用于创建主秘密。

SSL 和 TLS 之间存在一些差异，如下所示:

| S.NO | 加密套接字协议层 | 坦克激光瞄准镜（Tank Laser-Sight 的缩写） |
| 1. | SSL 代表安全套接字层。 | TLS 代表传输层安全性。 |
| 2. | SSL(安全套接字层)支持 **Fortezza** 算法。 | TLS(传输层安全)不支持 **Fortezza** 算法。 |
| 3. | SSL(安全套接字层)是 3.0 版本。 | 传输层安全性是 1.0 版本。 |
| 4. | 在 SSL(安全套接字层)中，消息摘要用于创建主密钥。 | 在传输层安全性中，使用伪随机函数来创建主秘密。 |
| 5. | 在 SSL(安全套接字层)中，使用消息认证码协议。 | 在传输层安全中，使用散列消息认证码协议。 |
| 6. | SSL(安全套接字层)比 TLS(传输层安全性)更复杂。 | 传输层安全性很简单。 |
| 7. | 与传输层安全性相比，SSL(安全套接字层)的安全性较低。 | 传输层安全性提供了很高的安全性。 |