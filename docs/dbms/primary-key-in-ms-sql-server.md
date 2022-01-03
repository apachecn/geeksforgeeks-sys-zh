# MS SQL Server 中的主键

> 原文:[https://www.geeksforgeeks.org/primary-key-in-ms-sql-server/](https://www.geeksforgeeks.org/primary-key-in-ms-sql-server/)

一个表有特定数量的列，每列有 n 行。有时，一列中可能有重复的行。例如，名为标识号的列有重复的行。为了避免行的重复，引入了键的概念。

密钥是可以唯一识别的一个属性或一组属性。有不同的键，如主键、外键、超级键和候选键。**主键**用于从单个列或一组列中识别唯一的行。

**基本语法–**

```
create table table name(
pk_column datatype primary key
....
);

```

**示例–**

```

create table student 
rollnumber number Primary key
name varchar2(50)
course varchar2(30)

```

创建表格并插入值–

<center>

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 |
| One hundred and sixteen | 玛雅人 | 公民的 |

</center>

在上表中，第 116 卷重复了两次。它违反了主键规则。因此，给出了一个错误。
主键在数据库操作中起着举足轻重的作用。无法想象没有主键的数据库。没有主键的数据库是乏味的工作。当表中不包含主键时，可能会出现许多问题。

**注意–**
一个表只能有一个主键。

非空约束必须与具有主键的列一起包含。在微软的情况下，系统会自动创建非空值。当主键添加到列中时，SQL Server 会自动创建唯一的聚集索引。