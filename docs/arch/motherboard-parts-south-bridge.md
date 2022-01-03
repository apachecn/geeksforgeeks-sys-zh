# 主板零件-南桥

> 原文:[https://www . geesforgeks . org/主板-零件-南桥/](https://www.geeksforgeeks.org/motherboard-parts-south-bridge/)

**主板**内置了很多部件，每个部件都有自己的功能。

在本文中，将讨论名为南桥的部分。

**南桥:**
主板有一个由南北桥两个芯片组成的逻辑芯片组。它被称为南桥，因为它位于主板的外围组件互连或 PCI 总线的南面。

与北桥不同，这款芯片没有直接连接到 CPU。北桥充当南桥和中央处理器之间的通信媒介。南桥通过中央处理器控制所有的输入输出活动。因此，它也被称为输入/输出控制器中枢，因为它充当所有输入/输出处理和功能的中枢。

**历史:**
南桥被 PCH 或平台控制器 Hub 架构取代。取而代之的是在 2008 年推出了具有众多功能的英特尔 5 芯片组。

**功能:**
南桥支持主板的各种组件，如:

1.  **Peripheral Component Interconnect (PCI) –** 
    South bridge supports the old and new versions of PCI bus as well. 
2.  **PATA and SATA –** 
    PATA and SATA are known to store and transfer chunks of data via CPU. These buses are responsible for connecting hard drives and this is only possible via South bridge. 
3.  **Clock –** 
    It provides a time quantum for each process and checks whether every process gets the time limit for execution or not. 
4.  **电源管理–**
    控制电源并在必要时使用，否则电源将被保存以备将来使用。

**优势:**T2】

*   许多输入和输出处理可以通过南桥同时控制，这是一个巨大的优势。

*   没有这个桥，输入输出控制是不可能的。

**劣势:**
南桥方面没有大的劣势。

随着技术的快速发展，主板也被许多新的元件所取代。根据一些消息来源，南北桥正在被一个名为 IHA 或英特尔中枢架构的新组件所取代，这将在后续文章中讨论。