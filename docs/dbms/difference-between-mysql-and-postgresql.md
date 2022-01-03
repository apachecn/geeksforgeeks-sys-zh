# 【MySQL 和 PostgreSQL 的区别

> 原文:[https://www . geesforgeks . org/区别-MySQL-和-postgresql/](https://www.geeksforgeeks.org/difference-between-mysql-and-postgresql/)

数据库是以易于管理和更新的方式构建的信息集合。为了使这项任务变得更容易，已经创建了各种[数据库管理系统(DBMS)](https://www.geeksforgeeks.org/dbms/) 。这些包括 MySQL、PostgreSQL、MongoDB、Redis 等。

**1。** [**MySQL**](https://www.geeksforgeeks.org/mysql-common-mysql-queries/)
它是最著名的、开源的**关系数据库管理系统(RDMS)** 。该表中的数据存储在表中，这使得执行 CRUD 操作(创建、读取、更新和删除)变得容易。MySQL 的一些特性包括:

*   快速、简单、可靠。
*   可用于大型和小型应用。
*   提供高扩展性

**2。PostgreSQL:**
它是一个强大的开源**对象关系数据库系统**。由于其高稳定性，它以低维护工作量提供了良好的性能。PostgreSQL 是第一个实现**多版本并发控制(MVCC)** 特性的 DBMS。PostgreSQL 的一些亮点是:

*   支持大量语言。
*   它提供高级安全功能。
*   它有**地理标记**支持。

【MySQL 和 PostgreSQL 的区别:

<figure class="table">

| 没有 | 关系型数据库 | 一种数据库系统 |
| --- | --- | --- |
| 1. | 是最**流行的**数据库。 | 是最**高级的**数据库。 |
| --- | --- | --- |
| 2. | 这是一个基于关系的数据库管理系统。 | 这是一个基于对象的关系数据库管理系统 |
| 3. | 仅当与 InnoDB 和 NDB 集群引擎一起使用时，才是 ACID 投诉 | 这是 ACID 发自内心的抱怨。 |
| 4. | 实现语言为 **C/C++** 。 | 实现语言为 **C** 。 |
| 5. | 它不支持 CASCADE 选项。 | 支持 CASCADE 选项。 |
| 6. | 提供的 GUI 工具是 **MySQL 工作台** | 提供 **PgAdmin** |
| 7. | 它不支持部分索引、位图索引和表达式索引。 | 它支持所有这些 |
| 8. | 它不支持物化视图和表继承。 | PostgreSQL 提供了这两者。 |
| 9. | SQL 只支持**标准数据类型**。 | 它支持**高级数据类型**，如数组、hstore 和用户定义类型。 |
| 10. | SQL 提供**有限的 MVCC 支持**(在 InnoDB 中) | **全 MVCC** 支援。 |

</figure>