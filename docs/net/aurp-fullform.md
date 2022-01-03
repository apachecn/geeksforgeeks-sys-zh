# AURP 全表

> 原文:[https://www.geeksforgeeks.org/aurp-fullform/](https://www.geeksforgeeks.org/aurp-fullform/)

AURP 代表基于更新的路由协议。它是[广域网](https://www.geeksforgeeks.org/wan-full-form/)的路由协议。它建议对 AppleTalk 路由协议进行一些改进。它允许通过外部网络系统在两个或多个本地互联网之间建立连接，从而创建广域网。

它由三个主要组成部分组成:

1.  Apple Dialogue Tunnel.
2.  Transmission of routing information among various routers.
3.  Network information provided by routers to nodes or other compatible routers.

**功能:**

*   Fully compatible with AppleTalk Phase 2.
*   It sends the routing table only once and updates it when it needs to be changed.
*   It is provided in the form of network hiding and device hiding.
*   Provide tunnel facilities through Internet Protocol (IP) or other networks.
*   The backup path can be used correctly by weighting the hop count and the label provided to the backup path, so as to facilitate navigation.

**优势:**

*   Routing traffic on the WAN is reduced because only updates are sent and Internet clusters are used.
*   As the number of hops is reduced, a large Internet can be created.
*   Number conflicts can be solved by using remapping technology of remote network numbers.
*   Internet storage requirements can be routed by means of Internet cluster technology.

**缺点:**

*   As the network hidden facilities are provided by AURP, the nodes on these hidden networks cannot access the Internet correctly through tunnels.
*   Since AppleTalk network numbers range from 1 to 65,279, there will be number conflicts between organizations.