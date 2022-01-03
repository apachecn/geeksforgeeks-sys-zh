# 【MapR 平台与 Cloudera 平台的区别

> 原文:[https://www . geeksforgeeks . org/区别-mapr-platform-and-cloud era-platform/](https://www.geeksforgeeks.org/difference-between-mapr-platform-and-cloudera-platform/)

**1。Cloudera :**
Cloudera 成立于 2008 年，由包括谷歌、雅虎！、甲骨文和脸书。它基于开源的 Apache [Hadoop](https://www.geeksforgeeks.org/hadoop-an-introduction/) ，但增加了自己的[专有软件](https://www.geeksforgeeks.org/difference-between-open-source-software-and-proprietary-software/)。它提供免费和付费分发以及额外的功能和支持。Cloudera 的长期目标是成为企业数据中心，从而减少/消除对[数据仓库](https://www.geeksforgeeks.org/data-warehousing/)的需求。它支持 MapReduce 和纱。自从创建 Hadoop 以来，它已经存在了最长的时间。Cloudera Distribution Hadoop (CDH)能够向正在运行的 Hadoop 集群添加新服务，并支持多集群管理。

**2。MapR :**
MapR 由约翰·施罗德(John Schroeder，M.C. Srivas)于 2009 年创立。它是一个数据平台，可以从单个计算机集群访问多个数据源，包括[大数据](https://www.geeksforgeeks.org/what-is-big-data/)工作负载，如 Apache Hadoop 和 [Apache Spark](https://www.geeksforgeeks.org/components-of-apache-spark/) 、Hive 和 Drill 等，并且可以同时访问。它以速度、规模和可靠性执行分析和应用。思科、谷歌云平台、亚马逊 EMR 等大公司的 Hadoop 服务都使用 MapR Hadoop Distribution。MapR Hadoop 分发遵循分布式体系结构，用于在处理节点上存储元数据，因为它依赖于不同的文件系统，称为 MapR 文件系统或简称为 MapRFS，并且没有名称节点体系结构。

**Cloudera 和 MapR 的区别:**

<center>

| 没有。 | CLOUDERA | MAPR(地图) |
| 01. | Cloudera 成立于 2008 年，由包括谷歌、雅虎！、甲骨文和脸书。 | MapR 由约翰·施罗德·西瓦斯博士于 2009 年创立。 |
| 02. | 它基于开源的 Apache Hadoop，但增加了自己的专有软件。 | 它是一个数据平台，可以从单个计算机集群访问各种数据源，包括大数据工作负载，如 Apache Hadoop、Hive 和 Drive、Apache Spark，但它也远远不止于此。 |
| 03. | Cloudera 的管理工具是 Cloudera Manager。 | MapR 的管理工具是 MapR 控制系统。 |
| 04. | Cloudera 没有卷支持。 | MapR 支持卷。 |
| 05. | 对于灾难恢复和备份，它使用常规备份和灾难恢复(BDR)功能。 | 对于灾难恢复，它使用镜像功能。 |
| 06. | Cloudera 复制允许复制数据。 | MapR 复制允许复制数据和元数据。 |
| 07. | Cloudera 有集中的元数据架构。 | MapR 具有分布式元数据架构。 |
| 08. | cloudera 中的文件系统访问是 Hadoop 分布式文件系统(HDFS)和只读 NFS。 | MapR 中的文件系统访问是 Hadoop 分布式文件系统(HDFS)和读写 NFS (POSIX)。 |
| 09. | 它使用 Kerberos 写级身份验证。 | 它使用 Kerberos、本机写级身份验证。 |
| 10. | Cloudera 有三个版本，一个是免费的，另一个是长达 60 天的企业版和完整的企业版。 | 它完全有企业版。 |
| 11. | 它运行在 Hadoop 分布式文件系统(HDFS)上。 | MAPR 在 MapR 文件系统上运行。 |

</center>