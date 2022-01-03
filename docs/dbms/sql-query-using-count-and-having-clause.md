# 使用 COUNT 和 HAVING 子句的 SQL 查询

> 原文:[https://www . geesforgeks . org/SQL-query-use-count-and-having-子句/](https://www.geeksforgeeks.org/sql-query-using-count-and-having-clause/)

考虑一个具有以下模式的 STUDENT 表:

```
STUDENT (Student_id, Student_Name, Address, Marks) 
```

Student _ id 是 STudio 表的主列。

让我们首先用 SQL 中的 create 命令创建表结构:

```
CREATE TABLE STUDENT 
(STUDENT_ID NUMBER (4), 
STUDENT_NAME VARCHAR2 (20), 
ADDRESS VARCHAR2 (20), 
MARKS NUMBER (3), 
PRIMARY KEY (STUDENT_ID));
```

现在，使用 SQL 中的插入命令将值插入到表中:

```
INSERT INTO STUDENT 
VALUES (100, ‘PUJA’, ’NOIDA’, 10); 

INSERT INTO STUDENT 
VALUES (101, ‘SUDO’, ’PUNE’, 30); 

INSERT INTO STUDENT 
VALUES (102, ‘BHALU’, ’NASHIK’, 40); 

INSERT INTO STUDENT 
VALUES (103, ‘CHETENA’, ’NOIDA’, 20); 

INSERT INTO STUDENT 
VALUES (104, ‘MOMO’, ’NOIDA’, 40);
```

现在显示学生表的内容:

```
SELECT * 
FROM STUDENT;
```

```
Student_id    Student_Name    Address    Marks
------------------------------------------------
100            PUJA            NOIDA      10
101            SUDO            PUNE       30
102            BHALU           NASHIK     40
103            CHETENA         NOIDA      20
104            MOMO            NOIDA      40

```

**查询-1:**
打印分数和分数超过 NOIDA 市学生平均分数的学生人数。

**解释:**
要获取 NOIDA 市学生的平均成绩，我们使用以下查询:

```
SELECT AVG(MARKS) 
FROM STUDENT 
WHERE ADDRESS =’NOIDA’ 
```

我们使用上面的子查询，使用 GROUP BY 和 HAVING 子句:

```
SELECT MARKS, COUNT (DISTINCT STUDENT_ID) 
FROM STUDENT 
GROUP BY MARKS 
HAVING MARKS > (SELECT AVG(MARKS) 
                   FROM STUDENT 
                   WHERE ADDRESS = ’NOIDA’ ); 
```

在上面的查询中，我们使用 GROUP BY Marks 表示它用相同的 MARKS 对行进行聚类，我们还使用 SELECT MARKS，COUNT(DISTINCT STUDENT_ID)，它打印每个聚类的 MARKS 和各个聚类的行数，即，

```
MARKS    COUNT
10           1
20           1
30           1
40           2 
```

之后我们使用 HAVING MARKS >(选择 AVG(MARKS)FROM STUDENT WHERE ADDRESS = ' NOIDA ')，它用于过滤结果，条件是分数必须大于 NOIDA 市学生的平均分数，即大于

```
(10+20+40) / 3 
= 23.3 
```

**输出:**

```
MARKS       COUNT (DISTINCT STUDENT_ID)
30             1
40             2 
```

**查询-2:**
显示名字第二个字母为 u 的学生的姓名和地址

**解释:**
为了匹配 STUDENT_NAME 字段的模式，我们使用了 LIKE 字符串比较运算符和两个保留字符%和 _。%替换任意数量的字符，' _ '替换单个任意字符。
这里，我们需要比较 STUDENT_NAME 的第二个字母，因此我们使用模式“_U%”。

```
SELECT Student_Name, Address 
FROM STUDENT 
WHERE STUDENT_NAME LIKE ‘_U%’ 
```

**输出:**

```
STUDENT_NAME  ADDRESS
PUJA            NOIDA
SUDO            PUNE 
```

**查询-3:**
打印获得最高分的学生的详细信息(如果获得最高分的学生不止一个，那么最高分将按照其姓名的字母顺序排列)。

**解释:**
要从 marks 字段获得最高分，我们使用 MAX 命令，即，

```
SELECT MAX(MARKS) 
FROM STUDENT; 
```

我们使用上面返回“40”的子查询，它将与 WHERE 命令一起使用。为了按照学生姓名字段的字母顺序进行排列，我们使用了 ORDER BY 子句，为了获得顶行，将使用 LIMIT 1。综合所有这些:

```
SELECT * 
FROM STUDENT 
WHERE MARKS = (SELECT MAX (MARKS) 
               FROM STUDENT) 
ORDER BY STUDENT_NAME LIMIT 1;  
```

**输出:**

```
Student_id    Student_Name    Address     Marks
102            BHALU            NASHIK     40 
```

**查询-4:**
将学号为 103 的学生姓名和地址分别改为 RITA 和德里。

**解释:**
要更改任何属性的值，我们将使用带有 SET 子句的 UPDATE 命令来指定它们的新值。

```
UPDATE STUDENT 
SET STUDENT_NAME = ’RITA’, ADDRESS=’DELHI’ 
WHERE STUDENT_ID=103 ; 
```

**输出:**

```
1 row updated 
```

为了看到我们将要使用的变化，

```
SELECT * 
FROM STUDENT; 
```

**输出:**

```
Student_id    Student_Name    Address      Marks
100            PUJA               NOIDA       10
101            SUDO               PUNE        30
102            BHALU              NASHIK      40
103            RITA               DELHI       20
104            MOMO               NOIDA       40 
```

**查询-5:**
从学生表中删除分数最低的细节。

**解释:**
要找到我们要用的最低分，

```
SELECT MIN(MARKS) 
FROM STUDENT; 
```

它将返回“10”作为最低分。

要删除行，我们将使用 delete 命令和 WHERE 命令来指定条件。

```
DELETE FROM STUDENT 
WHERE MARKS = (SELECT MIN(MARKS) 
               FROM STUDENT); 
```

**输出:**

```
1 row affected 
```

为了看到我们将要使用的变化，

```
SELECT * 
FROM STUDENT; 
```

**输出:**

```
Student_id    Student_Name    Address      Marks
101            SUDO               PUNE        30
102            BHALU              NASHIK      40
103            RITA               DELHI       20
104            MOMO               NOIDA       40 
```