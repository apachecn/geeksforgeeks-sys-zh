# 【Transbase 和 Vertica 之间的差异

> 原文:[https://www . geeksforgeeks . org/trans base-and-vertica 之间的差异/](https://www.geeksforgeeks.org/difference-between-transbase-and-vertica/)

**1。Transbase :**
它是由慕尼黑交易软件有限公司开发和维护的资源优化、高性能、普遍适用的关系数据库管理系统。它是一个关系数据库管理系统，支持 SQL 标准的所有重要功能。Transbase 的数据库可通过附加函数进行扩展，自定义数据类型也通过动态多线程技术提供查询的并行执行。

**2。Vertica :**
Vertica 是一个柱状关系型数据库管理系统，旨在处理现代分析工作负载并实现快速查询性能。其总部位于美国马萨诸塞州剑桥。它是一个独立于基础架构的平台，通过它支持在多个云平台(AWS、谷歌云、Azure)、内部和本地 Hadoop 节点上的部署。其分析平台社区版是免费提供的，但有一定的限制。

**Transbase 和 Vertica 的区别:**

<center>

| Transbase | 垂直的 |
| --- | --- |
| 它由交易软件有限公司开发，最初于 1987 年发布。 | 它由 Vertica / Micro Focus 开发，最初于 2005 年发布。 |
| FreeBSD、Linux、macOS、Solaris、Windows，都是 Transbase 的服务器、操作系统。 | Linux 是 Vertica 的服务器操作系统。 |
| Transbase 中缺少辅助数据库模型。 | 辅助数据库模型是文档存储。 |
| 它支持 C，C#，C++，Java，JavaScript，Kotlin，Objective-C，PHP，Python 都是编程语言。 | C++、Java、Perl、Python、R 都是支持编程的语言。 |
| ADO.NET、JDBC、ODBC、专有原生 API 是 Transbase 的 API 和其他访问方法。 | ADO.NET、JDBC、卡夫卡、ODBC、专有协议、RESTful HTTP、API 都是 API 等访问方式。 |
| 实现语言是 C 和 C++。 | 它没有任何实现语言。 |
| Transbase 的复制方法是主从复制。 | 复制方法是 Vertica 的主-主复制。 |
| Transbase 中缺少分区方法。 | 存在分片分区方法。 |

</center>