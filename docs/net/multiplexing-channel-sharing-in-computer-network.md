# 计算机网络中的复用(信道共享)

> 原文:[https://www . geesforgeks . org/multiplexing-channel-sharing-in-computer-network/](https://www.geeksforgeeks.org/multiplexing-channel-sharing-in-computer-network/)

**复用**是指多个源但只有一条链路。另一种替代方法是直接点对点连接，但它有许多问题，因为它需要每个设备一个输入/输出端口，每个设备一条所需的线路，并且如果在不同的楼层，还需要大量的布线。但是，相反，如果我们使用多路复用器方法，那么所有设备都连接到多路复用器，一条线路连接到主机，该链路承载多个信息通道，线路数量等于输出线路数量。

**多路复用器类型:**

1.  **Frequency Division Multiplexing (FDM) –** 
    The frequency spectrum is divided among the logical channels and each user has exclusive access to his channel. It sends signals in several distinct frequency ranges and carries multiple video channels on a single cable. Each signal is modulated onto a different carrier frequency and carrier frequencies are separated by guard bands. The bandwidth of the transmission medium exceeds the required bandwidth of all the signals. Usually, for frequency division multiplexing analog signaling is used in order to transmit the signals, i.e. more susceptible to noise. Assignment of non-overlapping frequency ranges to each user or signal on a medium. Thus, all signals are transmitted at the same time, each using different frequencies. 

    多路复用器接受输入并为每个器件分配频率。多路复用器连接到高速通信线上。相应的多路复用器或多路分解器位于高速线路的末端，用于分离多路复用信号。频谱被划分到逻辑信道中，每个用户挂在一个特定的频率上。无线电频谱是媒体和从媒体中提取信息的机制的一个例子。

    **FDM 的劣势:**
    FDM 的一个问题是无法充分利用电缆的容量。重要的是频带不要重叠。实际上，为了确保来自一个频带的信号不影响另一个频带的信号，频带之间必须有相当大的间隙。

2.  **Time Division Multiplexing (TDM) –** 
    Each user periodically gets the entire bandwidth for a small burst of time, i.e. entire channel is dedicated to one user but only for a short period of time. It is very extensively used in computer communication and telecommunication. Sharing of the channel is accomplished by dividing available transmission time on a medium among users. It exclusively uses *Digital Signaling* instead of dividing the cable into frequency bands. TDM splits cable usage into time slots. The data rate of transmission media exceeds the data rate of signals. Uses a frame and one slot for each slice of time and the time slots are transmitted whether the source has data or not. 

    有以下两种类型的时分复用:

    1.  **同步时分复用:**
        它是同步的，因为复用器和解复用器必须就时隙达成一致。最初的时分复用。多路复用器以循环方式接受来自连接设备的输入，并以永无止境的模式传输数据。这方面的一些常见例子是 t1 和综合业务数字网电话线。如果一个设备产生数据的速度比其他设备快，那么多路复用器要么对来自该设备的输入数据流进行采样的频率高于对其他设备的采样频率，要么缓冲更快的输入数据流。如果一个设备没有什么要传输的，多路复用器仍然必须将该设备的一段数据插入多路复用流中。

    2.  **统计时分复用:**
        时分但按需而非固定，基于每个数据包重新调度链路，来自不同来源的数据包在链路上交错。它允许连接到电路的节点比电路的容量多。工作的前提是，并非所有节点都将始终以全容量传输。它必须传输终端标识，即目的地 id 号，并且可能需要存储。统计多路复用器只传输活动工作站的数据。如果工作站不活动，多路复用流上不会浪费空间。它接受输入的数据流，并创建一个只包含要传输的数据的帧。

3.  **Wavelength Division Multiplexing –** 
    It is the same as FDM but applied to fibers, only the difference is that here the operating frequencies are much higher actually they are in the optical range. There’s great potential for fibers since the bandwidth is so huge. Fibers with different energy bands are passed through a diffraction grating prism. Combined on the long-distance link and then split at the destination. It has got high reliability and very high capacity. 

    它将多个数据流多路复用到一条光纤线路上。不同波长的激光器(称为 lambdas)传输多个信号。光纤上承载的每个信号可以以不同于其他信号的速率传输。

    *   **密集波分复用**将许多(30、40、50 或更多)通道组合到一根光纤上。密集波分复用信道具有非常高的容量，并且不断改进。
    *   **粗波分复用**只结合了几个λ。在这种情况下，信道间隔更宽，是密集波分复用的一个更便宜的版本。