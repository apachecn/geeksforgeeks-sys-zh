# TACACS+和 RADIUS 的区别

> 原文:[https://www . geeksforgeeks . org/tac ACS 和 radius 之间的差异/](https://www.geeksforgeeks.org/difference-between-tacacs-and-radius/)

前提–[TACACS+](https://www.geeksforgeeks.org/computer-network-tacacs/)、 [RADIUS](https://www.geeksforgeeks.org/computer-network-radius/)
为了提供一个集中的认证、授权和计费管理系统(AAA 框架)，使用了访问控制服务器(ACS)。对于客户端和 ACS 服务器之间的通信，使用了两种协议，即 TACACS+和 RADIUS。

**TACACS+**
终端访问控制器访问控制系统(TACACS+)是思科专有协议，用于思科客户端和思科 ACS 服务器之间的通信。它使用 TCP 端口号 49，这使得它可靠。

**RADIUS–**
远程访问拨入用户服务(RADIUS)是一种开放的标准协议，用于任何供应商 AAA 客户端和 ACS 服务器之间的通信。如果其中一个客户端或服务器来自任何其他供应商(除了思科)，那么我们必须使用 RADIUS。它使用端口号 1812 进行身份验证和授权，使用端口号 1813 进行记帐。

**相似性–**
该过程由网络接入设备(NAD–TACACS+或 RADIUS 的客户端)启动。NAD 联系 TACACS+或 RADIUS 服务器，并将身份验证请求(用户名和密码)传输到服务器。首先，NAD 获得用户名提示并将用户名传输到服务器，然后 NAD 再次联系服务器以获得密码提示，然后将密码发送到服务器。

如果凭据有效，服务器将回复访问接受消息，否则将向客户端发送访问拒绝消息。两种协议中的进一步授权和计费是不同的，因为在 RADIUS 中身份验证和授权是结合在一起的。

**差异–**

<figure class="table">

| **TACACS+** | **半径** |
| 思科专有协议 | 开放标准协议 |
| 它使用 TCP 作为传输协议 | 它使用 UDP 作为传输协议 |
| 它使用 TCP 端口号 49。 | 它使用 UDP 端口号 1812 进行身份验证和授权，使用 1813 进行记帐。 |
| 在 TACACS+中，身份验证、授权和记帐是分开的。 | 身份验证和授权在 RADIUS 中是结合在一起的。 |
| 所有的 AAA 包都是加密的。 | 只有密码是加密的，而其他信息如用户名、会计信息等没有加密。 |
| 优选用于 ACS。 | 使用 ISE 时使用 |
| 它提供了更精细的控制，即可以指定特定的授权命令。 | 不支持命令的外部授权。 |
| TACACS+提供多协议支持 | 不支持多协议。 |
| 用于设备管理。 | 用于网络访问 |

**优势(TACACS+超半径)–**

1.  由于 TACACS+使用 TCP，因此比 RADIUS 更可靠。

2.  TACACS+提供了对命令授权的更多控制，而在 RADIUS 中，不支持命令的外部授权。

3.  所有 AAA 数据包都在 TACACS+中加密，而只有密码在 RADIUS 中加密，即更安全。

**优势(半径超过 TACACS+)–**T2】

1.  由于它是一个开放标准，因此 RADIUS 可以与其他供应商的设备一起使用，而由于 TACACS+是思科专有的，它只能与思科设备一起使用。

2.  它拥有比 TACACS+更广泛的会计支持。

</figure>