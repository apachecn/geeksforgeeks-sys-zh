# SQL 中 Where 子句和 Having 子句的区别

> 原文:[https://www . geesforgeks . org/where-and-having-in-SQL 子句的区别/](https://www.geeksforgeeks.org/difference-between-where-and-having-clause-in-sql/)

**1。WHERE 子句:**
WHERE 子句用于从表中筛选记录，或者在连接多个表时使用。只有满足 WHERE 子句中指定条件的记录才会被提取。它可以与 SELECT、UPDATE、DELETE 语句一起使用。

让我们考虑下表“学生”

```
Roll_no       S_Name      Age

1                a             17

2                b             20

3                c             21

4                d             18

5                e             20

6                f             17

7                g             21

8                h             17 
```

考虑查询:

```
SELECT S_Name, Age FROM Student 
WHERE Age >=18
```

上述查询的输出为:

```
 S_Name      Age

b             20             

c             21             

d             18             

e             20             

g             21             
```

**2。HAVING 子句:**
HAVING 子句用于根据 HAVING 子句中的给定条件从组中筛选记录。那些满足给定条件的组将出现在最终结果中。HAVING 子句只能与 SELECT 语句一起使用
。

让我们考虑上面提到的学生表，并在上面应用有子句:

```
SELECT Age, COUNT(Roll_No) AS No_of_Students 
FROM Student GROUP BY Age
HAVING COUNT(Roll_No) > 1 
```

上述查询的输出为:

```
Age     No_of_Students

17              3

20              2

21              1 
```

**SQL 中 Where 子句和 Having 子句的区别:**

<figure class="table">

| 不，先生。 | WHERE 子句 | 拥有条款 |
| --- | --- | --- |
| 1. | WHERE 子句用于根据指定的条件从表中筛选记录。 | HAVING 子句用于根据指定的条件从组中筛选记录。 |
| 2. | WHERE 子句可以不带 GROUP BY 子句使用 | 没有分组依据子句，不能使用 HAVING 子句 |
| 3. | WHERE 子句在行操作中实现 | HAVING 子句在列操作中实现 |
| 4. | WHERE 子句不能包含聚合函数 | HAVING 子句可以包含聚合函数 |
| 5. | WHERE 子句可以与 SELECT、UPDATE、DELETE 语句一起使用。 | HAVING 子句只能与 SELECT 语句一起使用。 |
| 6. | WHERE 子句用在 GROUP BY 子句之前 | HAVING 子句用在 GROUP BY 子句之后 |
| 7. | WHERE 子句与诸如 UPPER、LOWER 等单行函数一起使用。 | HAVING 子句与 SUM、COUNT 等多行函数一起使用。 |

</figure>