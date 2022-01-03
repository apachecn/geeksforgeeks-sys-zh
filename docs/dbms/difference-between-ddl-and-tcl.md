# DDL 和 TCL 的区别

> 原文:[https://www . geesforgeks . org/difference-DDL-and-TCL/](https://www.geeksforgeeks.org/difference-between-ddl-and-tcl/)

**先决条件–**[SQL 命令](https://www.geeksforgeeks.org/sql-ddl-dql-dml-dcl-tcl-commands/)

**1。[数据定义语言(DDL)](https://www.geeksforgeeks.org/ddl-full-form/) :**
数据定义语言顾名思义，就是用来定义数据库模式的。例如:创建表、改变表都是 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的一些 DDL 指令。

**2。[事务控制语言(TCL)](https://www.geeksforgeeks.org/tcl-full-form/) :**
事务控制语言顾名思义，包含那些用于管理数据库内事务的命令。

**DDL 和 TCL 的区别:**

<center>

| 没有。 | 数据定义语言 | TCL 集团股份有限公司（TCL Corporation 的缩写） |
| --- | --- | --- |
| 1. | 它代表数据定义语言。 | 它代表事务控制语言。 |
| 2. | 它用于定义数据结构或整体数据库模式。 | 它包含这些命令，用于管理数据库中的事务。 |
| 3. | 通过使用 DDL 命令，无法处理数据库事务。 | TCL 命令是用来处理数据库事务的。 |
| 4. | 文件可以通过 DDL 命令轻松维护。 | 它用重要的特性——原子性来管理不同的任务。 |
| 5. | 在编写任何查询时，通常在编写 TCL 语句之前编写 DDL 语句。 | 通常，TCL 语句写在 DDL 语句之前。 |
| 6. | DDL 不需要任何日志文件来维护数据库。 | 它使用日志文件来跟踪数据库中所有事务的记录。 |
| 7. | 一些常用的 DDL 命令:CREATE、ALTER、DROP。 | 一些常用的 TCL 命令:提交、回滚。 |

</center>