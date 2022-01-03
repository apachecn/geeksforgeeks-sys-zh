# 计算机网络|第 8 集

> 原文:[https://www.geeksforgeeks.org/computer-networks-set-8/](https://www.geeksforgeeks.org/computer-networks-set-8/)

GATE CS 2008 考试提出了以下问题。

**1)应用层可以传递给下面 TCP 层的最大数据量是多少？**
(A)任意大小
(B) 2^16 字节 tcp 报头大小
(C) 2^16 字节
(D) 1500 字节

答(A)
应用层可以发送任意大小的数据。标准没有限定。如果需要，较低的层划分数据。

**2)客户端进程 P 需要与服务器进程 S 进行 TCP 连接，考虑以下情况:服务器进程 S 依次执行 socket()，bind()和 listen()系统调用，之后被抢占。随后，客户端进程 P 执行套接字()系统调用，然后是 connect()系统调用，以连接到服务器进程 s。服务器进程尚未执行任何 accept()系统调用。以下哪一个事件会发生？**
(A) connect()系统调用返回成功
(B) connect()系统调用阻塞
(C) connect()系统调用返回错误
(D) connect()系统调用导致核心转储

应答(C)
由于未执行 accept()调用，因此 connect()在等待的时间戳内没有得到响应&然后返回无响应服务器错误。

**3)10 Mbps 网络上的计算机由令牌桶管理。令牌桶以 2Mbps 的速率填充。它最初的容量为 16 兆位。计算机以 10Mbps 的速度传输的最大持续时间是多少？**
(A) 1.6 秒
(B) 2 秒
(C) 5 秒
(D) 8 秒

答案(二)

```
New tokens are added at the rate of r bytes/sec which is 
2Mbps in the given question. 

Capacity of the token bucket (b) = 16 Mbits
Maximum possible transmission rate (M) = 10Mbps
So the maximum burst time = b/(M-r) = 16/(10-2) = 2 seconds

```

在上面的公式中，从 M 中减去 r 来计算最大突发时间。这种减法的原因是，当传输以最大传输速率 m 发生时，以速率 r 添加新的令牌。

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见[门角](http://geeksquiz.com/gate-corner-2/)。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论