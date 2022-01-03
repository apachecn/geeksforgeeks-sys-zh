# 【LDAP 和 Kerberos 的区别

> 原文:[https://www . geeksforgeeks . org/LDAP 和 kerberos 之间的区别/](https://www.geeksforgeeks.org/difference-between-ldap-and-kerberos/)

**1。[轻量级目录访问协议(LDAP)](https://www.geeksforgeeks.org/ldap-full-form/) :**
LDAP 代表轻量级目录访问协议。它是一种协议，用于定位任何人，以定位网络中的个人、组织和其他设备，而不管是在公共互联网还是公司互联网上。它用于目录即服务，是微软构建活动目录的基础。

**LDAP 的特性:**

*   它提供了一个具有灵活架构的开源协议。
*   直接通过 TCP/IP 和 SSL 运行。
*   LDAP 是一种自动协议。
*   提供跨行业的广泛支持。

**2。[Kerberos](https://www.geeksforgeeks.org/kerberos/):**
Kerberos 是一种用于网络身份验证的协议。这用于使用加密密钥对网络中的客户端/服务器进行身份验证。它设计用于在与应用程序通信时提供强身份验证。Kerberos 协议的实现由麻省理工学院免费提供，并在许多商业产品中使用。

**Kerberos 的特性:**

*   它防止各种入侵攻击。
*   它通过互联网为网络应用程序提供身份验证。
*   在根提供单一信任并消除全网状场景。
*   允许与其他访问域的互操作性。

**LDAP 和 Kerberos 的区别:**

<center>

| 没有。 | 轻量级目录访问协议 | 麻省理工学院开发的安全认证系统 |
| --- | --- | --- |
| 1. | 它是轻量级目录访问协议的简称。 | 它被命名为 Kerberos。 |
| 2. | 访问时，LDAP 用于授权帐户详细信息。 | Kerberos 用于安全地管理凭据。 |
| 3. | 它不是开源的，但是它有开源的实现，比如开放 LDAP。 | 它是提供免费服务的开源软件。 |
| 4. | 它支持使用 RADIUS 协议的双因素身份验证。 | 它支持双因素身份验证。 |
| 5. | LDAP 在两个选项中添加了身份验证 SASL 或匿名身份验证。 | Kerberos 增加了高安全性，并提供了相互身份验证。 |
| 6. | 它在多层应用程序中提供身份验证。 | 它在多层应用程序中提供身份验证。 |

</center>