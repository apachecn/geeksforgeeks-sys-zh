# 万兆以太网

> 原文:[https://www.geeksforgeeks.org/10-gigabit-ethernet/](https://www.geeksforgeeks.org/10-gigabit-ethernet/)

**先决条件–**[千兆以太网](https://www.geeksforgeeks.org/introduction-of-gigabit-ethernet/)

IEEE 要求 802 委员会从万兆以太网开始。工作模式与之前的[以太网标准](https://www.geeksforgeeks.org/ethernet-frame-format/)相同。10 Gbps 是一个真正伟大的速度，比最初的以太网快 1000 倍。数据中心和交换机内部可能需要它来连接高端路由器、交换机和服务器，办公室之间的长距离高带宽干线也可能需要它来支持基于以太网和光纤的整个区域网络。短距离连接可以使用铜或光纤，而长距离连接可以使用光纤。

万兆以太网支持唯一的全双工操作。他们专注于能够高速运行的物理层细节。CSMA/光盘不再是万兆以太网的一部分。不过，兼容性仍然很重要，因此万兆以太网接口会自动协商，并回落到线路两端支持的最高速度。

下表列出了万兆以太网的主要类型。中距离使用波长为 0.85(短)的多模光纤，长距离使用 1.3(长)和 1.5(长)的单模光纤。为了使其适用于广域应用，人们可以使用 10GBase-ER，它可以运行 40 公里的距离。所有版本的万兆以太网都发送一个串行信息流，该信息流是通过对数据位进行加扰，然后用 **64B/66B** 代码进行编码而产生的。

**表:万兆以太网布线**

| 名字 | 电缆 | 最大值段 | 优势 |
| 10GBase-SR | 纤维光学 | 高达 300 米 | 多模光纤(0.85) |
| 10GBase-LR | 纤维光学 | 10 公里 | 单模光纤(1.3) |
| 10G 基站 | 纤维光学 | 40 公里 | 单模光纤(1.5) |
| 10GBase-CX4 | 4 对双斧 | 15 米 | 双轴铜 |
| 10G 基-T | 4 双 UTP | 100 米 | 6a 类 UTP |

10GBase-CX4 是第一个定义的铜质版本。它使用带有四对双轴向铜线的电缆。它以 3.125 Gsymbols/秒的速度运行，达到 10 Gbps。这种版本的铜比光纤便宜，但从长远来看，它是否会被更多普通双绞线上的 10 千兆以太网击败。

10GBase-T 中使用了 UTP 电缆。毫不奇怪，通过双绞线达到 10 Gbps 的物理层相当复杂。为了在两个方向上发送 2500 兆比特/秒，使用了四个双绞线。使用 800 兆字节/秒的信号速率和使用 16 个电压电平的符号可以达到这个速度。为了标准化以 40Gbps 和 100 Gbps 运行的以太网，IEEE 创建了一个组。专有产品已经上市，但标准尚未完成。