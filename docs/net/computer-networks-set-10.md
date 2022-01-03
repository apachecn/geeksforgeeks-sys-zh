# 计算机网络|第 10 集

> 原文:[https://www.geeksforgeeks.org/computer-networks-set-10/](https://www.geeksforgeeks.org/computer-networks-set-10/)

GATE CS 2007 考试提出了以下问题。

**1)将 B 类主机的地址拆分为子网，子网号为 6 位。子网的最大数量和每个子网中主机的最大数量是多少？**
(一)62 个子网，262142 台主机。
(B) 64 个子网，262142 台主机。
(丙)62 个子网，1022 台主机。
(D) 64 个子网，1024 台主机。

答案(C)
*最大子网数= 2^6-2 =62。*
注意从 2^6.中减去 2RFC 950 规范保留了由全 0(见上文)和全 1(广播)组成的子网值，将可用子网数量减少了两个。

*最大主机数为 2^10-2 = 1022。*
2 减去主机数量也是。所有位为 1 的地址被保留为广播地址，所有主机 id 位为 0 的地址被用作子网的网络地址。
通常，每个网络中可用于寻址特定主机的地址数量始终为 2^n-2，其中 n 是主机 id 的位数。
详见[本](http://en.wikipedia.org/wiki/Subnetwork#Subnet_and_host_counts)

**2)消息 11001001 将使用 CRC 多项式 x^3 + 1 来传输，以防止其出错。应该传递的信息是:**T4(A)11001001000
(B)11001001011
(C)11001010
(D)110010010011

答案(B)
多项式 x^3+1 对应的除数是 1001。

```
11001001 000  <--- input right padded by 3 bits
1001          <--- divisor
01011001 000  <---- XOR of the above 2
 1001         <--- divisor
00010001 000
   1001
00000011 000
      10 01
00000001 010
       1 001
00000000 011 <------- remainder (3 bits)

```

划分流程见[本](http://en.wikipedia.org/wiki/Cyclic_redundancy_check#Computation_of_CRC)。
给定的消息 11001001 除以 1001 后，我们得到的余数是 011，也就是 CRC。传输的数据是，消息+循环冗余校验，即 11001001 011。

**3)M 和 N 两个站的距离为 L 公里。所有帧都是 K 位长。每公里传播延迟为 t 秒。设 R 位/秒为信道容量。假设处理延迟可以忽略不计，当使用滑动窗口协议时，帧中序列号字段的最小位数为最大利用率:**
[![](img/a34b938a65bf1e475d8bca768e48dd31.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/gate2008cn.gif)

答案(三)

```
Distance between stations = L KM
Propogation delay per KM = t seconds
Total propagation delay = Lt seconds

Frame size = k bits
Channel capacity = R bits/second
Transmission Time = k/R

Let n be the window size.

UtiliZation = n/(1+2a) where a = Propagation time / transmission time
            = n/[1 + 2LtR/k]
            = nk/(2LtR+k) 
For maximum utilization: nk = 2LtR + k
Therefore, n = (2LtR+k)/k
Number of bits needed for n frames is Logn.

```

详见[本](http://nptel.iitm.ac.in/courses/Webcourse-contents/IIT%20Kharagpur/Computer%20networks/pdf/M3L3.pdf)。

**4)搭配以下:**

```
(P) SMTP     (1) Application layer
(Q) BGP      (2) Transport layer
(R) TCP      (3) Data link layer
(S) PPP      (4) Network layer
             (5) Physical layer 
```

(一)P–2 Q–1 R–3S–5
(二)P–1 Q–4 R–2S–3
(三)P–1 Q–4 R–2S–5
(四)P–2 Q–4 R–1S–3

答(二)
[SMTP](http://en.wikipedia.org/wiki/Simple_Mail_Transfer_Protocol) 是一种用于电子邮件传输的应用层协议。
[TCP](http://en.wikipedia.org/wiki/Transmission_Control_Protocol) 是一种核心传输层协议。
[BGP](http://en.wikipedia.org/wiki/Border_Gateway_Protocol) 是一种支持互联网上核心路由决策的网络层协议
[PPP](http://en.wikipedia.org/wiki/Point-to-point_protocol) 是一种常用于在两个联网节点之间建立直接连接的数据链路层协议。

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见[门角](http://geeksquiz.com/gate-corner-2/)。**

如果您发现任何答案/解释不正确，或者您想分享关于上述主题的更多信息，请写评论