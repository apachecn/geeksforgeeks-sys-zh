# SFTP 和 TFTP 的区别

> 原文:[https://www . geesforgeks . org/difference-sftp-and-TFTP/](https://www.geeksforgeeks.org/difference-between-sftp-and-tftp/)

**先决条件–**[传输层的职责](https://www.geeksforgeeks.org/transport-layer-responsibilities/)

**1。SSH 文件传输协议(SFTP) :**
这是一个建立在 SSH 之上的协议，用于以安全的方式高效地传输文件。使用该协议，它可以通过互联网连接轻松安全地迁移大量数据。它利用 SSH 功能，使信息传输具有更高的保护级别。

**2。普通文件传输协议(TFTP) :**
这是一个基于 UDP/IP 协议的协议构建，是一个简单的锁步文件传输协议，提供了一个从客户端到服务器传输文件的路径，反之亦然。通过使用该协议，我们可以将固件映像和网络文件传输到网络设备。

**SFTP 和 TFTP 的区别:**

<figure class="table">

| 

S.No

 | 

science for the people 为人类服务的科学

 | 

普通文件传送协议(Trivial File Transfer Protocol)

 |
| --- | --- | --- |
| 1. | 它是安全外壳文件传输协议的缩写。 | 它是普通文件传输协议的缩写。 |
| 2. | 它由塔图·伊洛宁于 1997 年创建。 | 它于 1981 年首次标准化。 |
| 3. | 它为在两个端点之间传输文件提供了一个安全通道。 | 它提供了从客户端到服务器以及从服务器到客户端的文件传输路径。 |
| 4. | 它在 22 号端口上运行。 | 它在端口号 69 上运行。 |
| 5. | 它为数据传输提供加密和身份验证 | 它既不提供加密也不提供身份验证。 |
| 6. | 支持转账恢复方式。 | 它支持锁步方法。 |
| 7. | 它使用 FTP 协议，但方式更安全。 | TFTP 使用 UDP 协议传输小的单个文件。 |
| 8. | 它支持 IPv6 HTTP 协议。 | 它不提供任何此类协议。 |

</figure>