# SQL 中的横向关键字

> 原文:[https://www.geeksforgeeks.org/lateral-keyword-in-sql/](https://www.geeksforgeeks.org/lateral-keyword-in-sql/)

横向关键字表示两个或多个表之间的横向连接。它将外部查询的输出与底层横向子查询的输出连接起来。这就像是 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的 for-each 循环，子查询遍历相关表的每一行，计算每一行的子查询。

然后，内部子查询返回的输出行被添加到与外部查询的连接结果中。如果没有横向，每个子查询的计算将相互独立，并且不能引用外部查询中引用的表中的项。

**横向连接的语法:**
横向连接由内部子查询前面的关键字横向表示，如下所示:

```
SELECT <Column Name>
FROM <Reference Table Name>
LATERAL <Inner Subquery> 
```

**例:**
假设我们要找到一个班成绩最高的前 3 名学生。这个查询很简单，如下所示:

```
SELECT studId, marks 
FROM student 
ORDER BY marks DESC FETCH FIRST 3 ROWS ONLY 
```

现在假设每个班级有 n 个部分，我们需要找到分数最高的前 3 名学生。现在，我们需要连接区域表来获得结果，并使用 Rank()函数找到前 3 名学生。查询如下:

```
SELECT secId, studId, marks 
FROM ( SELECT sec.secId, stud.studId, stud.marks, 
       RANK() OVER (PARTITION BY sec.secId ORDER BY marks DESC) rn 
       FROM student stud, section sec WHERE sec.secId = stud.secId )
WHERE rn <= 3 
```

这就是横向救援的地方。我们将使用第一个查询作为内部子查询，在该查询中，我们获取了分数最高的前 3 名学生。接下来，我们使用横向关键字将截面表与内部子查询连接起来。将对左侧表中的每一行计算横向右侧的内部查询。查询如下所示:

```
SELECT sec.secId, stud.studId, stud.marks 
FROM section sec,
LATERAL (SELECT studId, marks FROM student stud 
         WHERE sec.secId = stud.secId 
         ORDER BY marks DESC FETCH FIRST 3 ROWS ONLY) 
```

**为什么使用横向？**
简单来说，Lateral 提供了一种更简单、更干净的方法来返回多个列作为输出。虽然因为内部子查询必须为主查询的每一行运行，所以它使查询有点慢。横向关键字的一些重要应用是两个或多个表的聚合以及活动日志，其中日志记录可能需要大量临时数据。