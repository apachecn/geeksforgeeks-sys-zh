# 什么是环回地址？

> 原文:[https://www.geeksforgeeks.org/what-is-a-loopback-address/](https://www.geeksforgeeks.org/what-is-a-loopback-address/)

一个**环回地址**是一个不同的保留 [IP 地址](https://www.geeksforgeeks.org/what-is-an-ip-address/)范围，从 127.0.0.0 开始，到 127.255.255.255 结束，尽管 127.255.255.255 是 127.0.0.0/8 的广播地址。环回地址内置于 IP 域系统中，使设备能够发送和接收数据包。环回地址 127.0.0.1 通常被称为 localhost。

[TCP/IP 协议](https://www.geeksforgeeks.org/tcp-ip-in-computer-networking/)管理操作系统中所有的环回地址。它模拟同一系统上的 TCP/IP 服务器或 TCP/IP 客户端。这些环回地址总是可以访问的，因此用户可以随时使用它们来排除 TCP/IP 故障。

每当协议或程序从具有任何环回 IP 地址的计算机发送任何数据时，该流量都由自身内部的 TCP/IP 协议栈处理，即不将其传输到网络。也就是说，如果用户正在 ping 一个环回地址，他们将从运行在他们的计算机上的同一个 TCP/IP 堆栈中获得回复。因此，作为目的地址传输到任何环回地址的所有数据都不会在网络上弹出。

*127.0.0.1 是最常用的环回地址*；一般来说，127.0.0.1 和 localhost 在功能上是相似的，即环回地址 127.0.0.1 和主机名 localhost；内部映射。尽管如此，其他环回地址也是可以访问和使用的。

**IPv4 和 IPv6 环回地址:**

*   The loopback address of IP v4 is 127.0.0.0/8, and the most commonly used loopback address is 127.0.0.1.
*   IPv6 loopback address is:: 1

**如何使用“ping”命令:**

*   To use the ping command, go to the window start menu.
*   Search for Command Prompt.
*   Enter "ping" and then enter the loopback address. And,
*   Click enter.

例如，如下图所示，四个不同 IPv4 环回地址(127.0.0.0、127.0.0.1、127.15.90.69 和 127.255.255.255)的输出网络和广播地址是不可达环回地址和 IPv6 环回地址::1。

[**ping**](https://www.geeksforgeeks.org/what-is-ping/)T5】输出为 127.0.0.0(网络地址)。

```
C:\Users\bklad>ping 127.0.0.0

Pinging 127.0.0.0 with 32 bytes of data:
General failure.
General failure.
General failure.
General failure.

Ping statistics for 127.0.0.0:
   Packets: Sent = 4, Received = 0, Lost = 4 (100% loss),
```

**ping 输出为 127.0.0.1**

```
C:\Users\bklad>ping 127.0.0.1

Pinging 127.0.0.1 with 32 bytes of data:
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128
Reply from 127.0.0.1: bytes=32 time<1ms TTL=128

Ping statistics for 127.0.0.1:
   Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
   Minimum = 0ms, Maximum = 0ms, Average = 0ms  
```

**ping 输出为 127.15.90.69**

```
C:\Users\bklad>ping 127.15.90.69

Pinging 127.15.90.69 with 32 bytes of data:
Reply from 127.15.90.69: bytes=32 time<1ms TTL=128
Reply from 127.15.90.69: bytes=32 time<1ms TTL=128
Reply from 127.15.90.69: bytes=32 time<1ms TTL=128
Reply from 127.15.90.69: bytes=32 time<1ms TTL=128

Ping statistics for 127.15.90.69:
   Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
   Minimum = 0ms, Maximum = 0ms, Average = 0ms
```

**ping 输出为 127.255.255.255 (** [**广播地址**](https://www.geeksforgeeks.org/what-is-limited-broadcast-address/) **)。**

```
C:\Users\bklad>ping 127.255.255.255

Pinging 127.255.255.255 with 32 bytes of data:
Request timed out.
Request timed out.
Request timed out.
Request timed out.

Ping statistics for 127.255.255.255:
   Packets: Sent = 4, Received = 0, Lost = 4 (100% loss),
```

**ping 输出为::1。**

```
C:\Users\bklad>ping ::1

Pinging ::1 with 32 bytes of data:
Reply from ::1: time<1ms
Reply from ::1: time<1ms
Reply from ::1: time<1ms
Reply from ::1: time<1ms

Ping statistics for ::1:
   Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),
Approximate round trip times in milli-seconds:
   Minimum = 0ms, Maximum = 0ms, Average = 0ms
```

**环回地址的优势:**

*   Finding devices on the network is an efficient method.
*   It can be configured as the router ID of [BGP](https://www.geeksforgeeks.org/border-gateway-protocol-bgp/) [OSPF](https://www.geeksforgeeks.org/open-shortest-path-first-ospf-protocol-fundamentals/) and other protocols.
*   Used as source address and destination address for testing network connectivity.
*   It can also be used to test IP software.

**缺点:**

*   Just like a physical interface, you need a unique address.