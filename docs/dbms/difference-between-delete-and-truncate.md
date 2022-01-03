# 删除和截断的区别

> 原文:[https://www . geesforgeks . org/delete-and-truncate 之差/](https://www.geeksforgeeks.org/difference-between-delete-and-truncate/)

**1。DELETE :**
DELETE 是一个 [DML(数据操作语言)](https://www.geeksforgeeks.org/difference-between-ddl-and-dml-in-dbms/)命令，在我们指定要从表或关系中删除的行(元组)时使用。DELETE 命令可以包含一个 WHERE 子句。如果 **WHERE** 子句与 DELETE 命令一起使用，那么它只删除或删除那些满足条件的行(元组)，否则默认情况下，它从表中删除所有元组(行)。

**DELETE 命令语法:**

```
DELETE FROM TableName 
WHERE condition; 
```

**2。TRUNCATE :**
TRUNCATE 是一个 [DDL(数据定义语言)](https://www.geeksforgeeks.org/difference-between-ddl-and-dml-in-dbms/)命令，用于删除表中的所有行或元组。与 DELETE 命令不同，TRUNCATE 命令不包含 WHERE 子句。在 TRUNCATE 命令中，会记录每个已删除数据页的事务日志。与 DELETE 命令不同，TRUNCATE 命令速度很快。在使用 TRUNCATE 命令后，我们无法回滚数据。

**TRUNCATE 命令的语法:-**

```
TRUNCATE TABLE  TableName; 
```

让我们看看 DELETE 和 TRUNCATE 命令之间的区别:-

<figure class="table">

| S.NO | 删除 | 缩短 |
| --- | --- | --- |
| 1. | DELETE 命令用于删除指定的行(一行或多行)。 | 而该命令用于删除表中的所有行。 |
| 2. | 这是一个数据操作语言命令。 | 而它是一个数据定义语言命令。 |
| 3. | DELETE 命令中可能有 WHERE 子句，用于过滤记录。 | 而 TRUNCATE 命令中可能没有 WHERE 子句。 |
| 4. | 在 DELETE 命令中，一个元组在移除之前被锁定。 | 在此命令中，数据页在删除表数据之前被锁定。 |
| 5. | DELETE 语句一次删除一行，并在事务日志中为每个删除的行记录一个条目。 | TRUNCATE TABLE 通过解除分配用于存储表数据的数据页来删除数据，并且只在事务日志中记录页解除分配。 |
| 6. | 删除命令比截断命令慢。 | 而 TRUNCATE 命令比 DELETE 命令快。 |
| 7. | 要使用删除，您需要对该表拥有删除权限。 | 要对表使用 Truncate，我们至少需要对表的 ALTER 权限。 |
| 8. | 对表使用 DELETE 语句后，列的标识将保留该标识。 | 如果表包含标识列，列的标识将重置为其种子值。 |
| 9. | 删除可以用于索引视图。 | 截断不能用于索引视图。 |

</figure>