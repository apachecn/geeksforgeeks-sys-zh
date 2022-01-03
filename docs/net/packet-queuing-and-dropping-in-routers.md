# 路由器中的数据包排队和丢弃

> 原文:[https://www . geesforgeks . org/数据包排队和丢弃路由器/](https://www.geeksforgeeks.org/packet-queuing-and-dropping-in-routers/)

路由器是在网络上引导数据流的重要网络设备。路由器有一个或多个**输入**和**输出接口**，分别接收和发送数据包。由于路由器的内存有限，路由器可能会用尽空间来容纳新到达的数据包。如果数据包的到达速率大于数据包从路由器内存中退出的速率，就会出现这种情况。在这种情况下，新数据包被忽略*或*旧数据包被丢弃。作为资源分配机制的一部分，路由器必须实现一些队列规则，这些规则控制数据包在需要时如何缓冲或丢弃。

[![Resolution Days 2022 GeeksforGeeks](img/11f7b6527218dede633083214c76fe24.png)](https://practice.geeksforgeeks.org/resolution-days-2022 "Resolution Days 2022 GeeksforGeeks")

![Routers queuing](img/36c2b48b06c71b7e24b694e8773f54c0.png)

**图 1:** 路由器的入站和出站流量图