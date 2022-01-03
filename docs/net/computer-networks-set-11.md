# 计算机网络|第 11 集

> 原文:[https://www.geeksforgeeks.org/computer-networks-set-11/](https://www.geeksforgeeks.org/computer-networks-set-11/)

GATE CS 2006 考试提出了以下问题。

**1)站 A 使用滑动窗口协议使用 32 字节的数据包向站 B 发送消息。A 和 B 之间的往返延迟为 80 毫秒，A 和 B 之间路径上的瓶颈带宽为 128 kbps。A 应该使用的最佳窗口大小是多少？**
(一)20
(二)40
(三)160
(四)320

答案(二)

```
Round Trip propagation delay = 80ms 
Frame size = 32*8 bits
Bandwidth = 128kbps
Transmission Time = 32*8/(128) ms = 2 ms

Let n be the window size.

UtiliZation = n/(1+2a) where a = Propagation time / transmission time
            = n/(1+80/2)

For maximum utilization: n = 41 which is close to option (B)

```

**2)两台电脑 C1 和 C2 配置如下。C1 的 IP 地址为 203.197.2.53，网络掩码为 255.255.128.0。C2 的 IP 地址为 203.197.75.201，网络掩码为 255.255.192.0。以下哪个陈述是正确的？**
(A) C1 和 C2 都假设他们在同一个网络上
(B) C2 假设 C1 在同一个网络上，但是 C1 假设 C2 在不同的网络上
(C) C1 假设 C2 在同一个网络上，但是 C2 假设 C1 在不同的网络上
(D) C1 和 C2 都假设他们在不同的网络上。

答案(三)

```
Network Id of C1 = bitwise '&' of IP of C1 and subnet mask of C1 
                 = (203.197.2.53) & (255.255.128.0) 
                 = 203.197.0.0
C1 sees network ID of C2 as bitwise '&' of IP of C2 and subnet mask of C1 
                = (203.197.75.201) & (255.255.128.0) 
                = 203.197.0.0
which is same as Network Id of C1.

Network Id of C2 = bitwise '&' of IP of C2 and subnet mask of C2
                 = (203.197.75.201) & (255.255.192.0) 
                 = 203.197.64.0
C2 sees network ID of C1 as bitwise '&' of IP of C1 and subnet mask of C2
                = (203.197.2.53) & (255.255.192.0) 
                = 203.197.0.0
which is different from Network Id of C2.

```

因此，C1 假设 C2 在同一个网络上，而 C2 假设 C1 在不同的网络上。

**3)站 A 需要使用滑动窗口(窗口大小 3)和 go-back-n 差错控制策略向站 B 发送由 9 个分组组成的消息。所有数据包都已准备就绪，可以立即传输。如果 A 发送的每第 5 个数据包都丢失了(但是 B 的 ack 没有丢失)，那么 A 将发送多少个数据包来发送消息给 B？**
(一)12
(二)14
(三)16
(四)18

答案(C)
总共发送了 16 个数据包。事件顺序见下表。由于使用了[回退-n](http://en.wikipedia.org/wiki/Go-Back-N_ARQ) 错误控制策略，丢失数据包后的所有数据包都会被再次发送。

```
Sender      Receiver
 1            
 2            1
 3            2
 4            3
 5            4
 6           
 7            6
              7             
          [Timeout for 5] 

 5
 6            5
 7            6
 8
 9           
              8
              9
          [Timeout for 7]

 7           
 8            7
 9            8

         [Timeout for 9]
 9           
              9

```

**所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见[门角](http://geeksquiz.com/gate-corner-2/)。**

如果您发现任何答案/解释不正确，或者您想分享更多关于上述主题的信息，请写评论