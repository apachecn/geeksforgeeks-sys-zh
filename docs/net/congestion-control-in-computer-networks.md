# 计算机网络中的拥塞控制

> 原文:[https://www . geeksforgeeks . org/计算机网络拥塞控制/](https://www.geeksforgeeks.org/congestion-control-in-computer-networks/)

What is **congestion**?A state occurs in the network layer when the message traffic is so heavy that it slows down network response time.**Effects** of Congestion**Congestion control algorithms**Let us consider an example to understandImagine a bucket with a small hole in the bottom.No matter at what rate water enters the bucket, the outflow is at a constant rate. When the bucket is full of water additional water enters spills over the sides and is lost.Similarly, each network interface contains a leaky bucket and the following **steps** are involved in the leaky bucket algorithm:**Need** of token bucket Algorithm:-The leaky bucket algorithm enforces output patterns at the average rate, no matter how bursty the traffic is. So in order to deal with the bursty traffic, we need a flexible algorithm so that the data is not lost. One such algorithm is the token bucket algorithm.**Steps** of this algorithm can be described as follows:Let’s understand with an example,In figure (A) we see a bucket holding three tokens, with five packets waiting to be transmitted. For a packet to be transmitted, it must capture and destroy one token. In figure (B) We see that three of the five packets have gotten through, but the other two are stuck waiting for more tokens to be generated.

**令牌桶优于漏桶的方式:**
漏桶算法控制数据包引入网络的速率，但本质上非常保守。令牌桶算法引入了一些灵活性。在令牌桶中，算法令牌在每个刻度处生成(直到某个限制)。对于要传输的传入数据包，它必须捕获令牌，并且传输以相同的速率进行。因此，如果令牌可用，一些繁忙的数据包会以相同的速率传输，从而在系统中引入一定的灵活性。

**公式:** M * s = C + ρ * s
其中 S–是花费的时间
M–最大输出速率
ρ–令牌到达速率
C–令牌桶的容量(以字节为单位)

Let’s understand with an example,

漏桶算法问题链接:[https://www.geeksforgeeks.org/computer-networks-set-8/](https://www.geeksforgeeks.org/computer-networks-set-8/)T2】

本文由[维卡什·库马尔](https://www.quora.com/profile/Vikash-Kumar-164)供稿。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息