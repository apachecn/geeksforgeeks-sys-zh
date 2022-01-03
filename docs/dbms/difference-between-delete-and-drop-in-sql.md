# SQL 中 DELETE 和 DROP 的区别

> 原文:[https://www . geesforgeks . org/delete-and-drop-in-SQL 之差/](https://www.geeksforgeeks.org/difference-between-delete-and-drop-in-sql/)

先决条件–[SQL 命令](https://www.geeksforgeeks.org/sql-ddl-dml-dcl-tcl-commands/)
**[【删除】](https://www.geeksforgeeks.org/sql-delete-statement/)** 是一个数据操作语言(DML)命令，用于从关系中移除部分或全部元组。如果 WHERE 子句与 DELETE 命令一起使用，它只删除那些满足 WHERE 子句条件的元组，但是如果 DELETE 语句中缺少 WHERE 子句，那么默认情况下，关系中存在的所有元组都会被删除。

DELETE 命令的**语法**:

```
DELETE FROM relation_name 
WHERE condition;
```

是一个数据定义语言(DDL)命令，它删除模式的命名元素，如关系、域或约束，您也可以使用 DROP 命令删除整个模式。

DROP 命令的**语法**:

```
DROP SCHEMA schema_name RESTRICT;
DROP Table table_name CASCADE;
```

**对比图:**

| 参数 | 删除 | 滴 |
| --- | --- | --- |
| 基础 | 它从表中移除部分或全部元组。 | 它从数据库中删除整个模式、表、域或约束。 |
| 语言 | 数据操作语言命令 | 数据定义语言命令。 |
| 条款 | WHERE 子句主要与 DELETE 命令一起使用。 | DROP 命令不需要子句。 |
| 反转 | DELETE 执行的操作可以回滚，因为它使用了缓冲区。 | DROP 执行的操作不能回滚，因为它直接作用于实际数据。 |
| 空间 | 即使使用 delete 删除表中的所有元组，表在内存中占用的空间也不会被释放 | 它从内存中释放表空间 |
| 主要问题 | 内存不足 | 内存碎片 |
| 参考地点 | 优秀的 | 足够的 |
| 灵活性 | 固定尺寸 | 调整大小是可能的 |