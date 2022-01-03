# 【RIPv1 和 RIPv2 的区别

> 原文:[https://www . geesforgeks . org/differences-rip v1-和-ripv2/](https://www.geeksforgeeks.org/differences-between-ripv1-and-ripv2/)

**1。RIPv1 :**
RIPv1 使用有类路由。定期路由更新不携带子网信息，缺乏对[可变长度子网掩码(VLSM)](https://www.geeksforgeeks.org/introduction-of-variable-length-subnet-mask-vlsm/) 的支持。这种限制使得同一网络类别内不可能有不同大小的子网。换句话说，网络类中的所有子网必须具有相同的大小。也不支持路由器认证，使得 RIP 容易受到各种攻击。

**2。RIPv2 :**
RIPv2 是 RFC 1723 中定义的无类距离矢量路由协议。作为无类路由协议，意味着它在路由更新中包含子网掩码和网络地址。

由于 RIPv1 的不足，RIP 版本 2 (RIPv2)于 1993 年开发，具备支持子网信息的能力，支持[无类域间路由(CIDR)](https://www.geeksforgeeks.org/classless-inter-domain-routing-cidr/) 。

**rip v1 和 RIPv2 的区别:**

<center>

| SR.NO | RIPv1 | RIPv2 |
| --- | --- | --- |
| 1. | RIPv1 是一种距离矢量路由协议。 | RIPv2 也是距离矢量路由协议。 |
| 2. | 它只能支持类全网。 | 它可以支持全类和无类网络。 |
| 3. | 它不支持身份验证。 | 它支持身份验证。 |
| 4. | 它的跳数限制是 15。 | 它的跳数限制是 15。 |
| 5. | 它不支持 VLSM 和不连续网络。 | 它支持 VLSM 和不连续网络。 |
| 6. | 它不太安全。 | 它更安全。 |
| 7. | RIPv1 使用广播流量进行更新。 | RIPv2 使用多播流量进行更新。 |
| 8. | RIPV1 不提供触发器更新。 | RIPv2 提供触发更新。 |
| 9. | RIPV1 没有向路由表发送子网掩码。 | RIPv2 向路由表发送子网掩码。 |
| 10. | RIPv1 不支持手动路由总结。 | RIPv2 支持手动路由总结。 |

</center>