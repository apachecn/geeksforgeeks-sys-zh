# 【LDAP 和 OAuth 2 的区别

> 原文:[https://www . geeksforgeeks . org/LDAP-and-oauth-2 之间的差异/](https://www.geeksforgeeks.org/difference-between-ldap-and-oauth-2/)

**1。[轻量级目录访问协议(LDAP)](https://www.geeksforgeeks.org/lightweight-directory-access-protocol-ldap/) :**
LDAP 代表轻量级目录访问协议。它是一种用于定位任何人的协议，以便在网络中定位个人、组织和其他设备，而不管是在公共互联网还是公司互联网上。它被用作目录即服务，并且是微软构建活动目录的基础。

**LDAP 的特性:**

*   它实现了一个具有灵活架构的开源协议。
*   直接通过 TCP/IP 和 SSL 运行。
*   LDAP 是一种自动协议。
*   提供跨行业的广泛支持。

**2。 [OAuth 2](https://www.geeksforgeeks.org/what-is-oauth-open-authorization/) :**
OAuth 顾名思义，它是一个授权框架，便于通过 HTTP 服务授予用户对其帐户的有限访问权限。当用户请求访问资源时，会调用一个应用编程接口，并在身份验证令牌通过后调用。

**OAuth 2 的特性:**

*   这是一种灵活的协议，允许在不使用用户凭据的情况下进行访问。
*   更容易实现。
*   它提供服务器端的代码授权。
*   它提供了强身份验证。

**LDAP 和 OAuth 的区别:**

<center>

| 没有。 | 轻量级目录访问协议 | OAuth 2 |
| --- | --- | --- |
| 1. | 它简称为轻量级目录访问协议。 | 它被称为 OAuth 2。 |
| 2. | 访问时，LDAP 用于授权记录的详细信息。 | 它用于服务器端的身份验证用户凭据。 |
| 3. | 它不是开源的，但它拥有开源的实现，如开放 LDAP。 | 这是一个开放的访问授权标准。 |
| 4. | 它支持使用 RADIUS 协议的双因素身份验证。 | 它提供双向身份验证，并可以告诉您用户的属性数量。 |
| 5. | LDAP 在两个选项中附加了身份验证 SASL 或匿名身份验证。 | OAuth 通过称为网络令牌的访问令牌提供身份验证。 |
| 6. | 它在多层应用程序中呈现身份验证。 | 它在多层应用程序中提供身份验证。 |

</center>