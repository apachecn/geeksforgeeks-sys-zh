# SQL 中 From 子句和 Where 子句的区别

> 原文:[https://www . geesforgeks . org/from-and-where-in-SQL 子句的区别/](https://www.geeksforgeeks.org/difference-between-from-and-where-clause-in-sql/)

**1。FROM 子句:**
用于选择要使用选择、更新或删除命令进行操作的数据集。它与 SQL 语句结合使用来操作源表中的数据集。我们可以在 FROM 子句中使用子查询从表中检索数据集。

**FROM 子句的语法:**

```
SELECT * 
FROM TABLE_NAME; 
```

**2。WHERE 子句:**
用于对选定的数据集或源数据应用任何条件。源数据可以是单个表，也可以是连接多个表的结果。它返回那些满足 WHERE 子句中提到的条件的数据集实例。可以使用各种比较或逻辑运算符来应用条件，如–
AND、or、IN、NOT IN、BETWEEN、等于、不等于等。

**WHERE 子句的语法:**

```
SELECT * FROM TABLE_NAME
WHERE (CONDITIONS); 
```

**示例:**
考虑一个表名 STUDENT

<center>

| S_NO。 | s_NAME | S_AGE | 部分 |
| --- | --- | --- | --- |
| one | 亚什 | Twenty | A |
| Two | Vishwash | Twenty-one | A |
| three | Vishesh | Nineteen | B |
| four | 希瓦姆 | Twenty-three | A |
| five | 瓦苏 | Twenty-one | B |
| six | Shrey | Twenty | C |

</center>

**问题:**
我们必须选择表 STUDENT 中年龄小于 22 岁且部分为 a 的那些实例

**查询:**

```
SELECT * 
FROM STUDENT 
WHERE S_AGE<22 AND S_SECTION='A'; 
```

**输出:**
FROM 子句选择应该在其上应用 WHERE 子句的表，WHERE 子句检查这两个条件，以找到满足它们的数据集实例。

<center>

| S_NO。 | s_NAME | S_AGE | 部分 |
| --- | --- | --- | --- |
| one | 亚什 | Twenty | A |
| Two | Vishwash | Twenty-one | A |

</center>

【FROM 子句和 WHERE 子句之间的差异:

<center>

| S_NO。 | FROM 子句 | WHERE 子句 |
| --- | --- | --- |
| 1. | 它用于选择需要进行操作的数据集。 | 它用于检查某些条件以过滤结果 |
| 2. | 我们在 FROM 子句中提供一些数据集作为输入。 | 在 WHERE 子句中，我们给出一些条件作为输入。 |
| 3. | FROM 子句选择数据集，将其提供给 WHERE 子句，以应用查询中给定的条件。 | WHERE 子句充当选择器，从 from 子句提供数据集中筛选所需的实例。 |
| 4. | FROM 子句是必需的，因为如果没有数据集，就不能执行任何操作。 | WHERE 是可选的，我们只在条件检查时使用它。 |

</center>