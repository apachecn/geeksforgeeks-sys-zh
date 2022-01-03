# 自动超控和自动允许的区别在

> 原文:[https://www . geesforgeks . org/as-override-and-allow is-in/](https://www.geeksforgeeks.org/difference-between-as-override-and-allowas-in/)之间的差异

**1。AS Override :**
其功能允许提供商边缘(PE)路由器在 VPN 路由和转发接入链路上运行的外部 BGP 会话上更改客户边缘(CE)设备使用的私有自治系统。专用自动系统号改为豌豆号。

**2。Allowas In :**
该功能允许接收和处理路由，即使路由器在 AS-Path 中检测到自己的 ASN。如果[路由器](https://www.geeksforgeeks.org/introduction-of-a-router/)认为其在 AS-Path 中的 ASN 是一种环路防止机制，它会丢弃 BGP 网络前缀。

**自动超控和自动超控的区别:**

<center>

| 参数 | 作为替代 | 所有人都在 |
| 概观 | 它被 PE 用来修改 AS 路径。这样做是为了在默认行为下不丢弃前缀，从而不允许它自己的 AS 成员出现在前缀的 AS 路径中。 | 它被用作自治系统路径环路防止机制，其中 BGP 的默认行为是不允许其自身的自治系统号出现在前缀的自治系统路径中。 |
| 输出 | 在对本地自动化系统的 BGP 更新中，自动化系统覆盖功能取代了自动化系统。 | 它在包含本地 AS 的 BGP 中更新，这是允许的。 |
| 配置于 | 其功能在服务提供商端配置。 | 其功能在客户端配置。 |
| 配置 | 它配置在:
路由器 bgp
邻居 as-override 下 | 在
路由器 bgp
邻居允许接入下配置 |
| 作为路径 | AS 路径中有修改。 | 自动化路径中没有修改。 |
| 范围。 | 在服务提供商端执行配置。 | 在服务提供商端执行配置。 |
| 最佳用途。 | 当客户要求在 CE 端保持最低配置时，最好使用这种方法。 | 这种方法最适合在 BGP 中引入一个异常作为循环防止机制。 |

</center>