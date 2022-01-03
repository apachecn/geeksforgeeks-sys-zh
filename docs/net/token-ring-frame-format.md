# 令牌环帧格式

> 原文:[https://www.geeksforgeeks.org/token-ring-frame-format/](https://www.geeksforgeeks.org/token-ring-frame-format/)

先决条件–[以太网帧格式](https://www.geeksforgeeks.org/computer-network-ethernet-frame-format/)

*   **拓扑–**环形拓扑
*   **传输–**单向
*   **编码–**差分曼彻斯特编码
*   **访问控制–**令牌传递
*   **数据速率–**4 Mbps，16 Mbps

### 令牌环帧格式:

![](img/f0fa8230961e9fc229f87967b178f629.png)

![](img/9a7be55781c0dc846ebf2cd5be90977f.png)

*   **Start frame delimiter (SFD) –** Alerts each station for the arrival of token(or data frame) or start of the frame. It is used to synchronize clocks.

*   **Access control (AC) –**
    ![](img/c43eb4712a07c03b90ecb378586e5025.png)

    **优先级位**和**预留位**有助于实现优先级。优先级位=保留位= 3。例如:-服务器被赋予优先级= 7，客户端被赋予优先级= 0。

    **令牌位**用于指示令牌帧的存在。如果令牌位= 1–>令牌帧，如果令牌位= 0–>不是令牌帧。

    **监控位**有助于解决孤立包问题。它被循环冗余校验覆盖，因为监视器是强大的机器，当修改监视器位时可以重新计算循环冗余校验。如果监视器位= 1–>已被监视器标记，并且如果监视器位= 0–>尚未被监视器标记。

*   **帧控制(FC)–**前 2 位表示帧是否包含数据或控制信息。在控制帧中，该字节指定控制信息的类型。
    ![](img/b05de91c3048342ccf11142ecdac17a4.png)

*   **Destination address (DA) and Source address (SA) –** consist of two 6-byte fields which is used to indicate MAC address of source and destination.
*   **Data –** Data length can vary from 0 to maximum token holding time (THT) according to token reservation strategy adopted. Token ring imposes no lower bound on size of data i.e. an advantage over Ethernet.
*   **Cyclic redundancy check (CRC) –** 32 bit CRC which is used to check for errors in the frame, i.e., whether the frame is corrupted or not. If the frame is corrupted, then its discarded.
*   **End delimiter (ED) –** It is used to mark the end of frame. In Ethernet, length field is used for this purpose. It also contains bits to indicate a damaged frame and identify the frame that is the last in a logical sequence.
*   **帧状态(FS)–**是终止数据帧的 1 字节字段。
    ![](img/e0b884f1d55741ae0ba5b23ed67792cd.png)
    由于循环冗余校验不覆盖文件系统字节，因此它利用了 2 份循环冗余校验位作为错误检测机制(100%冗余)，因此目的地在修改循环冗余校验位时不必重新计算循环冗余校验。