# 远程直接内存访问(RDMA)

> 原文:[https://www . geesforgeks . org/remote-direct-memory-access-rdma/](https://www.geeksforgeeks.org/remote-direct-memory-access-rdma/)

**远程直接内存访问(RDMA)** 是网络中一台计算机对另一台计算机内存的访问，不涉及一台计算机的操作系统、处理器或缓存。它释放了许多资源，从而提高了系统的吞吐量和性能。

读写等操作可以在远程机器上执行，而不会中断该机器的中央处理器。这项技术有助于提高数据传输速率和低延迟联网。RDMA 通过启用网络适配器将数据直接传输到系统的缓冲区，使用*零拷贝网络*。

**RDMA 特色:**

1.  **零拷贝网络–**
    数据可以在应用程序的缓冲区之间直接发送和接收，而无需在网络层之间拷贝。
2.  **减少 CPU 的参与–**
    应用程序可以直接从远程服务器访问数据，而不会消耗远程服务器的 CPU 时间。远程服务器的中央处理器的高速缓冲存储器也不会被访问的内容填满。
3.  **有效交易–**
    数据以离散消息的形式发送和接收，而不是流的形式，这消除了分离消息的需要。

**支持 RDMA 的网络协议:**

1.  **InfiniBand(IB)–**
    从一开始就支持 RDMA 的协议。由于是新的网络技术，需要[网卡](https://www.geeksforgeeks.org/nic-full-form/)和[交换机](https://www.geeksforgeeks.org/types-of-switches-in-computer-network/)支持该技术。
2.  **融合以太网上的 RDMA(RoCE)–**
    一种允许在[以太网](https://www.geeksforgeeks.org/ethernet-frame-format/)上执行 RDMA 操作的网络协议。这允许在标准以太网基础设施(交换机)上使用 RDMA。
3.  **互联网广域 RDMA 协议(iWARP)–**
    一种允许通过 [TCP](https://www.geeksforgeeks.org/tcp-and-udp-in-transport-layer/) 执行 RDMA 操作的协议。iWARP 不支持 IB 和 RoCE 的某些功能。这允许在标准以太网基础设施(交换机)上使用 RDMA。

**应用:**

*   用于云计算等需要小 CPU 占用空间的行业。
*   用于医疗设备、存储和备份等需要高带宽的行业。