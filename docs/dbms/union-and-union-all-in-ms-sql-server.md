# MS SQL Server 中的并集和全并集

> 原文:[https://www . geesforgeks . org/union-and-union-all-in-ms-SQL-server/](https://www.geeksforgeeks.org/union-and-union-all-in-ms-sql-server/)

**1。联合:**
联合是指将两个或多个数据集合并成一个集合。在 SQL Server 中，联合用于使用 select 语句将两个查询组合成一个结果集。Union 提取查询中描述的所有行。

**语法–**

```
query1 UNION query2
```

在用于查询之前，Union 需要满足几个条件。其中一个条件是，要提取的行必须来自表中相同的列。

**示例–**

```
select name, rollnumber 
from student 
UNION 
select name, rollnumber 
from marks
```

<center>
**Table –** Student

| 名字 | 辊号 | 课程 |
| --- | --- | --- |
| 玛雅人 | One hundred and eleven | 中学生毕业考试 |
| 里亚 | One hundred and twelve | 技工 |

</center>

<center>
**Table –** Marks

| 名字 | 辊号 | 马克斯（英格兰人姓氏） |
| --- | --- | --- |
| 玛雅人 | One hundred and eleven | Eight point nine |
| 里亚 | One hundred and twelve | Seven point eight |

</center>

**输出–**

<center>

| 名字 | 辊号 | 名字 | 辊号 |
| --- | --- | --- | --- |
| 玛雅人 | One hundred and eleven | 玛雅人 | One hundred and eleven |
| 里亚 | One hundred and twelve | 里亚 | One hundred and twelve |

</center>

这里使用了两个不同的表来提取行，但是为提取指定的列对于这两个表都是相同的。如果正在使用不同的列，则会出现错误。对于两个查询，指定的数据类型也必须相同。

**2。联合所有:**
联合用于使用查询中指定的条件提取行，而联合所有用于从两个表的集合中提取所有行。

**语法–**

```
query1 UNION ALL query2
```

同样的条件也适用于联合所有。“联合”和“全部联合”之间的唯一区别是，“联合”提取查询中指定的行，而“全部联合”提取两个查询中包含重复(重复值)的所有行。