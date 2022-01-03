# 【DBMS 面试常见问题|第二集

> 原文:[https://www . geesforgeks . org/common-question-DBMS-interview-questions-set-2/](https://www.geeksforgeeks.org/commonly-asked-dbms-interview-questions-set-2/)

本文是[常见 DBMS 面试问题的延伸|集 1](https://www.geeksforgeeks.org/commonly-asked-dbms-interview-questions/) 。

**Q .有一个表只有一行完全重复。写一个查询找到重复行**

| **名称** | **段** |
| --- | --- |
| 字母表 | CS1 |
| bcd | CS2 |
| 字母表 | CS1 |

在上表中，我们可以使用下面的查询找到重复的行。

```
SELECT name, section FROM tbl
GROUP BY name, section
HAVING COUNT(*) > 1

```

**问:查询找到员工第二高的工资？**

```
SELECT max(salary) FROM EMPLOYEES WHERE salary IN
(SELECT salary FROM EMPLOYEEs MINUS SELECT max(salary)
FROM EMPLOYEES);
```

运筹学

```
SELECT max(salary) FROM EMPLOYEES WHERE 
salary <> (SELECT max(salary) FROM EMPLOYEES);
```

**问:考虑下面的员工表。以下查询的结果中有多少行？**

**工资 ID 部门名称**
【110000 EC】
【240000 EC】【330000 cs】
【440000 me】
【550000 me】
【66000000 me】
770000 cs

**以下查询结果有多少行？**

```
SELECT E.ID
FROM  Employee E
WHERE  EXISTS  (SELECT E2.salary
FROM Employee E2
WHERE E2.DeptName = 'CS'
AND   E.salary > E2.salary)
```

以下 5 行将是查询结果，因为 3000 是 CS 员工的最低工资，并且所有这些行都大于 30000。

2
4
5
6
7

**问:写一个更新 Emp 表的触发器，这样，如果 Dep 表中进行了更新，那么该部门所有员工的工资应该增加一定的数量(更新)**

假设表名是 Dept 和 Emp，触发器可以写成–

```
CREATE OR REPLACE TRIGGER update_trig
AFTER UPDATE ON Dept
FOR EACH ROW
DECLARE
CURSOR emp_cur IS SELECT * FROM Emp;
BEGIN
FOR i IN emp_cur LOOP
IF i.dept_no = :NEW.dept_no THEN
DBMS_OUTPUT.PUT_LINE(i.emp_no);  --  for printing those
UPDATE Emp                      -- emp number which are
SET sal = i.sal + 100           -- updated
WHERE emp_no = i.emp_no;
END IF;
END LOOP;
END;
```

**Q .有一个表格包含两栏学生和分数，你需要找到所有分数大于平均分数的学生，即高于平均分数的学生名单。**

```
SELECT student, marks 
FROM table
WHERE marks > SELECT AVG(marks) from table;
```

**问:使用子查询说出获得第三高分的学生。**

```
SELECT Emp1.Name
FROM Employee Emp1
WHERE 2 = (SELECT COUNT(DISTINCT(Emp2.Salary))
           FROM Employee Emp2
           WHERE Emp2.Salary > Emp1.Salary
          )
```

*逻辑-工资高于此人的人数将为 2。

**问:为什么我们不能将 WHERE 子句用于 HAVING 这样的聚合函数？**

SQL 中 having 和 where 子句的区别在于，where 子句不能与聚合一起使用，但是 having 子句可以。请注意:这不是一个预定义的规则，但总的来说，您会看到在大量的 SQL 查询中，我们在分组依据之前使用 WHERE，在分组依据之后使用 HAVING。

Where 子句充当前置过滤器，而 Having 子句充当后置过滤器。

where 子句适用于行的数据，而不是聚合数据。

让我们考虑下表“标记”。

学生课程分数

a C1 40
a C2 50
b C3 60
d C1 70
e C2 80

考虑一下这个查询

```
SELECT Student, sum(Score) AS total 
FROM Marks
```

这将逐行选择数据。having 子句处理聚合数据。

例如，以下查询的输出

```
SELECT Student, sum(score) AS total FROM Marks
```

学生总数
a 90
b 60
d 70
e 80

当我们在上面的查询中应用时，我们得到

```
SELECT Student, sum(score) AS total
FROM Marks having total > 70
```

学生总数
a 90
e 80

**问:主键和唯一键的区别，如果唯一键只允许一个空值，为什么要使用唯一键？**

主键:

*   一行中只有一个(元组)。
*   从不允许空值(仅键字段)。
*   唯一密钥标识符，不能为空，并且必须唯一。

唯一密钥:

*   一行中可以有多个唯一键。
*   唯一键可以有空值(只允许单个空值)。
*   它可以是候选键。
*   唯一键可以为空，也可以不唯一。

**问:物化视图和动态视图有什么区别？**

物化视图

*   基于磁盘，并根据查询定义定期更新。
*   物化表很少创建或更新，必须与其关联的基表同步。

动态视图

*   仅虚拟化，并在每次访问时运行查询定义。
*   每当用户请求特定视图时，可以创建动态视图。

**问:什么是嵌入式动态 SQL？**

静态或嵌入式 SQL

*   应用程序中的 SQL 语句在运行时不会改变，因此可以硬编码到应用程序中。

动态 SQL

*   运行时构造的 SQL 语句；例如，应用程序可以允许用户输入他们自己的查询。
*   动态 SQL 是一种编程技术，使您能够在运行时动态构建 SQL 语句。您可以通过使用动态 SQL 创建更通用、更灵活的应用程序，因为 SQL 语句的全文在编译时可能是未知的。

| **序列号** | **静态(嵌入式)SQL** | **动态(交互)SQL** |
| 1. | 在静态 SQL 中，如何访问数据库是在嵌入式 SQL 语句中预先确定的。 | 在动态 SQL 中，如何访问数据库在运行时决定。 |
| 2. | 更加快捷高效。 | 它不那么迅速和有效。 |
| 3. | SQL 语句在编译时编译。 | SQL 语句在运行时编译。 |
| 4. | 应用程序计划的解析、验证、优化和生成都是在编译时完成的。 | 应用程序计划的解析、验证、优化和生成都是在运行时完成的。 |
| 5. | 它通常用于数据均匀分布的情况。 | 它通常用于数据分布不均匀的情况。 |
| 6. | 不使用 EXECUTE IMMEDIATE、EXECUTE 和 PRECute 语句。 | 使用了 EXECUTE IMMEDIATE、EXECUTE 和 PRECute 语句。 |
| 7. | 它不太灵活。 | 它更灵活。 |

http://docs.oracle.com/cd/A87860_01/doc/appdev.817/a76939/adg09dyn.htm

**问:CHAR 和 VARCHAR 有什么区别？**

*   CHAR 和 VARCHAR 在存储和检索方面是不同的。
*   CHAR 列长度是固定的，而 VARCHAR 长度是可变的。
*   字符 CHAR 数据类型最多可以容纳 255 个字符，而 VARCHAR 最多可以容纳 4000 个字符。
*   CHAR 比 VARCHAR 快 50%。
*   CHAR 使用静态内存分配，而 VARCHAR 使用动态内存分配。

你可能还喜欢:

*   在数据库管理系统上练习[测验](https://www.geeksforgeeks.org/quiz-corner-gq/)
*   [最后一分钟笔记](https://www.geeksforgeeks.org/last-minute-notes-dbms/)–数据库管理系统
*   数据库管理系统[文章](https://www.geeksforgeeks.org/category/dbms/)

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。