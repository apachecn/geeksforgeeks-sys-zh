# 高级数据链路控制(HDLC)封装

> 原文:[https://www . geesforgeks . org/高层-数据-链路-控制-HDLC-封装/](https://www.geeksforgeeks.org/high-level-data-link-control-hdlc-encapsulation/)

[高级数据链路控制(HDLC)](https://www.geeksforgeeks.org/basic-frame-structure-of-hdlc/) 基本上通过网络或通信链路提供可靠的数据帧传输。HDLC 提供了各种操作，如框架、数据透明性、错误检测和纠正，甚至流量控制。主站只是发送包含从站地址的命令。然后，辅助站简单地发送包含其自身地址的响应。

**HDLC 封装协议:**
我们知道，HDLC 的每一帧至少包括 6 到 7 个字段，如开始/结束标志字段、控制字段、信息字段、FCS(帧校验序列)字段。标准 HDLC 协议包含六个字段。而另一方面，思科 HDLC 包含一个额外的协议字段。标准协议使用仅支持一种协议，而 cHDLC 协议使用支持多协议环境。由于报头中的协议字段，支持多种协议是可能的，这有助于识别不同的协议。cHDLC 基本上是由思科系统公司创建的。

*   **地址字段–**
    该字段用于识别和指定存在于 cHDLC 帧中的数据包类型。单播数据包可以是 0*0F，广播数据包可以是 0*8F。
*   **控制字段–**
    该字段始终设置为零，即 0*00。

*   **Protocol field –**
    This field is especially required to specify and identify type of protocol that is being encapsulated withing cHDLC frame. It can be 0x0800 for Internet Protocol.

    **验证 HDLC 封装:**
    我们知道 HDLC 一般是思科路由器上串行接口的默认封装方式。因此，它不会在任何运行配置中列出。这仅仅意味着为了验证 HDLC 封装，我们甚至不能使用 show running-config 命令。因此，我们必须使用 show interfaces (Interface)命令来识别和查看接口中的封装类型。

    ```
    Router#show interfaces serial 0/0/0
    Serial0/0/0 is administratively down, line protocol is down (disabled)
      Hardware is HD64570
      MTU 1500 bytes, BW 1544 Kbit, DLY 20000 usec,
      reliability 255/255, txload 1/255, rxload 1/255
      Encapsulation HDLC, loopback not set, keepalive set (10 sec)
      Last input never, output never, output hang never
      Last clearing of "show interface" counters never 
    ```

    输出将显示 HDLC 的封装类型。

    **HDLC 封装故障排除:**
    要查看和了解串行接口的当前状态，我们可以使用下面给出的两种命令:

    *   显示 ip 接口简介
    *   显示界面[界面]

    Show controllers 命令是一个重要的诊断工具，有助于排除串行线路故障。该命令输出还指示接口通道的状态以及接口上是否连接了电缆。有一些原因导致了在 HDLC 实施过程中出现的一些问题，由于这些问题，议定书的地位将下降。

    这些原因如下:

    *   远程端存在非思科路由器。
    *   远程路由器使用其他协议，如 PPP。
    *   DCE(数据电路终端设备)设备无法向数据终端设备提供时钟速率。
    *   卡的内部布线有问题。
    *   未知的电气接口。

    下面给出了一些串行接口问题:

    1.  **串行 x 启动，线路协议启动–**
        该命令指示线路启动并正常运行。没有任何行动的要求。
    2.  **Serial x is down, Line Protocol is down (DTE mode) –**
        This command indicates that there is an issue. This issue can arise due to different reasons. Some of them are given below:
        *   **电缆故障–**
            此问题可以通过交换所有故障电缆来解决。
        *   **硬件故障–**
            这个问题可以通过将串行线换到另一个端口来解决。
    3.  **串口 x 开启，线路协议关闭(DTE 模式)–**
        该命令也表示存在问题。出现此问题的原因可能是本地或远程配置错误。这个问题可以通过将调制解调器、CSU(通道服务单元)或 DSU(数据服务单元)置于本地环回模式，然后使用 show interface serial 命令来解决。该命令指示线路协议是否启动。