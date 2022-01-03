# FTPS 和 SFTP 的区别

> 原文:[https://www . geeksforgeeks . org/ftps 和-sftp 之间的差异/](https://www.geeksforgeeks.org/difference-between-ftps-and-sftp/)

**1。文件传输协议安全(FTPS) :**
FTPS 被称为 FTP SSL，指的是[文件传输协议(T4)优于](https://www.geeksforgeeks.org/file-transfer-protocol-ftp-in-application-layer/)[安全套接字层(SSL)](https://www.geeksforgeeks.org/secure-socket-layer-ssl/) ，后者比 FTP 更安全。FTPS 也称为文件传输协议安全。它指的是具有安全性的基本文件传输协议，通过对数据进行加密来保护数据免受任何攻击，这样任何人都不能利用两端传输之间的任何信息。它实现了 AES 算法、三重 DES 算法和许多其他算法来加密数据。

**FTPS 的优势:**

*   它广为人知并被广泛使用
*   人类可以阅读和理解交流
*   它是加密的
*   易于实施
*   为基于 SSL/TLS 的服务器间文件传输提供服务
*   它在
    [中内置了支持。NET 框架](https://www.geeksforgeeks.org/introduction-to-net-framework/)

**FTPS 的缺点:**

*   它没有一致的目录列表格式
*   并非所有的 FTP 服务器都支持 SSL/TLS
*   它不能执行文件系统操作
*   它需要一个辅助数据通道
*   旧的 FTP 服务器不支持 SSL
*   它没有获取和更改文件或目录属性的标准方法

**2。安全文件传输协议(SFTP) :**
SFTP 被称为 SSH FTP，指的是通过[安全外壳(SSH)](https://www.geeksforgeeks.org/introduction-to-sshsecure-shell-keys/) 的文件传输协议(FTP)，该协议在传输过程中对命令和数据进行加密。SFTP 也称为安全文件传输协议。它是 SSH 的扩展。它加密文件和数据，然后通过安全的外壳数据流发送它们。该协议允许远程连接到其他系统并从命令行执行命令。像 FTPS 一样，它也实现了 AES 算法、三重 DES 算法和许多其他算法来加密数据。

**SFTP 的优势:**

*   它有很好的标准背景，定义了操作的大多数方面
*   在
    [防火墙](https://www.geeksforgeeks.org/introduction-of-firewall-in-computer-network/)后面使用很容易，因为它使用一个端口
*   连接始终受到保护/安全
*   目录列表一致/统一
*   它只有一个连接，不需要数据连接

**SFTP 的缺点:**

*   交互是二进制的，不能按原样记录以供人类阅读
*   很难管理和验证 SSH 密钥
*   没有服务器到服务器的副本
*   [没有内置 SSH/SFTP 支持。NET 框架](https://www.geeksforgeeks.org/introduction-to-net-framework/)
*   兼容性问题的概率

**FTPS 和 SFTP 的区别:**

<center>

| 没有。 | FTPS | science for the people 为人类服务的科学 |
| 01. | FTPS 用 SSL 引用文件传输协议。 | SFTP 提到了 SSH 文件传输协议。 |
| 02. | 它也被称为安全套接字层上的文件传输协议。 | 它也被称为安全外壳文件传输协议。 |
| 03. | 文件传输协议安全简称 FTPS。 | 安全文件传输协议简称 SFTP。 |
| 04. | 不支持基于密钥的身份验证。 | SSH 密钥可用于验证 SFTP 连接。 |
| 05. | 在这种情况下，支持证书。 | 在这种情况下，不支持证书。 |
| 06. | 它使用多端口数字。每次发出文件传输请求时，都需要为数据通道打开另一个端口号。 | SFTP 只需要一个单一的端口号就可以进行所有的 SFTP 通信，这使得它很容易保护和提供更大的保护。 |
| 07. | 它是最常用的，因为它无处不在的遗产。 | 但现在，它在最近的设备和软件中更为常见。 |
| 08. | 身份验证通过 x.509 证书执行。 | 身份验证是通过 SSH 密钥执行的。 |
| 09. | 它有单独的命令和文件数据连接。 | 它没有单独的命令和文件数据连接。 |

</center>