# MySQL–开启删除级联约束

> 原文:[https://www . geesforgeks . org/MySQL-on-delete-cascade-constraint/](https://www.geeksforgeeks.org/mysql-on-delete-cascade-constraint/)

**ON DELETE CASCADE** 约束用于 MySQL 中，当父表中的行被删除时，会自动删除子表中的行。例如，当一名学生在在线学习平台注册时，该学生的所有详细信息都用其唯一的号码/id 记录下来。这些在线学习平台中的所有课程都有自己的代码、标题和名称。学生可以根据自己的意愿报名参加任何课程。

没有规定所有学生必须注册所有课程，或者他们必须在同一天参加课程。学生可以注册一门或多门课程。假设您从“学生”表中删除了一行，现在您还需要删除“注册”表中引用“学生”表中该行的所有行。为此，我们需要在删除级联。以下是解释“删除级联”引用操作如何工作的步骤。

**步骤 1:** 创建**学生**表

```
CREATE TABLE Student (
    sno INT PRIMARY KEY,
    sname VARCHAR(20),
    age INT

);
```

**第二步:**将行插入****学生**表格**

```
INSERT INTO Student(sno, sname,age)
 VALUES(1,'Ankit',17),
       (2,'Ramya',18),
       (3,'Ram',16);
```

****第三步:**执行**选择**查询，查看**学生**表中的数据。**

```
SELECT *
FROM Student;
```

****输出:****

<figure class="table">

| SnO | sname | 年龄 |
| --- | --- | --- |
| one | 鸭子！鸭子 | Seventeen |
| Two | 拉玛！拉玛 | Eighteen |
| three | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | Sixteen |

****步骤 4:** 创建**课程**表**

```
CREATE TABLE Course (
    cno INT PRIMARY KEY,
    cname VARCHAR(20)
);
```

****第 5 步:**将行插入**至**路线**表格中****

```
INSERT INTO Course(cno, cname)
 VALUES(101,'c'),
       (102,'c++'),
       (103,'DBMS');
```

****第 6 步:**执行**选择**查询，查看**课程**表中的数据。**

```
SELECT *
FROM Course;
```

****输出:****

<figure class="table">

| <u>cno</u> | cname |
| --- | --- |
| One hundred and one | c |
| One hundred and two | c++ |
| One hundred and three | 数据库管理系统 |

****第七步:**创建**报名**表**T5****

```
CREATE TABLE Enroll (
    sno INT,
    cno INT,
    jdate date,
    PRIMARY KEY(sno,cno),
    FOREIGN KEY(sno) 
        REFERENCES Student(sno)
        ON DELETE CASCADE
    FOREIGN KEY(cno) 
        REFERENCES Course(cno)
        ON DELETE CASCADE
);
```

****第 8 步:**在**报名**表格中插入行**

```
INSERT INTO Enroll(sno,cno,jdate)
 VALUES(1, 101, '5-jun-2021'),
       (1, 102, '5-jun-2021'),
       (2, 103, '6-jun-2021');
```

****第九步:**执行**选择**查询，查看**报名**表中的数据。**

```
SELECT *
FROM Enroll;
```

****输出:****

<figure class="table">

| 斯诺 | cno | jdate(犹太人) |
| --- | --- | --- |
| one | One hundred and one | 2021 年 6 月 5 日 |
| one | One hundred and two | 2021 年 6 月 5 日 |
| Two | One hundred and three | 2021 年 6 月 6 日 |

****第 10 步**:这里的父表是**学生**和**课程**，子表是**报名**。如果学生退出课程或课程从课程列表中删除，它也必然会影响子表。**

```
DELETE FROM Student
WHERE sname="Ramya";
```

****第 11 步:**执行****选择**查询查看数据。****

```
**Select * from Student;**
```

******输出:******

<figure class="table">

| 斯诺 | sname | 年龄 |
| --- | --- | --- |
| one | 鸭子！鸭子 | Seventeen |
| three | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | Sixteen |

```
**Select * from Enroll;**
```

******输出:******

<figure class="table">

| 斯诺 | cno | jdate(犹太人) |
| --- | --- | --- |
| one | One hundred and one | 2021 年 6 月 5 日 |
| one | One hundred and two | 2021 年 6 月 5 日 |

****当您删除父表中 sno=2 的内容时，它也会自动从子表中删除 sno=2 的详细信息。同样，如果从“课程”表中删除一门课程，它会自动删除子表“注册”中该课程的行。这是因为指定了 DELETE CASCADE 上的外键约束。****

</figure>

</figure>

</figure>

</figure>

</figure>