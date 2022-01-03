# SQL 和 HiveQL 的区别

> 原文:[https://www . geesforgeks . org/SQL 和-hiveql 之间的差异/](https://www.geeksforgeeks.org/difference-between-sql-and-hiveql/)

**1。[结构化查询语言(SQL)](https://www.geeksforgeeks.org/structured-query-language/) :**
SQL 是一种特定于领域的语言，用于编程，旨在管理关系数据库管理系统(也称为 RDBMS)中保存的数据。它在处理结构化数据(即包含实体和变量之间关系的数据)时也很有用。SQL 是用于在数据库中存储、操作和检索数据的标准语言。

**2。[Hive Query Language(Hive QL)](https://www.geeksforgeeks.org/hive-overview/):**
Hive QL 是 Hive 用来分析和处理元存储中结构化数据的查询语言。它非常类似于 SQL，并且高度可伸缩。它重用关系数据库世界中熟悉的概念，如表、行、列和模式，以方便学习。Hive 支持四种文件格式，即文本文件、序列文件、ORC 和 RC 文件(记录列文件)。

**SQL 和 HiveQL 的区别:**

<center>

| 根据 | 结构化查询语言 | 希维 SQL |
| --- | --- | --- |
| 表结构中的更新命令 | 更新，删除

插入， | 更新，删除

插入， |
| 经营 | 关系数据 | 数据结构 |
| 交易 | 支持 | 支持的有限支持 |
| 指数 | 支持 | 支持 |
| 数据类型 | 它总共包含五种数据类型，即整数、浮点、定点、文本和二进制字符串、时态 | 它总共包含 9 种数据类型，即布尔、整数、浮点、定点、文本和二进制字符串、时态、数组、映射、结构。 |
| 功能 | 数百种内置功能 | 数百种内置功能 |
| Mapreduce | 不支持 | 支持 |
| 表格中的多表插入 | 不支持 | 支持 |
| 创建表格…作为选择 | 不支持 | 支持 |
| 选择命令 | 支持 | 部分排序支持 SORT BY 子句，限制返回的行数 |
| 连接 | 支持 | 内部连接、外部连接、半连接、映射连接、交叉连接 |
| 子查询 | 支持 | 仅用于 FROM、WHERE 或 HAVING 子句中 |
| 视图 | 可以更新 | 只读，即不能更新 |

</center>