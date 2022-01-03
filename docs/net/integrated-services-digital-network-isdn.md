# 综合业务数字网络(ISDN)

> 原文:[https://www . geesforgeks . org/integrated-services-digital-network-isdn/](https://www.geeksforgeeks.org/integrated-services-digital-network-isdn/)

这些是一组通信标准，用于在公共交换电话网的传统电路上同时进行语音、视频、数据和其他网络服务的数字传输。在*综合业务数字网络(ISDN)* 之前，电话系统被视为传输语音的一种方式，一些特殊服务可用于数据。综合业务数字网的主要特点是它可以将语音和数据集成在同一条线路上，这在传统的电话系统中是无法实现的。

综合业务数字网是一种电路交换电话网络系统，但它也提供分组交换网络接入，允许语音和数据的数字传输。这可能会带来比模拟电话更好的语音或数据质量。它以 64 千比特/秒的增量为数据提供分组交换连接。它在上行和下行方向提供最大 128 千比特/秒的带宽。通过通道绑定实现了更高的数据速率。一般来说，三个或四个 BRIs(六到八个 64 千比特/秒信道)的 ISDN B 信道是绑定的。

在[现场视察模型](https://www.geeksforgeeks.org/layers-osi-model/)的背景下，综合业务数字网被用作数据链路和物理层的网络，但通常综合业务数字网仅限于使用 Q.931 和相关协议。1986 年引入的这些协议是一组信令协议，用于建立和断开电路交换连接，并为用户提供高级呼叫功能。ISDN 在单个桌面视频会议系统和群组视频会议系统之间同时提供语音、视频和文本传输。

**综合业务数字网接口:**
综合业务数字网接口如下:

1.  **Basic Rate Interface (BRI) –**
    There are two data-bearing channels (‘B’ channels) and one signaling channel (‘D’ channel) in BRI to initiate connections. The B channels operate at a maximum of 64 Kbps while the D channel operates at a maximum of 16 Kbps. The two channels are independent of each other. For example, one channel is used as a TCP/IP connection to a location while the other channel is used to send a fax to a remote location. In iSeries ISDN supports a basic rate interface (BRl).

    基本速率接口(BRl)指定了一个数字管道，由两个 64 Kbps 的 B 通道和一个 16 Kbps 的 D 通道组成。这相当于 144 Kbps 的速度。此外，BRl 服务本身需要 48 Kbps 的操作开销。因此，需要 192 Kbps 的数字管道。

2.  **主要费率接口(PRI)–**
    主要费率接口服务由一个 D 通道和 23 或 30 个 B 通道组成，具体取决于您所在的国家。iSeries 不支持 PRI。在通常的主速率接口(PRI)中，存在一个具有 23 个 B 通道和一个 64 Kbps D 通道的数字管道。23 个 64 Kbps 的 B 通道和一个 64 Kbps 的 D 通道等于 1.536 Mbps。PRI 服务也使用 8 Kbps 的开销。因此，PRI 需要 1.544 Mbps 的数字管道。
3.  **宽带-综合业务数字网络(B- ISDN)–**
    窄带综合业务数字网络被设计为在当前的通信基础设施上运行，该基础设施严重依赖于铜缆，然而 B-综合业务数字网络主要依赖于光纤的发展。根据 CCITT 的说法，B-ISDN 最好被描述为“一种需要传输信道能够支持高于主要速率的速率的服务”。

**ISDN 服务:**
ISDN 为用户提供完全一体化的数字服务。这些服务分为三类:承载服务、远程服务和补充服务。

1.  **承载服务–**
    承载网络提供用户之间的信息(语音、数据和视频)传输，而无需网络操纵该信息的内容。网络不需要处理信息，因此不改变内容。承载服务属于 OSI 模型的前三层。它们在综合业务数字网标准中有很好的定义。它们可以使用电路交换、分组交换、帧交换或小区交换网络来提供。
2.  **远程服务–**
    在这种情况下，网络可能会更改或处理数据内容。这些服务对应于现场视察模型的第 4-7 层。远程服务依赖于承载服务的设施，并且被设计成适应复杂的用户需求。用户不需要知道过程的细节。远程服务包括电话、电传、传真、可视图文、电传和电话会议。尽管综合业务数字网通过名称来定义这些服务，但它们还没有成为标准。
3.  **补充服务–**
    承载服务和远程服务的附加功能由补充服务提供。反向计费、呼叫等待和消息处理是补充服务的例子，这些都是今天电话公司所熟悉的服务。

**ISDN 原理:**
ISDN 基于 ITU-T(原 CCITT)定义的标准工作。电信标准化部门代表国际电信联盟(国际电联)协调电信标准，总部设在瑞士日内瓦。根据国际电联电信联盟的建议，综合业务数字网的各种原则是:

*   为了支持交换和非交换应用
*   支持语音和非语音应用
*   依赖 64 kbps 连接
*   网络中的智能
*   分层协议体系结构
*   多种配置