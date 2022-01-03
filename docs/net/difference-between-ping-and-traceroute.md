# 【Ping 和 Traceroute 的区别

> 原文:[https://www . geesforgeks . org/ping 和 traceroute 的区别/](https://www.geeksforgeeks.org/difference-between-ping-and-traceroute/)

在计算机网络中，数据以称为数据包的小块形式发送。每个数据包都是单独传输的，也可能遵循不同的路由到达目的地。一旦原始消息的所有这些包到达目的地，它们就被重新组装以形成原始消息。但是，有时可能会发生网络服务器关闭、网络拥塞或其他技术故障，这可能会阻止消息到达目的地。为了诊断此类拥塞和网络故障，我们使用了两个常用程序，即 Ping 和 Traceroute。

**Ping**–这是一个实用程序，可以帮助用户检查特定的 IP 地址是否可访问。Ping 通过向指定地址发送数据包并等待回复来工作。它还测量往返时间并报告错误。

Ping 还用于检查本地网络上的计算机是否处于活动状态。为此，用户必须进入命令提示符并键入:ping 127.0.0.1，如果地址是活动的，ping 将返回如下消息:

```
Pinging 127.0.0.1 with 32 bytes of data
Reply from 127.0.0.1: bytes=32 time<10ms TTL=32
Reply from 127.0.0.1: bytes=32 time<10ms TTL=32
Reply from 127.0.0.1: bytes=32 time<10ms TTL=32
Reply from 127.0.0.1: bytes=32 time<10ms TTL=32
```

IP 地址 127.0.0.1 是本地主机的地址，即使发件人没有连接到互联网，也会收到 ping 回复。

**Traceroute**–它是一个实用程序，可以跟踪从您的计算机到主机的数据包，并且还会显示到达那里所需的步数(跳数)，以及每一步所需的时间。Traceroute 的工作原理是发送生存时间较短的数据包(生存时间 TTL)，它指定了数据包在返回之前可以生存多少步(跳)。当数据包无法到达最终目的地并在中间步骤过期时，该节点会返回数据包并标识自己。因此，通过逐渐增加 TTL，Traceroute 能够识别中间主机。如果任何一跳返回“请求超时”，则表示网络拥塞，以及网页加载缓慢和连接中断的原因。

Ping 和 Traceroute 的主要区别在于，Ping 是一个快速简单的实用程序，可以告诉您指定的服务器是否可访问，以及从服务器发送和接收数据需要多长时间，而 Traceroute 则可以找到到达服务器所需的确切路由以及每一步(跳)所需的时间。

详见[追踪路线](https://www.geeksforgeeks.org/traceroute-in-network-layer/)。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论