# 【COAP 和 MQTT 协议的区别

> 原文:[https://www . geeksforgeeks . org/coap-和-mqtt-协议之间的差异/](https://www.geeksforgeeks.org/difference-between-coap-and-mqtt-protocols/)

**1。受限应用协议(COAP) :**
受限应用协议是一种基于客户端服务器的协议。通过该协议，COAP 分组可以在不同的客户端节点之间共享，这是由 COAP 服务器命令的。服务器负责根据其逻辑共享信息，但不必确认。这用于支持状态转移模型的应用程序。

**2。消息查询遥测传输(MQTT) :**
消息查询遥测传输协议是一种基于通信的协议，用于物联网设备。该协议基于发布-订阅方法，其中客户端仅通过订阅主题的代理接收信息。Broker 是一个中介，它在传递消息之前将消息分类到标签中。

【COAP 和 MQTT 协议的区别:

<figure class="table">

| 的基础 | COAP | MQTT |
| --- | --- | --- |
| 缩写 | 受限应用协议 | 消息查询遥测传输 |
| 通信类型 | 它使用请求-响应模型。 | 它使用发布-订阅模型 |
| 消息模式 | 这同时使用了异步和同步。 | 这仅使用异步 |
| 传输层协议 | 这主要使用[用户数据报协议(UDP)](https://www.geeksforgeeks.org/user-datagram-protocol-udp/) | 这主要使用[传输控制协议(TCP)](https://www.geeksforgeeks.org/tcp-ip-model/) |
| 标题大小 | 它有 4 字节大小的报头 | 它有 2 字节大小的报头 |
| 基于 RESTful | 是的，它使用 REST 原则 | 不，它不使用 REST 原则 |
| 持久性支持 | 它没有这样的支持 | 它支持并最好地用于实时数据通信 |
| 消息标签 | 它通过给消息添加标签来提供。 | 它没有这样的功能。 |
| 可用性/安全性 | 它用于公用区域网络，并具有安全机制。 | 它用于物联网应用，并且是安全的 |

</figure>