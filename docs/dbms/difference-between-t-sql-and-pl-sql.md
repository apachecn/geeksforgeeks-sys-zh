# T-SQL 和 PL-SQL 的区别

> 原文:[https://www . geesforgeks . org/t-SQL 和-pl-sql 之间的区别/](https://www.geeksforgeeks.org/difference-between-t-sql-and-pl-sql/)

**1。Transact-SQL(T-SQL):**
T-SQL 是 Transact 结构查询语言的缩写。它是微软的产品，是用来与关系数据库交互的 SQL 语言的扩展。它被认为在微软的 SQL 服务器上表现最好。T-SQL 语句用于对数据库执行事务。由于与 SQL 服务器实例的所有通信都是通过向服务器发送 TransacT-SQL 语句来完成的，因此 t-SQL 具有巨大的重要性。用户也可以使用 T-SQL 定义函数。

测试 SQL 函数的类型有:

*   **聚合**功能。
*   **排名**功能。有不同类型的排名函数。
*   **行集**功能。
*   **标量**功能。

这些增加使 T-SQL 符合图灵完备性测试的标准。因此，Transact-SQL 是一种编程语言。

**2。SQL 的程序语言(PL/SQL) :**
[PL/SQL](https://www.geeksforgeeks.org/plsql-introduction/) 代表 SQL 的程序语言。它是甲骨文公司对 SQL 的程序性扩展，也是对甲骨文关系数据库的程序性扩展。它的主要优点是它允许使用过程，过程类似于函数。PL/SQL 的主要亮点是它给了我们迭代、决策和更多特性的功能。PL/SQL 中最小的功能单元称为块。它可以处理异常(运行时错误)。

PL/SQL 是一种应用程序语言，通常用于构建、格式化和显示用户屏幕、网页和报告，而 SQL 则为这些应用程序提供数据。

**T-SQL 和 PL-SQL 的区别:**

<center>

| S.No | T-SQL | PL/SQL |
| --- | --- | --- |
| 1. | TL-SQL 的完整形式是事务结构查询语言。 | PL/SQL 的完整形式是过程语言结构查询语言。 |
| 2. | T-SQL 是微软开发的。 | PL-SQL 是由 Oracle 开发的。 |
| 3. | T-SQL 为程序员提供了更高程度的控制。 | 它是一种自然的编程语言，与 SQL 非常兼容，并提供更高的功能。 |
| 4. | T-SQL 在微软的 SQL 服务器上表现最好。 | PL-SQL 在使用 Oracle 数据库服务器时性能最佳。 |
| 5. | 借助于 T-SQL 中的批量插入语句，用户可以输入多行。 | 使用 PL/SQL 支持像函数重载、信息隐藏和数据封装这样的 OOPS 概念。 |
| 6. | 它更容易理解，也更容易使用。 | 它被认为比 T-SQL 更复杂，功能更强大。 |
| 7. | 在 T-SQL 中，必须使用 SELECT INTO 语句。 | 在 PL/SQL 中，将使用插入语句。 |
| 8. | 在 T-SQL 中，DELETE 和 UPDATE 语句都得到了改进，使得来自另一个表的数据可以在操作中使用，而无需使用子查询。 | 在 PL/SQL 中，子查询需要在操作中使用另一个表中的数据。 | 9. | 在 T-SQL 中，没有 AUTOCOMMIT 命令，事务在每个事务之后通过手动使用 COMMIT 命令来保存。 | 在 PL/SQL 中，自动提交可用于自动提交/保存事务。 |

</center>