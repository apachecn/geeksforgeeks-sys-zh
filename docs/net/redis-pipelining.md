# 重复管道铺设

> 哎哎哎:# t0]https://www . geeksforgeeks . org/redis-pipelining/

**Redis** 是支持请求或响应协议的传输控制协议(TCP)服务器。请求分两步完成:

*   客户端以阻塞方式向服务器发送查询，得到服务器响应。
*   然后服务器操作命令，并将查询的响应结果发送回客户端。

**什么是流水线:**
在流水线中，客户端可以向服务器发送多个查询或请求，完全不需要等待查询的所有回复，最终可以一次读取回复。在流水线操作中，客户需要读命令的应答，然后才能调用写命令。

**Redis 流水线的优势:**
Redis 流水线的主要优势是提升协议性能。它提高了 Redis 的性能，因为多个命令同时执行。通过流水线操作获得的速度范围从本地主机连接的 5 倍到低速互联网连接的至少 100 倍。

**示例:**
我们来看一个场景，我们将一次向 Redis 提交多个命令，然后它将一次性提供所有命令的输出。

打开 Redis 终端，输入以下命令:

(echo-en“PING \ r \ n SET master geeks forgeeks \ r \ n GET master \r\n INCR 访问者\r\n INCR 访问者\ r \ n INCR 访问者\ r \ n”；休眠 15) |
nc localhost 6876

**输出:**

**1<sup>ST</sup>Run:**T4】$(echo-en“PING \ r \ n SET master geeks forgeeks \ r \ n GET master \r\n INCR 访问者\r\n INCR 访问者\ r \ n INCR 访问者\ r \ n”；睡眠|

```
nc localhost 6876  
+PONG 
+OK 
geeksforgeeks
:5 
:6 
:7 
```

**2<sup>nd</sup>Run:**T4】$(echo-en“PING \ r \ n SET master geeks forgeeks \ r \ n GET master \r\n INCR 访问者\r\n INCR 访问者\ r \ n INCR 访问者\ r \ n”；睡眠|

```
nc localhost 6876  
+PONG 
+OK 
geeksforgeeks
:8 
:9 
:10
```

**注:**

*   PING 命令用于检查 redis 的连接。
*   一个名为“master”的字符串集具有值“geeksforgeeks”。
*   获得了密钥值，并将访问者数量增加了 3 倍。