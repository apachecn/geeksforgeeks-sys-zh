# SQL 触发器|学生数据库

> 原文:[https://www.geeksforgeeks.org/sql-trigger-student-database/](https://www.geeksforgeeks.org/sql-trigger-student-database/)

**触发器:**触发器是数据库中的存储过程，每当数据库中发生特殊事件时，它都会自动调用。例如，当一行被插入到指定的表中或者当某些表列被更新时，可以调用触发器。

**语法:**

```
create trigger [trigger_name] 
[before | after]  
{insert | update | delete}  
on [table_name]  
[for each row]  
[trigger_body] 
```

**语法解释:**

1.  创建触发器[trigger_name]:用 trigger_name 创建或替换现有触发器。
2.  [前|后]:指定触发器将在何时执行。
3.  {插入|更新|删除}:这指定了 DML 操作。
4.  on [table_name]:指定与触发器关联的表的名称。
5.  [针对每一行]:这指定了行级触发器，即触发器将针对受影响的每一行执行。
6.  [trigger_body]:这提供了触发触发器时要执行的操作

**触发器的 BEFORE 和 AFTER:**
BEFORE 触发器在触发语句运行之前运行触发动作。
AFTER 触发器在触发语句运行后运行触发动作。

**例:**
给定学生成绩报告数据库，记录学生成绩评定。在这样的模式中，创建一个触发器，以便每当插入记录时，自动插入指定标记的总数和平均值。

在这里，由于触发器将在插入记录之前调用，所以可以使用 before 标记。

**假设数据库模式–**

```
mysql> desc Student; 
+-------+-------------+------+-----+---------+----------------+ 
| Field | Type        | Null | Key | Default | Extra          | 
+-------+-------------+------+-----+---------+----------------+ 
| tid   | int(4)      | NO   | PRI | NULL    | auto_increment | 
| name  | varchar(30) | YES  |     | NULL    |                | 
| subj1 | int(2)      | YES  |     | NULL    |                | 
| subj2 | int(2)      | YES  |     | NULL    |                | 
| subj3 | int(2)      | YES  |     | NULL    |                | 
| total | int(3)      | YES  |     | NULL    |                | 
| per   | int(3)      | YES  |     | NULL    |                |
+-------+-------------+------+-----+---------+----------------+ 
7 rows in set (0.00 sec)
```

问题语句的 SQL 触发器。

```
create trigger stud_marks 
before INSERT 
on 
Student 
for each row 
set Student.total = Student.subj1 + Student.subj2 + Student.subj3, Student.per = Student.total * 60 / 100;
```

上面的 SQL 语句将在学生数据库中创建一个触发器，每当输入主题标记时，在将该数据插入数据库之前，触发器将计算这两个值，并使用输入的值进行插入。即，

```
mysql> insert into Student values(0, "ABCDE", 20, 20, 20, 0, 0); 
Query OK, 1 row affected (0.09 sec) 

mysql> select * from Student; 
+-----+-------+-------+-------+-------+-------+------+ 
| tid | name  | subj1 | subj2 | subj3 | total | per  | 
+-----+-------+-------+-------+-------+-------+------+ 
| 100 | ABCDE |    20 |    20 |    20 |    60 |   36 | 
+-----+-------+-------+-------+-------+-------+------+ 
1 row in set (0.00 sec)
```

通过这种方式，可以在数据库中创建和执行触发器。