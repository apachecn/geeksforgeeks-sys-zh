# 在 MS SQL Server 中插入语句

> 原文:[https://www . geesforgeks . org/insert-语句-in-ms-sql-server/](https://www.geeksforgeeks.org/insert-statement-in-ms-sql-server/)

数据库包含许多按顺序存储数据的表。要将这些行相加，用户需要使用 insert 语句。

**语法:**

```
insert into table_name(column_list)
values(values_list) 

```

为了更好地理解，下面给出了一个例子。

**示例–**
名为 student 的表必须插入值。必须按照以下步骤进行:

```
insert into student (varchar2 name(20), int rollnumber, varchar2 course(50));
values('Riya', 111, 'Computer Science'); 

```

**输出–**

```
1 row(s) inserted 

```

要检查值是否实际插入，必须给出如下查询:

```
select *
from student; 

```

**输出–**

<figure class="table">

| 名字 | 辊号 | 课程 |
| --- | --- | --- |
| 里亚 | One hundred and eleven | 计算机科学 |

**插入多行:**
一个表在一个 insert 语句中最多可以存储 1000 行。如果用户想一次插入多行，必须编写以下语法。

**语法:**

```
insert into table_name(column_list)
values(value_list1)
values(values_list2)
.
.
.
.
values(values_listn) 

```

如果用户要插入 1000 多行，必须使用多个 insert 语句、大容量插入或派生表。

**示例–**
考虑一个表生。如果用户一次要输入 6 个学生的数据，必须按如下方式进行查询-

```
insert into student(int rollnumber, varchar2(30) name, varchar2(20) course);
values(111, 'Riya', 'CSE');
values(112, 'Apoorva', 'ECE');
values(113, 'Mina', 'Mech');
values(114, 'Rita', 'Biotechnology);
values(115, 'Veena', 'Chemical');
values(116, 'Deepa', 'EEE'); 

```

**输出–**

```
6 row(s) inserted 

```

要检查表中是否存在这些值，必须按如下方式进行查询:

```
select *
from student; 

```

**输出–**

<figure class="table">

| 辊号 | 名字 | 课程 |
| --- | --- | --- |
| One hundred and eleven | 里亚 | 中学生毕业考试 |
| One hundred and twelve | 它能提供 | 欧洲经济委员会 |
| One hundred and thirteen | 迈纳 | 技工 |
| One hundred and fourteen | 丽塔 | 生物技术 |
| One hundred and fifteen | 印度的七弦琴 | 化学的 |
| One hundred and sixteen | 迪帕 | 东方马脑脊髓炎 |

插入多行语句仅在 2008 年及以后才可用。

</figure>

</figure>