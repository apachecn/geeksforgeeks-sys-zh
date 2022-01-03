# 分布式数据库管理系统的缺点

> 原文:[https://www . geesforgeks . org/distributed-DBMS 的缺点/](https://www.geeksforgeeks.org/disadvantages-of-distributed-dbms/)

**分布式数据库系统**是一种数据库管理系统，其中数据库存在于不同的位置，并通过网络连接。分布式数据库中的每个站点都能够访问和处理本地数据以及远程数据。尽管分布式数据库管理系统能够进行有效的通信和数据共享，但它仍然存在以下各种缺点。

1.  **Complex nature :**
    Distributed Databases are a network of many computers present at different locations and they provide an outstanding level of performance, availability and of course reliability. Therefore, the nature of Distributed DBMS is comparatively more complex than a centralized DBMS. Complex software are required for Distributed DBMS . Also, It ensures no data replication, which adds even more complexity in its nature.
2.  **整体成本:**
    各种成本，如维护成本、采购成本、硬件成本、网络/通信成本、人工成本等加起来就是整体成本，比正常的 DBMS 成本更高。

*   **Security issues:**
    In a Distributed Database, along with maintaining no data redundancy, the security of data as well as network is a prime concern. A network can be easily attacked for data theft and misuse.*   **Integrity Control:**
    In a vast Distributed database system, maintaining data consistency is important. All changes made to data at one site must be reflected to all the sites. The communication and processing cost is high in Distributed DBMS in order to enforce the integrity of data.*   **Lacking Standards:**
    Although it provides effective communication and data sharing, still there are no standard rules and protocols to convert a centralized DBMS to a large Distributed DBMS. Lack of standards decreases the potential of Distributed DBMS.

    如果数据没有正确地分布在不同的站点，那么查询处理时间将会增加，对请求的响应将会变慢。