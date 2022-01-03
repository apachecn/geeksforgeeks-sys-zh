# SDLC 中使用的衍生协议

> 原文:[https://www . geesforgeks . org/衍生-协议-in-use-SDLC/](https://www.geeksforgeeks.org/derivative-protocols-used-in-sdlc/)

尽管**高级数据链路控制(HDLC)** 、**同步数据链路控制(SDLC)** 的子集最初是在 HDLC 之前由 IBM 创建的。

SDLC 是第一个完全基于同步、面向比特操作的链路层协议。SDLC 基本上是 HDLC 的前身。SDLC 基本上执行各种功能，例如:

*   它用于通过链路传输数据或信息单元。
*   它还管理链接级流。
*   它还管理传输过程中可能出现的错误的错误恢复和纠错过程。

**SDLC 支持的物理链路:**
SDLC 高度支持的物理链路有多种类型，如下所示:

*   **数据通道–**
    这些通道用于在并行管理器中传输或传输位，因为这些通道连接的节点应该彼此非常靠近。

*   **SDLC link–**
    这是将远程节点连接在一起的最常见和最广泛使用的方法。*   **X.25 Interface –**
    This interface remote nodes might also get connected over packet-switched network with help of protocol known as QLLC Qualified logical link control (QLLC) simply to carry SDLC frames.

    **衍生协议:**
    有很多非常流行的协议，都是从 SDLC 协议衍生而来的。这些协议由许多标准机构标准化。

    下面给出了一些简单基于 SDLC 的重要衍生协议:

    1.  **Link Access Procedure, Balanced (LAPB) –**
        LAPB is used to implement [Data Link Layer (DLL)](https://www.geeksforgeeks.org/framing-in-data-link-layer/) as described and defined in X.25 protocol suite. LAPB is best and popular known protocol for its presence in X.25 protocol stack. It is reliable synchronous serial protocol basically used to manage packet framing among DTE () and DCE stations.

        It is bit-oriented protocol that is being derived from HDLC that is used to ensure that all of data frames are error-free and are in correct or right sequence. It shares same format of frames, types of frames, and functions of different fields similar to SDLC and HDLC. As the name suggests, LAPB is balanced protocol that usually operates in ABM (Asynchronous Balanced Mode).
    2.  **High-Level Data Link Control (HDLC) –**
        HDLC is basically standard that is being adopted by [International Standards Organizations (ISO)](https://www.geeksforgeeks.org/iso-full-form/). It is bit-oriented code-transparent SDLC protocol that is developed by ISO. HDLC and SDLC both share same format of frame. HDLC fields also provide functionality similar to those in SDLC.

        HDLC 通常提供两种服务，即面向连接和无连接。它通常支持三种不同类型的数据传输模式，即 NRM(正常响应模式)、ABM(异步平衡模式)和异步响应模式(ARM)。但是 is 不支持环路和集线器先行配置。思科路由器也使用它通过租用线路进行串行通信，作为点对点协议(PPP)的替代方式。

    3.  **Logical Link Control (LLC) –**
        LLC was basically developed by IEEE 802.2\. It is generally required to provide HDLC style services on LAN (Local Area Network). It is highly popular data link protocol for LANs. LLC is subset of HDLC. It uses Asynchronous Balanced Mode (ABM) subclass of HDLC. LLC usually provides flow control and ARQ (Automatic Repeat Request) error management techniques.

        LLC 基本上有三个版本，如下所示:

        *   ㈠。物理服务标题(PSH)
        *   ㈡。合格逻辑链路控制(QLLC)
        *   ㈢。增强型逻辑链路控制(ELLC)
    4.  **合格逻辑链路控制(QLLC)–**
        QLLC 是 IBM 定义的 DLL 协议，它只允许 SNA(系统网络体系结构)数据通过 X.25 网络传输。它还提供传输国民账户体系数据非常需要的数据链路控制能力。QLLC 和 X.25 一起取代了 SNA 协议中的 SDLC。QLLC 是有限责任公司的翻版。