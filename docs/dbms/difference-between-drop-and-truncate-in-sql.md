# SQL 中 DROP 和 TRUNCATE 的区别

> 原文:[https://www . geesforgeks . org/SQL 中删除和截断的区别/](https://www.geeksforgeeks.org/difference-between-drop-and-truncate-in-sql/)

先决条件–[在 SQL 中删除和截断](https://www.geeksforgeeks.org/sql-drop-truncate/)

**1。DROP :**
DROP 是一个 [DDL(数据定义语言)](https://www.geeksforgeeks.org/sql-ddl-dql-dml-dcl-tcl-commands/)命令，用于删除该表的表定义和索引、数据、约束、触发器等。就性能而言，DROP 命令执行起来很快，但比 TRUNCATE 慢，因为它会引起复杂性。与 DELETE 不同，我们不能在使用 DROP 命令后回滚数据。在 DROP 命令中，表空间从内存中释放出来，因为它会永久删除表及其所有内容。

**DROP 命令的语法–**

```
DROP TABLE table_name;
```

**2。TRUNCATE :**
TRUNCATE 是 [DDL(数据定义语言)](https://www.geeksforgeeks.org/sql-ddl-dql-dml-dcl-tcl-commands/)命令。它用于从表中删除所有元组。像 DROP 命令一样，TRUNCATE 命令也不包含 WHERE 子句。TRUNCATE 命令比 DROP 和 DELETE 命令都快。像 DROP 命令一样，我们也不能在使用这个命令后回滚数据。

**TRUNCATE 命令的语法–**

```
TRUNCATE TABLE table_name; 
```

让我们看看 SQL 中 DROP 和 TRUNCATE 命令的区别:-

| S.NO | 滴 | 缩短 |
| --- | --- | --- |
| 1. | DROP 命令用于删除表定义及其内容。 | 而 TRUNCATE 命令用于删除表中的所有行。 |
| 2. | 在 DROP 命令中，从内存中释放表空间。 | 而 TRUNCATE 命令不会从内存中释放表空间。 |
| 3. | DROP 是一个数据定义语言命令。 | 而 TRUNCATE 也是一个 DDL(数据定义语言)命令。 |
| 4. | 在 DROP 命令中，表的视图不存在。 | 在此命令中，表视图存在。 |
| 5. | 在 DROP 命令中，完整性约束将被删除。 | 在此命令中，完整性约束不会被删除。 |
| 6. | 在 DROP 命令中，不使用撤消空间。 | 在此命令中，使用了撤消空间，但小于删除空间。 |
| 7. | DROP 命令执行起来很快，但是会引起复杂的情况。 | 虽然这个命令比 DROP 快。 |