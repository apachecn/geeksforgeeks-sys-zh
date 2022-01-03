# SQL 中的 order by 子句和 group by 子句之间的差异

> 原文:[https://www . geeksforgeeks . org/SQL 中按订单和按条款分组的区别/](https://www.geeksforgeeks.org/difference-between-order-by-and-group-by-clause-in-sql/)

**1。排序依据:**
排序依据关键字以升序或降序对结果集进行排序。默认情况下，此子句按升序对结果集进行排序。为了按降序对结果集进行排序，使用了 **DESC** 关键字。

**按语法排序–**

```
SELECT column_1, column_2, column_3...........
FROM Table_Name
ORDER BY column_1, column_2, column_3....... ASC|DESC;

Table_Name: Name of the table.
ASC: keyword for ascending order
DESC: keyword for descending order 
```

**2。分组依据:**
分组依据语句用于对具有相同值的行进行分组。它经常与聚合函数一起使用，例如:AVG()、最大值()、计数()、最小值()等。关于 group by 子句需要记住的一点是，元组是根据元组属性值之间的相似性进行分组的。

**按语法分组–**

```
SELECT function_Name(column_1), column_2
FROM Table_Name
WHERE condition
GROUP BY column_1, column_2
ORDER BY column_1, column_2; 
```

函数名:聚合函数的名称，例如:

```
SUM(), AVG(), COUNT() etc.

Table_Name: Name of the table. 
```

让我们看看按条款排序和按条款分组的区别:-

| S.NO | 分组依据 | 以...排序 |
| --- | --- | --- |
| 1. | Group by 语句用于对具有相同值的行进行分组。 | 而 Order by 语句以升序或降序对结果集进行排序。 |
| 2. | 它可能在 CREATE VIEW 语句中被允许。 | 而它在 CREATE VIEW 语句中不使用。 |
| 3. | 在 select 语句中，它总是用在 order by 关键字之前。 | 而在 select 语句中，它总是用在 group by 关键字之后。 |
| 4. | 属性不能在聚合函数下的 group by 语句中。 | 而按语句顺序，属性可以在聚合函数下。 |
| 5. | 在 group by 子句中，元组根据元组属性值之间的相似性进行分组。 | 而在 order by 子句中，结果集是根据升序或降序排序的。 |
| 6. | 分组依据控制元组(行)的表示。 | 而 order by 子句控制列的显示。 |