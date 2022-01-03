# SQL | UNION 运算符

> 原文:[https://www.geeksforgeeks.org/sql-union-operator/](https://www.geeksforgeeks.org/sql-union-operator/)

**UNION** 运算符可用于查找结果集或两个或多个表的组合。

**使用 UNION 的条款和条件:**

*   UNION 中使用的每个表必须具有相同的列数。
*   这些列必须具有相同的数据类型。
*   每个表中的列必须顺序相同。

**1。联合语法:**

```
SELECT columnnames FROM table1
UNION
SELECT columnnames FROM table2;

```

默认情况下，UNION 运算符只提供唯一的值。要查找重复值，请使用“联合所有”:

**2。联合所有语法:**

```
SELECT columnnames FROM table1
UNION ALL
SELECT columnnames FROM table2;

```

假设我们有两张表“极客 1”和“极客 2”；

```
Select * 
from Geeks1; 
```

<center>

| 身份证明 | 名字 | 薪水 | 城市 |
| --- | --- | --- | --- |
| One thousand two hundred and thirty-four | 库希 | Twenty-three thousand | 斋浦尔 |
| Two thousand three hundred and forty-five | 非常 | Twenty-four thousand | 德里 |
| Three thousand four hundred and fifty-six | 科马尔 | Twenty-four thousand five hundred | 无聊死了 |

</center>

```
Select * 
from Geeks2; 
```

<center>

| 身份证明 | 名字 | 薪水 | 城市 |
| --- | --- | --- | --- |
| Five thousand six hundred and seventy-eight | 伐柏拉姆牌登山靴橡胶底 | Twenty-six thousand | 我很自豪 |
| Six thousand seven hundred and eighty-nine | 马什 | Twenty-four thousand five hundred | 无聊死了 |
| Seven thousand eight hundred and ninety | Ashish | Twenty-five thousand six hundred | 德里 |

</center>

**SQL UNION 示例–**
以下 SQL 语句从“极客 1”和“极客 2”表中查找城市(仅唯一值):

**示例–**

```
SELECT City 
FROM Geeks1

UNION

SELECT City 
FROM Geeks2
ORDER BY City; 
```

**输出–**

<center>

| 城市 |
| --- |
| 德里 |
| 我很自豪 |
| 斋浦尔 |
| 无聊死了 |

</center>

**SQL UNION ALL 示例–**
下面的 SQL 语句从“极客 1”和“极客 2”表中查找城市(也是重复值):

**示例–**

```
SELECT City 
FROM Customers

UNION ALL

SELECT City 
FROM Suppliers
ORDER BY City; 
```

**输出–**

<center>

| 城市 |
| --- |
| 德里 |
| 德里 |
| 我很自豪 |
| 斋浦尔 |
| 无聊死了 |
| 无聊死了 |

</center>