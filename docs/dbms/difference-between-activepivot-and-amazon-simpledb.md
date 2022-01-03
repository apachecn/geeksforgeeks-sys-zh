# 【ActivePivot 和亚马逊 SimpleDB 的区别

> 原文:[https://www . geeksforgeeks . org/区别-active pivot-和-amazon-simpledb/](https://www.geeksforgeeks.org/difference-between-activepivot-and-amazon-simpledb/)

**1。活动枢轴:**
活动枢轴是一个内存中的[数据库管理系统](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)，结合事务和分析处理来处理不断变化的数据的聚合。该数据库使用柱状存储架构以及字典压缩和 Java 对象的二进制表示。它是法国公司 ActiveViam 的核心产品之一——曾被称为四方 FS，成立于 2005 年。

**2。亚马逊简单数据库:**
这是一个由亚马逊托管的简单[数据库](https://www.geeksforgeeks.org/what-is-database/)服务，数据存储在亚马逊云中。亚马逊是一个实时运行结构化数据查询的网络服务。这个数据库是 Amazon.com 用二郎写的。它具有以下特点—高可用性和灵活性，几乎没有或根本没有管理负担。

**active pivot 和亚马逊 SimpleDB 的区别:**

<center>

| 没有。 | ActivePivot | 亚马逊简单数据库 |
| --- | --- | --- |
| 1. | 它是由 ActiveViam 开发的。 | 它是亚马逊在 2007 年开发的。 |
| 2. | 它是一个内存中的数据库管理系统，结合了跨国处理和分析处理来处理不断变化的数据聚合。 | 它由亚马逊托管简单的数据库服务，数据存储在亚马逊云中。 |
| 3. | 它不支持任何复制方法。 | 它支持复制方法。 |
| 4. | 它不能作为云服务使用。 | 它可以作为云服务使用。 |
| 5. | 它的主要数据库模型是面向对象的数据库管理系统。 | 它的主要数据库模型是键值存储。 |
| 6. | 它支持服务器端脚本和 Java 中的后处理器。 | 它不支持服务器端脚本。 |
| 7. | 在 ActivePivot 中，分区可以通过分片和水平分区来完成。 | 它不支持分区方法。 |
| 8. | 它支持带有多维表达式的 SQL 查询语言。 | 它不支持 SQL 查询语言。 |

</center>