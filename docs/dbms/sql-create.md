# SQL | CREATE

> 原文:[https://www.geeksforgeeks.org/sql-create/](https://www.geeksforgeeks.org/sql-create/)

SQL 中有两个 CREATE 语句可用:

1.  创建数据库
2.  创建表格

**创建数据库**

一个**数据库**被定义为一组结构化的数据。因此，在 SQL 中，以良好的结构方式存储数据的第一步是创建一个数据库。 **CREATE DATABASE** 语句用于在 SQL 中创建新的数据库。

**语法**:

```
CREATE DATABASE database_name;

database_name: name of the database.

```

**示例查询:**
该查询将在 SQL 中创建新的数据库，并将该数据库命名为 *my_database* 。

```
CREATE DATABASE my_database;

```

**创建表格**

我们已经在上面学习了创建数据库。现在为了存储数据，我们需要一个表来实现。CREATE TABLE 语句用于在 SQL 中创建一个表。我们知道表格由行和列组成。因此，在创建表时，我们必须向 SQL 提供关于列名、要存储在列中的数据类型、数据大小等所有信息。现在让我们深入了解如何使用 CREATE TABLE 语句在 SQL 中创建表的细节。

**语法**:

```
CREATE TABLE table_name
(
column1 data_type(size),
column2 data_type(size),
column3 data_type(size),
....
);

table_name:  name of the table.
column1 name of the first column.
data_type: Type of data we want to store in the particular column. 
            For example,int for integer data.
size: Size of the data we can store in a particular column. For example if for
a column we specify the data_type as int and size as 10 then this column can store an integer
number of maximum 10 digits. 

```

**示例查询:**
该查询将创建一个名为 Students 的表，该表有三列，ROLL_NO、NAME 和 SUBJECT。

```
CREATE TABLE Students
(
ROLL_NO int(3),
NAME varchar(20),
SUBJECT varchar(20),
);

```

该查询将创建一个名为“学生”的表。ROLL_NO 字段是 int 类型，可以存储大小为 3 的整数。接下来的两列 NAME 和 SUBJECT 属于 varchar 类型，可以存储字符，大小 20 指定这两个字段最多可以容纳 20 个字符。

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。