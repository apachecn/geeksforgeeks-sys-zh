# 计算机网络|第 9 集

> 原文:[https://www.geeksforgeeks.org/computer-networks-set-9/](https://www.geeksforgeeks.org/computer-networks-set-9/)

GATE CS 2007 考试提出了以下问题。

**1)以下哪一项使用 UDP 作为传输协议？**
(一)HTTP
(二)Telnet
(三)DNS
(四)SMTP

答案(C)
[DNS](http://en.wikipedia.org/wiki/Domain_Name_System) 主要使用端口号 53 上的用户数据报协议(UDP)来服务请求。DNS 查询由来自客户端的单个 UDP 请求和来自服务器的单个 UDP 回复组成。

**2)在使用曼彻斯特编码的以太网中，比特率为:**
(A)波特率的一半。
(B)两倍波特率。
(丙)与波特率相同。
(D)以上都不是

答案(A)
在[曼彻斯特编码](http://en.wikipedia.org/wiki/Manchester_code)中，[比特率](http://en.wikipedia.org/wiki/Bit_rate)是[波特率的一半。](http://en.wikipedia.org/wiki/Baud)

**3)一个时隙局域网中有 n 个站。每个站尝试在每个时隙中以概率 p 发送。在给定的时隙内，只有一个站传输的概率是多少？**
(a)(1-p)^(n-1)
(b)np(1-p)^(n-1)
(c)p(1-p)^(n-1)
(d)1-(1-p)^(n-1)

答案(B)
特定站发送而没有其他人发送的概率= p*(1-p)^(n-1)
任何站可以发送的概率= n*(特定站发送的概率)= n*p*(1-p)^(n-1).详见[本](http://www.cs.umd.edu/~shankar/417-F01/Slides/chapter5a-aus/sld022.htm)。

**4)在令牌环网中，传输速度为 10^7 bps，传播速度为 200 米/微秒。这个网络中的 1 位延迟相当于:**
(A) 500 米的电缆。
(B) 200 米电缆。
(丙)20 米长的电缆。
(D) 50 米的电缆。

答案(C)
传输延迟为 1 位 t = 1/(10^7) = 0.1 微秒。
1 微秒可行驶 200 米。因此，在 0.1 微秒内，可以行驶 20 米。

**请参见**[**GATE Corner**](http://geeksquiz.com/gate-corner-2/)**查看往年所有论文/解答/说明、教学大纲、重要日期、笔记等。**

如果您发现任何答案/解释不正确，或者您想分享更多关于以上讨论主题的信息，请写评论