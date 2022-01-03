# 距离矢量路由和链路状态路由的区别

> 原文:[https://www . geesforgeks . org/距离矢量路由和链路状态路由之差/](https://www.geeksforgeeks.org/difference-between-distance-vector-routing-and-link-state-routing/)

先决条件–[路由算法分类](https://www.geeksforgeeks.org/computer-network-classification-routing-algorithms/)

[**距离矢量路由**](https://www.geeksforgeeks.org/computer-network-routing-protocols-set-1-distance-vector-routing/)**–**

*   这是一种动态路由算法，其中每台路由器计算自身与每个可能目的地(即其近邻)之间的距离。
*   路由器将整个网络的知识分享给邻居，并根据邻居更新表格。
*   与邻居的信息共享定期进行。
*   它利用**贝尔曼-福特算法**制作路由表。
*   **问题–**计数到无穷大的问题，可以通过拆分视界来解决。
    **—**好消息传得快，坏消息传得慢。
    **–**持续的循环问题，即循环将永远存在。

[**链路状态路由**](https://practice.geeksforgeeks.org/problems/what-is-link-state-routing-protocol)**–**

*   这是一种动态路由算法，其中每台路由器都与网络中的每台其他路由器共享其邻居的知识。
*   路由器只通过泛洪向所有路由器发送其邻居的信息。
*   信息共享只有在发生变化时才会发生。
*   它利用**迪克斯特拉算法**制作路由表。
*   **Problems –** Heavy traffic due to flooding of packets. 
    **–** Flooding can result in infinite looping which can be solved by using the **Time to live (TTL)** field. 

    *距离矢量路由和链路状态路由的比较:*

![](img/c874fe2237255a246bb27b36b51b290b.png)