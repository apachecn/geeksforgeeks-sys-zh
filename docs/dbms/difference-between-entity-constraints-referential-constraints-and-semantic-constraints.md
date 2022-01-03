# 实体约束、参照约束和语义约束的区别

> 原文:[https://www . geeksforgeeks . org/区别-实体-约束-引用-约束-和-语义-约束/](https://www.geeksforgeeks.org/difference-between-entity-constraints-referential-constraints-and-semantic-constraints/)

关系[数据库](https://www.geeksforgeeks.org/what-is-database/)中的数据以表格的形式存储。表格使数据看起来有条理。然而在某些情况下，我们在处理数据时可能会遇到问题，比如重复。我们可能希望对数据实施规则，以避免此类技术问题。这些规则被称为约束。约束可以定义为必须对数据强制执行以避免错误的规则。约束有三种:实体约束、指称约束和语义约束。下面列出了这三种约束之间的差异:

**1。实体约束:**
这些约束在一个表中给出。实体约束是主键、外键和唯一的。

**示例:**

```
create table student (rollnumber int primary key, name varchar2(30), course varchar2(10));
Insert into student values(111, 'ABC', 'Chemical');
Insert into student values(112, 'JJP', 'Mech');

```

| 辊号 | 名字 | 课程 |
| One hundred and eleven | 字母表 | 化学的 |
| One hundred and twelve | JJP | 技工 |

这些值被插入到表中。假设插入了下面给出的值:

```
Insert into student values(111, 'MAB', 'EEE');

```

它给出了一个错误，因为滚动号是一个防止重复的主键约束。这些约束确保保持表中的唯一性，以避免重复。

**2。引用约束:**
这些约束用于引用其他表来对数据强制条件。广泛使用的引用约束是外键。

**示例:**

```
create table marks (rollnumber int, name varchar2(30), course varchar2(30)
references student, marks int);

```

创建表格时有一个限制，即分数应奖励给那些只学习学生表格中所列课程的学生。如果用户试图输入一个不存在的值，它会返回一个错误。

**3。语义约束:**
数据类型是表中实施的语义约束。数据类型有助于数据根据其类型进行隔离。

**例:**
一个名字是不同字母的组合。我们可以将 name 列放在 char 数据类型中，但是 char 不满足条件，因此 varchar 最好用于 name。

```
name varchar2(30);

```

**实体约束、参照约束和语义约束的区别:**

<center>

| 特征 | 实体约束 | 参考约束 | 语义约束 |
| **定义** | 实体约束是在表中提出的。 | 引用约束由多个表强制实施。 | 语义约束是对特定属性的值实施的。 |
| **种类** | 实体约束为:唯一、主键、空。 | 引用约束是外键。 | 语义约束是数据类型。 |
| **描述** | 这些约束用于强制表中的唯一性(而空用于不定义任何值) | 这些约束用于引用另一个表来分析数据。 | 这些约束用于根据类别划分一组特定值。 |
| **功能** | 这些约束确保数据库中没有重复。 | 这些约束确保了数据库的一致性。 | 这些约束确保值被相应地分类，以避免混淆。 |
| **语法** | 主键:
创建表(第 1 列数据类型 1 主键…) | 外键:
创建表(列 1 数据类型 1 引用表名…) | 第 1 列 varchar2(30) |
| **示例** | 没有两个学生可以被指定同一个学号。 | Rollnumber 指的是标记表。 | 名称被分配给精度为 50 的 varchar2。 |

</center>