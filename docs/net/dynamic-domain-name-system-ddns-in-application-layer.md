# 应用层动态域名系统(DDNS)

> 原文:[https://www . geesforgeks . org/dynamic-domain-name-system-ddns-in-application-layer/](https://www.geeksforgeeks.org/dynamic-domain-name-system-ddns-in-application-layer/)

当 [DNS(域名系统)](https://www.geeksforgeeks.org/domain-name-server-dns-in-application-layer/)被设计出来的时候，没有人想到会有这么多的地址变化，比如增加一个新的主机，删除一个主机，或者改变一个 [IP 地址](https://www.geeksforgeeks.org/introduction-of-classful-ip-addressing/)。当有更改时，必须对需要大量手动更新的 DNS 主文件进行更改，并且必须动态更新。

**动态域名系统(DDNS) :**
这是一种在域名服务器(DNS)中自动更新名称服务器的方法，通常是实时更新，主动 DDNS 配置其配置的主机名、地址或其他信息。在 DDNS，当名称和地址之间的绑定被确定时，信息通常通过 [DHCP(动态主机配置协议)](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/)被发送到主 DNS 服务器。

主服务器更新区域。辅助服务器被主动或被动地通知。非活动通知，主服务器向辅助服务器发送消息，而在非活动通知中，辅助服务器定期检查任何更改。在这两种情况下，在收到更改通知后，辅助服务器都会请求整个区域的信息(区域传输)。

DDNS 可以使用身份验证机制来提供安全性，并防止未经授权更改 DNS 记录。

**优势:**

1.  当网络配置改变时，它节省了手动更新静态地址所需的时间。
2.  它节省了空间，因为一次可以根据需要使用多个地址，而不是为该 IP 地址的所有可能用户使用一个地址。
3.  从用户的角度来看，这是非常舒适的，因为任何 IP 地址的更改都不会影响他们的任何活动。
4.  它不影响可访问性，因为更改的 IP 地址是根据 URL 自动配置的。

**缺点:**

1.  由于缺少静态 IP 地址和域名映射，它的可靠性较低。
2.  动态域名服务本身并不能保证你试图连接的设备就是你自己的。

**用途:**

1.  它用于路由器等互联网接入设备。
2.  它用于安全设备制造商，甚至需要基于知识产权的安全设备，如数字视频录像机。