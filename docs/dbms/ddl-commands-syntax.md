# DDL 命令&语法

> 原文:[https://www.geeksforgeeks.org/ddl-commands-syntax/](https://www.geeksforgeeks.org/ddl-commands-syntax/)

在本文中，我们将讨论 DDL 命令的概述，并理解 DDL 命令，如创建、更改、截断、删除。为了更好地理解，我们将借助一个示例来介绍每个命令语法。我们一个一个来讨论。

**概述:**
数据定义语言(DDL)是 SQL 的子集，也是 [DBMS(数据库管理系统)](https://www.geeksforgeeks.org/dbms/)的一部分。DDL 由 CREATE、ALTER、TRUNCATE 和 DROP 等命令组成。这些命令用于创建或修改 SQL 中的表。

**DDL 命令:**
在本节中，我们将介绍如下 DDL 命令。

1.  创造
2.  改变
3.  缩短
4.  滴

我们一个一个来讨论。

**命令-1 :**
**CREATE :**
此命令用于在 SQL 中创建新表。用户必须给出表名、列名及其数据类型等信息。

**语法–**

```
CREATE TABLE table_name
(
column_1 datatype,
column_2 datatype,
column_3 datatype,
....
);
```

**示例–**
我们需要创建一个表来存储特定学院的学生信息。创建语法如下。

```
CREATE TABLE Student_info
(
College_Id number(2),
College_name varchar(30),
Branch varchar(10)
);
```

**Command-2:**
**ALTER:**
此命令用于添加、删除或更改现有表中的列。用户需要知道现有的表名，并且可以轻松地执行添加、删除或修改任务。

**语法–**
向现有表添加列的语法。

```
ALTER TABLE table_name
ADD column_name datatype;
```

**示例–**
在我们的 Student_info 表中，我们想要为 CGPA 添加一个新列。语法如下。

```
ALTER TABLE Student_info
ADD CGPA number;
```

**Command-3:**
**TRUNCATE:**
此命令用于从表中删除所有行，但表的结构仍然存在。

**语法–**
删除现有表的语法。

```
TRUNCATE TABLE table_name;
```

**示例–**
学院管理局希望删除新批次所有学生的详细信息，但希望保留表格结构。他们可以使用的命令如下。

```
TRUNCATE TABLE Student_info;
```

**命令-4 :**
**DROP :**
此命令用于从数据库中移除现有表及其结构。

**语法–**
删除现有表的语法。

```
DROP TABLE table_name;
```

**示例–**
如果学院当局想要通过删除学生信息表来更改他们的数据库。

```
DROP TABLE Student_info;
```