# 信息安全中的 Slammer 蠕虫

> 原文:[https://www . geesforgeks . org/slammer-worm in-information-security/](https://www.geeksforgeeks.org/slammer-worm-in-information-security/)

Slammer Worm 被称为蓝宝石、赫尔克恩等。这是 2003 年传播最快的蠕虫，有人称之为“沃霍尔蠕虫”。它是在 1 月 25 日发现的，但在 1 月 20 日发现了一些类似的痕迹。它产生了大量的网络数据包，导致服务器过载，降低了网络的流量。

该蠕虫不会将自己保存在任何内存中，也不会在系统中创建或修改文件。它只影响那些在系统上运行微软 SQL server 2000 或 MSDE 2000 的系统。如果在系统中静默安装了 MSDE 2000 或微软 SQL server 2000 等软件，该蠕虫会影响设备。这种蠕虫花了 15 分钟传播到世界各地，感染了 30 多万人和 5.8 万人。由于该蠕虫消耗的带宽，许多 DNS 服务器宕机并经历了大量数据包丢失。

**有趣的事实:**

*   It infected a larger percentage of computers within 10 minutes.
*   Almost all Windows systems are affected by the slammer worm.
*   This worm affects the private rental network, causing service interruption of financial institutions.

**这个病毒是谁创造的？这种病毒的历史是怎样的？**

它最初是由安全专家大卫·利奇菲尔德发现的。2002 年，微软发布了一个补丁，可以修复这个蠕虫。由于许多人没有尝试修复这个弱点，2003 年有 7.5 万台服务器被感染。许多自动取款机对消费者不起作用，损失越来越大。因此，在 2003 年 1 月 25 日，这种蠕虫病毒导致了全球互联网的减速。现在，许多人报告说，他们接到了 911 电话，也对许多被取消的航班负责。

**slammer 蠕虫的功能–**

*   This will generate a large number of network packets, which will overload the server. It later slowed down the internet connection.
*   It does affect any system, but it affects those systems with Microsoft SQL Server 2000 (that is; Run SQL Server 2000 Enterprise Edition and Standard Edition, SQL Server 2000 Evaluation Edition and SQL Server 2000 Developer Edition, SQL Server 2000 Personal Edition) or MSDE 2000.

**该蠕虫的影响–**

*   It will slow down the network connection speed, because it will generate a large number of network packets, which will overload the server.
*   It has the function of shielding the network.
*   It has the ability to slow down or block the server.
*   This worm will cause the e-mail service to fail.
*   5。 This worm can increase the traffic through UDP port 1434.
*   The worm will not save itself in any memory, nor will it create or modify files in the system.
*   Only those who are running Microsoft SQL Server 2000 on the system are affected.

**案例分析:**

有一个国家受到了蠕虫的影响。一些韩国人声称他们的整个基础设施遭到破坏，损失了数十亿韩元。像 SK 电信和 ISP KT Freetel 公司这样的一些公司也失去了互联网连接。这种事情发生在韩国是因为监狱蠕虫。

**这种蠕虫感染系统的方式–**

*   1。 It enters the computer memory.
*   2。 Then it loads some API functions to generate an Ip address and infect other machines.
*   3。 It began to send multiple packets containing the worm code, and caused the port to be attacked by DDOS.

**蠕虫的预防–**

*   The worm can be removed by restarting the infected system.
*   We should use some anti-virus software such as Mcafee, Symantec and Trend Micro with these cleaning tools to clean this kind of virus.