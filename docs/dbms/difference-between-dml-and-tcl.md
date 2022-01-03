# DML 和 TCL 的区别

> 原文:[https://www . geesforgeks . org/difference-DML-and-TCL/](https://www.geeksforgeeks.org/difference-between-dml-and-tcl/)

先决条件–[DDL、DML、TCL 和 DCL](https://www.geeksforgeeks.org/sql-ddl-dml-tcl-dcl/)
**1。数据操作语言(DML) :**
DML 用于操作数据库中的数据。例如 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的插入、更新、删除指令。

**2。事务控制语言(TCL) :**
TCL 处理数据库中的事务。

**DML 和 TCL 的区别:**

<figure class="table">

| 南没有。 | 种类 | DoctorofModernLanguages 现代语言博士 | TCL 集团股份有限公司（TCL Corporation 的缩写） |
| --- | --- | --- | --- |
| 1. | 完全形式 | DML 代表数据操作语言。 | TCL 代表事务控制语言。 |
| 2. | 定义 | DML 代表数据操作语言，用于通过执行插入、更新和删除操作来操作数据库中的数据。 | 事务控制语言由处理数据库中事务的命令组成。
 |
| 3. | 分类 | 数据修改语言进一步分为程序性和非程序性数据修改语言。 | 事务控制语言没有任何进一步的分类。 |
| 4. | 展示了数据库管理系统功能 | 它具有易于维护(文件)的特点。 | 它表现出原子性的特征。 |
| 5. | 在交易中使用 | DML 不能用于数据库事务。 | TCL 用于处理数据库事务。 |
| 6. | 命令 | 在查询中，DML 语句通常写在 TCL 语句之前。 | TCL 语句通常写在查询中的 DML 语句之后。 |
| 7. | 日志文件的使用 | 它不使用日志文件。 | 它使用日志文件来记录所有事务。 |
| 8. | 命令 | DML 中常用的命令有:更新、插入、合并、选择、删除、调用、解释计划、锁定表。 | TCL 中常用的命令有:提交、回滚、保存点、设置事务。 |
| 9. | 处理人 | DML 由数据库管理系统体系结构的查询编译器和查询优化器处理。 | TCL 由事务管理器和恢复管理器处理。 |
| 10. | 锁 | 它使用锁进行并发控制。 | 它不使用锁。 |
| 11. | WHERE 子句 | 大多数 DML 语句都有 WHERE 子句来过滤它们。 | TCL 不需要 WHERE 子句。 |
| 12. | 数据访问路径 | DML 可以用来解释数据的访问路径。 | TCL 无法解释数据访问路径。 |
| 13. | 调用子程序 | 用于调用 PL/SQL 或 Java 子程序。 | 它不用于调用子程序。 |
| 14. | 合并操作 | 我们可以使用 DML 执行合并操作。 | TCL 无法执行合并操作。 |
| 15. | 引发 | 在 DML 语句之后触发触发器。 | TCL 不用于触发器。 |
| 16. | 例子 | 查找历史系所有讲师姓名的 SQL 查询示例:
从讲师中选择姓名

WHERE dept _ name = ' History '；
 | We will use commit command to save the table record permanently. Incase we want to update the name Jolly to sherlock and save it permanently, we would use the following, 
UPDATE STUDENT 
SET NAME = ‘Sherlock’ 
WHERE NAME = ‘Jolly’; COMMIT
回滚； |

</figure>