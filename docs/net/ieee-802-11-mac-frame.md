# IEEE 802.11 Mac 帧

> 原文:[https://www.geeksforgeeks.org/ieee-802-11-mac-frame/](https://www.geeksforgeeks.org/ieee-802-11-mac-frame/)

**先决条件–**[Wi-fi 基础知识](https://www.geeksforgeeks.org/basics-of-wi-fi/)
MAC 层为控制媒体访问等多项任务提供功能，还可以为漫游、身份验证和节能提供支持。媒体访问控制提供的基本服务是强制异步数据服务和可选的时间限制服务。
IEEE 802.11 定义了两个 MAC 子层:-

1.  **分布式协调功能(DCF)–**
    DCF 使用 CSMA/CA 作为接入方式，因为无线局域网无法实现 CSMA/光盘。它只提供异步服务。
2.  **点协调功能(PCF)–**
    PCP 在 DCF 之上实现，主要用于授时传输。它使用集中、无争用的轮询访问方法。它提供异步和时间限制服务。

**MAC 帧:**
MAC 层帧由 9 个字段组成。下图显示了 IEEE 802.11 媒体访问控制数据帧的基本结构以及帧控制字段的内容。

![](img/57770374c6952e7f71dc74aa204d9d3b.png)

*   **帧控制(FC)–**
    它是一个 2 字节长的字段，用于定义帧的类型和一些控制信息。光纤通道中的各种字段包括:

1.  **版本:**
    是一个 2 位长的字段，表示当前协议版本，目前固定为 0。
2.  **类型:**
    它是一个 2 位长的字段，决定了帧的功能，即管理(00)、控制(01)或数据(10)。值 11 被保留。
3.  **子类型:**
    这是一个 4 位长的字段，表示帧的子类型，如关联请求为 0000，信标为 1000。
4.  **至 DS:**
    这是一个 1 位长的字段，设置后表示目的帧是用于 DS(分发系统)的。
5.  **来自 DS:**
    这是一个 1 位长的字段，设置后表示帧来自 DS。
6.  **更多片段(更多片段):**
    这是一个 1 位长的字段，当设置为 1 时，表示帧后有其他片段。
7.  **重试:**
    是 1 位长的字段，如果当前帧是前一帧的重传，该位设置为 1。
8.  **电源管理(电源管理):**
    这是一个 1 位长的字段，表示成功传输帧后的站点模式。该字段设置为 1 表示工作站进入省电模式。如果该字段设置为 0，电台将保持活动状态。
9.  **更多数据:**
    这是一个 1 位长的字段，用于指示接收方发送方比当前帧有更多的数据要发送。这可以由接入点用来向处于省电模式的站指示更多的分组被缓冲，或者它可以由站用来在被轮询之后向接入点指示更多的轮询是必要的，因为该站有更多的数据准备发送。
10.  **WEP:**
    是 1 比特长的字段，表示应用了 802.11 的标准安全机制。
11.  **顺序:**
    这是一个 1 位长的字段，如果该位设置为 1，则必须严格按照顺序处理接收到的帧。

*   **Duration/ID –**
    It is 4 bytes long field which contains the value indicating the period of time in which the medium is occupied(in µs).*   **Address 1 to 4 –**
    These are 6 bytes long fields which contain standard IEEE 802 MAC addresses (48 bit each). The meaning of each address depends on the DS bits in the frame control field.*   **SC (Sequence control) –**
    It is 16 bits long field which consists of 2 sub-fields, i.e., Sequence number (12 bits) and Fragment number (4 bits). Since acknowledgement mechanism frames may be duplicated hence, a sequence number is used to filter duplicate frames.*   **Data –**
    It is a variable length field which contain information specific to individual frames which is transferred transparently from a sender to the receiver(s).*   **CRC(循环冗余校验)–**
    它是一个 4 字节长的字段，包含一个 32 位的 CRC 检错序列，以确保无错帧。