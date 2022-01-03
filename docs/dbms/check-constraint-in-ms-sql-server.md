# 检查微软 SQL 服务器中的约束

> 原文:[https://www . geesforgeks . org/check-constraint-in-ms-SQL-server/](https://www.geeksforgeeks.org/check-constraint-in-ms-sql-server/)

**检查约束:**
它与关系运算符一起用于检查值是否满足条件(布尔型)。如果满足条件，布尔表达式将设置为真，否则设置为假。检查约束没有特定的语法。它与创建表语法一起使用。

**语法:**

```
Create table Marks 
name varchar2(30), 
rollnumber number primary key, 
marks int check (marks<=75)
```

将创建一个名为“学生”的表，并附带标记不得大于 75 的条件。用户插入几个值，如下所示–

**表–**标记

| 名字 | 辊号 | 马克斯（英格兰人姓氏） |
| --- | --- | --- |
| 爱莎 | One hundred and eleven | Sixty |
| 奈纳 | One hundred and twelve | Seventy-three |

这些值是根据创建表语法中提到的条件插入的。用户尝试再插入一些值，但仍出现如下所示的错误

**示例-1:**

```
Insert into Student 
values('Maya', '117', '80')
```

**输出–**
该值大于 75 时会导致错误。

**示例-2:**

```
Insert into Student 
values('Maya' '111', '74')
```

**输出–**
显示错误。这是由于用于 rollnumber 的主键。主键禁止在表中使用重复项。

**空时检查约束:**

```
Insert into Student 
values('Riya', '112', 'NULL')
```

**输出–**
在 SQL 中，如果值未知，则使用空值。因此它被认为是假的。