# 计算机网络中一个通道的容量

> 原文:[https://www . geesforgeks . org/计算机网络通道容量/](https://www.geeksforgeeks.org/capacity-of-a-channel-in-computer-network/)

通道容量是指**传输介质(导线或链路)**的容量。容量是传输介质可以容纳的位数。所以基本上有两种类型的信道——全双工和半双工。

1.  **Half duplex–** Transmission can be carried out in one direction at a time.
2.  **Full duplex–** Transmission can be carried out in both directions at the same time.

**例如**，传输介质以其最大容量运行，此时它所保持的位数称为传输介质的容量。

**但是如何从数学上找到容量呢？**

*   If the length of the transmission medium is longer, its capacity will be higher.
*   It also depends on the cross-sectional area of the medium.
*   If the bandwidth is 1 bps, it can occupy 1 bit per second. Every second, it moves forward, so that the next bit can occupy space. Therefore, the final time when it will occupy all bits will be its propagation delay.

信道的容量取决于两件事:

1.  bandwidth
2.  propagation delay

```
Capacity = bandwidth * propagation delay 
(in case of half duplex)

Capacity =2* bandwidth * propagation delay 
(in case of full duplex) 
```