# 计算机网络中的电路切换

> 原文:[https://www . geesforgeks . org/circuit-in-computer-network/](https://www.geeksforgeeks.org/circuit-switching-in-computer-network/)

在电路交换中，网络资源(带宽)被分成若干部分，并且在连接期间位延迟是恒定的。发送方和接收方之间建立的专用路径/电路提供了有保证的数据速率。一旦电路建立，数据就可以无延迟地传输。

电话系统网络是电路交换的一个例子。 **TDM(时分复用)和 FDM(频分复用)**是将多个信号复用成单个载波的两种方法。

*   **频分复用:** *分成多个频带*
    当多个数据信号被组合以通过共享通信介质同时传输时，使用频分复用或 FDM。这是一种将总带宽分成一系列不重叠的频率子带的技术，其中每个子带携带不同的信号。无线电频谱中的实际应用&光纤共享多个独立信号。

*   **时分复用:** *划分成帧*
    时分复用(TDM)是一种通过传输线两端的同步开关在公共信号路径上发送和接收独立信号的方法。时分复用用于长距离通信链路，承受来自终端用户的大量数据流量负载。
    时分复用(TDM)也称为数字电路交换。

**电路切换的优势:**
它有以下优势:

1.  电路交换的主要优点是在计算机之间建立了一个保证数据速率的传输信道。
2.  在电路内交换中，由于专用的传输路径，数据流没有延迟。

**电路切换的缺点:**
它有以下缺点:

1.  建立连接需要很长时间。
2.  建立专用信道需要更多的带宽。
3.  即使信道空闲，它也不能用于传输任何其他数据，因为连接专用于电路交换。

电路切换中的公式:

```
Transmission rate = Link Rate or Bit rate / 
                    no. of slots = R/h bps
Transmission time = size of file / 
                    transmission rate 
                 = x / (R/h) = (x*h)/R second
Total time to send packet to destination =
               Transmission time + circuit setup time 
```

**关于电路交换的问题**–
这些问题将帮助您理解电路交换

**示例 1 :** 通过电路交换网络从主机 A 向主机 B 发送一个“x 比特”文件需要多长时间，该网络使用带有“h 时隙”的 TDM，比特率为“R Mbps”，电路建立时间为 k 秒。找到总时间？

**说明:**
传输速率=链路速率或比特率/时隙数= R/h bps
传输时间=文件大小/传输速率= x / (R/h) = (x*h)/R

总时间=传输时间+电路建立时间= (x*h)/R 秒+ k 秒

**例 2 :** 如果一条链路每秒传输 F 帧，每个时隙有 B 比特，那么求传输速率？

**说明:**
由于没有提到每帧有多少槽，所以我们取一帧就有一个槽。
传输速率是 1 秒内发送的数据量。
传输速率= F * B 位/秒

要了解电路交换和分组交换的区别，请参考–[带电路交换的区别&分组交换](https://www.geeksforgeeks.org/computer-network-circuit-switching-vs-packet-switching/)T2】

参考文献:
[【https://en.wikipedia.org/wiki/Circuit_switching】](https://en.wikipedia.org/wiki/Circuit_switching)

本文由 **Shaurya Uppal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。