# MS SQL Server 中的唯一约束

> 原文:[https://www . geesforgeks . org/unique-constraint-in-ms-SQL-server/](https://www.geeksforgeeks.org/unique-constraint-in-ms-sql-server/)

一个表可能有行形式的重复数据。这可能会导致从查询中检索数据时出现故障。为了避免它们，使用了唯一的约束。唯一允许对一列或一组列进行唯一排序，这意味着用户不能在列中插入重复或重复的值，因为这会导致错误。创建表时，会在表中强制实施唯一约束。

**示例–**
如果用户想要创建一个学生表，并且想要强制执行唯一约束，可以按如下方式完成–

```
create table Student
(name varchar2(30), rollnumber int unique, age int)
```

**表–**学生

<center>

| 名字 | 辊号 | 年龄 |
| --- | --- | --- |
| 爱莎 | One hundred and eleven | 中学生毕业考试 |
| 皮亚 | One hundred and twelve | 技工 |

在上面创建的表中，rollnumber 被强制执行一个唯一的约束，因为每个学生被分配了不同的 rollnumber 以避免混淆。为了进一步理解，下面给出了一个例子–

```
insert into student 
values ('Maya', '111', 'CSE');
```

**输出:**
由于 111 已经分配给另一个学生，因此会出现错误。这样，唯一约束限制了表中重复项的使用。

**结果:**
违反唯一键约束' UQ _ _ 学生 __EBE41F7A3D93XXXX '。无法在对象“学生”中插入重复的键。
重复键值为(111)。
声明已经终止。

**注意–**
主键和唯一键具有相同的功能，即在一组列中强制唯一性，以避免重复。主键和唯一性的唯一区别是主键只能使用一次，而唯一性可以使用多次。

</center>