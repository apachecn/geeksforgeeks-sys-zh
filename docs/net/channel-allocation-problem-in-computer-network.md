# 计算机网络中的信道分配问题

> 原文:[https://www . geesforgeks . org/channel-分配-计算机网络中的问题/](https://www.geeksforgeeks.org/channel-allocation-problem-in-computer-network/)

**信道分配**是为了承载用户特定的任务，将单个信道划分分配给多个用户的过程。每次过程发生时，用户的数量可能会有所不同。如果有 N 个用户，并且信道被分成 N 个大小相等的子信道，则每个用户被分配一个部分。如果用户数量很少，并且不经常变化，那么可以使用频分复用，因为它是一种简单有效的信道带宽分配技术。

信道分配问题可以通过两种方案来解决:局域网和城域网中的静态信道分配和动态信道分配。

![](img/abf09952510d61bee06a12743ccd3c57.png)

这些解释如下。

**1。局域网和城域网中的静态信道分配:**
这是在多个竞争用户之间分配单个信道的经典或传统方法[频分复用(FDM)](https://www.geeksforgeeks.org/computer-network-frequency-division-and-time-division-multiplexing/) 。如果有 N 个用户，带宽被分成 N 个大小相等的部分，每个用户被分配一个部分。由于每个用户都有一个专用频带，因此用户之间没有接口。

分成固定数量的块是没有效率的。

```
T = 1/(U*C-L)

T(FDM) = N*T(1/U(C/N)-L/N) 
```

其中，

```
T = mean time delay,
C = capacity of channel,
L = arrival rate of frames,
1/U = bits/frame,
N = number of sub channels,
T(FDM) = Frequency Division Multiplexing Time 
```

**2。动态渠道分配:**
可能的假设包括:

1.  **站模型:**
    假设 N 个站中的每一个独立产生帧。在间隔 IDt 内产生数据包的概率，其中 I 是新帧的恒定到达速率。

2.  **单信道假设:**
    在这个分配中，所有的站都是等价的，并且可以在那个信道上发送和接收。

3.  **碰撞假设:**
    如果两帧在时间上重叠，那就是碰撞。任何冲突都是错误，两帧都必须重新传输。冲突只是可能的错误。

4.  **时间**可分为有槽或连续。

5.  **站**可以在尝试之前感知到某个频道正忙。

**协议假设:**

*   n 个独立电台。
*   站被阻塞，直到它生成的帧被发送。
*   在一段长度 Dt 内生成帧的概率是 IDt，其中 I 是帧的到达速率。
*   只有一个频道可用。
*   时间可以是连续的，也可以是开槽的。
*   **载波侦听:**站可以在传输前检测信道是否已经繁忙。
*   **无载波侦听:**用于侦听丢失数据的超时。