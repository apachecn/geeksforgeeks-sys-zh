# SQL 中 ALTER 和 UPDATE 命令的区别

> 原文:[https://www . geesforgeks . org/alter-and-update-command-in-SQL/](https://www.geeksforgeeks.org/difference-between-alter-and-update-command-in-sql/)之间的差异

**1。更改命令:**

ALTER SQL 命令是一个 DDL(数据定义语言)语句。ALTER 用于更新数据库中表的结构(如添加、删除、修改数据库中表的属性)。

**语法:**

```
// add a column to the existing table

ALTER TABLE tableName

ADD columnName columnDefinition;

// drop a column from the existing table

ALTER TABLE tableName

DROP COLUMN columnName;

// rename a column in the existing table

ALTER TABLE tableName

RENAME COLUMN olderName TO newName;

// modify the datatype of an already existing column in the table

ALTER TABLE table_name

ALTER COLUMN column_name column_type;

```

**2。更新命令:**

更新命令是一个数据操作语言语句。它用于操作任何现有列的数据。但是不能被改变表的定义。

**语法:**

```
// table name that has to update

UPDATE tableName

// which columns have to update

SET column1 = value1, column2 = value2, ...,columnN=valueN.

// which row you have to update

WHERE condition

```

注意:如果没有 WHERE 子句，表中的所有记录都将被更新。

**SQL 中 ALTER 和 UPDATE 命令的区别:**

<figure class="table">

| SR.NO | ALTER 命令 | 更新命令 |
| --- | --- | --- |
| one | 改变命令是数据定义语言。 | 更新命令是一种数据操作语言。 |
| Two | Alter 命令将在结构级别而不是数据级别执行操作。 | 更新命令将在数据级别执行。 |
| three | ALTER Command 用于添加、删除、修改数据库中关系(表)的属性。 | 更新命令用于更新数据库中的现有记录。 |
| four | 默认情况下，ALTER 命令将所有元组的值初始化为空。 | 更新命令将命令中指定的值设置为元组。 |
| five | 该命令对表结构进行更改。 | 该命令对表中的数据进行更改。 |
| six | 示例:表结构、表名、服务点、函数等。 | 示例:在行或列等中更改表中的数据。 |

</figure>