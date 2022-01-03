# 传统无线移动通信

> 原文:[https://www . geesforgeks . org/繁体-无线-移动-通信/](https://www.geeksforgeeks.org/traditional-wireless-mobile-communication/)

一个**蜂窝设备**今天已经不加思考地成为我们人类学手臂的延伸，赋予我们一种额外的通信手段，我们称之为无线通信或移动电信。

插入移动设备的几毫米大小的 SIM 卡形成了一种全球通用的网络技术，称为全球移动通信系统。我们倾向于把它看作是一个装饰性的手机和几个分散的蜂窝塔，这是符合我们日常需求的复杂架构的一部分。这个 GSM 系统可以分为三个主要子系统:*无线电子系统、网络子系统和操作子系统*。

让我们讨论一下这个分级系统的分解，以获得电信提供商如何为各地的移动用户提供言论自由的简要概述。

**1。无线电子系统–**
众所周知，移动通信以无线电波的形式在空中传播。无线电子系统包括两个主要部件。这些包括移动站和基站系统。

*   **移动台(MS)** 是用户设备，本质上是我们手机的硬件和 SIM 卡作为软件的一部分。SIM 卡是我们设备通信的灵魂，包含所有用户特定的数据，如序列号、卡类型、个人识别码、认证密钥、个人识别码解锁密钥、国际移动用户身份(IMSI)和订阅服务列表。移动台还存储无线通信所需的动态数据，例如位置信息和用于加密和解密的密钥。
*   The **Base station system (BSS)** is mainly responsible for maintaining the radio connection to the MS and performing coding and decoding of the voice communication. Now, the BSS is able to do this with the help of radio equipment such as antennas, amplifiers and signal processors, which we see as the cell tower, officially termed as the Base Transceiver Station (BTS). Each BTS acts within a radius or cell region and there are several BTSs and BSSs, each controlled by a Base Station Controller (BSC). The BSC is the prime manager of the BTS. It designates radio frequencies for communication and performs handover from one BTS to another within the BSS when the MS signal is weak.

    到目前为止，简化的通信路径可以表示为:

    ```
    MS -> BSS (BTS+BSC)
    ```

    **2。网络子系统–**
    通信系统的这一部分是另一个层次，处理从一个基站到另一个基站的切换。这使得我们所知的国内和国际漫游成为可能。该切换由移动交换中心或移动交换中心执行。MSC 通过它的数据库——归属位置寄存器(HLR)和访问者位置寄存器(VLR)知道用户位置。

    单个 HLR 数据库存储移动台的特定信息，如 IMSI 和预订的服务以及当前位置区域。移动台一离开当前位置区域，就会在 HLR 进行追踪和更新。这个更新的 HLR 被复制到负责移动台的移动台的 VLR。与每个用户的单个 HLR 不同，每个移动台内存在多个虚拟局域网，并且它保存其位置区域内移动台在 HLR 的所有信息。

    简化的通信路径现在可以表示为:

    ```
    MS -> BSS (BTS+BSC) -> MSC (HLR+VLR)
    ```

    **3。运营子系统–**
    GSM 的这一部分负责网络的平稳运行，涉及流量监控、用户管理、安全、计费和计费。它将所有信息保存在一个名为“设备身份注册”的现有移动设备统一数据库中。在被盗的情况下，通常是该数据库被更新，以将被盗设备列入黑名单，并阻止相关 SIM 卡上的通信。

    更新后的通信路径现在可以表示为:

    ```
     MS -> BSS (BTS+BSC) -> MSC (HLR+VLR)+EIR
    ```

    无线网络还通过网关移动交换中心与公共标准网络——公共交换电话网、综合业务数字网、公共分组数据网和 PLMN——进行交互，以完成全球移动通信系统网络。

    最终的通信路径现在可以表示为:

    ```
    MS -> BSS (BTS+BSC) -> MSC (HLR+VLR)+EIR -> Public Standard Network
    ```

    上述的全球移动通信系统是允许 2A 的传统移动通信后端技术。除非受到地理位置的限制，否则对话会不断地来回流动。