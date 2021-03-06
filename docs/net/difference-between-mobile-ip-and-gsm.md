# 移动 IP 和 GSM 的区别

> 原文:[https://www . geesforgeks . org/mobile-IP 和-gsm 的区别/](https://www.geeksforgeeks.org/difference-between-mobile-ip-and-gsm/)

在讨论 GSM 和移动 IP 之间的共性之前，让我们先简单讨论一下。

**1。[移动 IP](https://www.geeksforgeeks.org/mobile-internet-protocol-or-mobile-ip/) :**
移动 IP 是 IP 协议的延伸。它允许笔记本电脑(或智能手机)连接到互联网。

**移动 IP 的服务:**

*   支持多种不同的操作模式。
*   代理和移动节点发现彼此的多种方式。
*   使用单个或多个 COAs。
*   多种封装形式。

**工序:**

*   **代理发现:**它向移动节点通告本地或外地代理使用其服务的协议。
*   **向本地代理注册:**它定义了移动节点向本地代理注册 COAs 时使用的协议。
*   **数据报的间接路由:**它定义了数据报从归属代理传输到移动节点的方式。

**2。 [GSM](https://www.geeksforgeeks.org/how-gsm-works/) :**
GSM 代表 **G** 全球 **S** 系统，用于 **M** 车载通信。
是全球广泛使用的移动通信系统。它使用时分多址(TDMA)通过具有两个不同客户端数据流的信道发送数字化和简化的数据，每个数据流都在自己特定的时隙内。

两者的主要区别是:
GSM 是你用来访问数据的无线电网络。
移动 IP 用于将您的 IP 数据从您的设备传输到一个集中的出口点，在此进入公共互联网。

**移动 IP 与 GSM 的区别:**

<center>

| GSM 元件 | 全球移动通信系统元素评述 | 移动 IP 元素 | 家庭系统 | 移动用户的永久电话号码所属的网络。 | 家庭网络 |
| 网关移动交换中心或简单的家庭移动交换中心，家庭位置寄存器(HLR)。 | 归属 MSC:获取移动用户可路由地址的联系点。
HLR:家庭系统中的数据库，包含永久电话号码、个人资料信息、移动用户的当前位置、订阅信息。 | 本地代理 |
| 拜访系统 | 移动用户当前所在的家庭系统以外的网络。 | 受访网络 |
| 访客移动服务交换中心，访客位置寄存器(VLR) | 被访问的 MSC:负责在与 MSC 相关联的小区中建立去往/来自移动节点的呼叫。
VLR:拜访系统中的临时数据库条目，包含每个拜访移动用户的订阅信息。 | 外国代理人 |
| 移动台漫游号码(MSRN)或简单的漫游号码 | 归属移动交换中心和被访问移动交换中心之间的电话单元段的可路由地址，对移动台和通信方都不可见。 | 转交地址 |

</center>