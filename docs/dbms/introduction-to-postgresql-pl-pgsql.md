# PostgreSQL PL/pgSQL 简介

> 原文:[https://www . geesforgeks . org/introduction-to-PostgreSQL-pl-pgsql/](https://www.geeksforgeeks.org/introduction-to-postgresql-pl-pgsql/)

在这篇文章中，我们将讨论 PostgreSQL PL/pgSQL 的概述，还将借助每个操作的示例介绍 CRUD(CREATE、READ、UPDATE、DELETE)操作，最后将讨论 PostgreSQL PL/pgSQL 的优缺点。我们一个一个来讨论。

[**PostgreSQL**](https://www.geeksforgeeks.org/postgresql-format-function/)**:**
它是一个功能强大的开源对象关系数据库系统，扩展了 SQL 语言。它使用 SQL 语言以及安全扩展工作负载的许多功能的组合。它是开源的和高度可扩展的。它还支持所有主要的操作系统。它有一个经过验证的体系结构，以及可靠性、可扩展性、数据完整性等几个基础，这些是 PostgreSQL 流行的主要因素。PostgreSQL 是一种过程编程语言。PL/pgSQL 旨在创建用户定义的函数、存储过程和触发器，继承所有用户定义的函数和类型，等等。

【PostgreSQL 入门:
首先我们将学习如何使用基本的 PLSQL 命令创建单个表。然后我们将学习如何使用基本的选择技术来查询数据。最后，我们将学习如何更新或删除现有的表结构。让我们从下面的讨论开始。

**在 PostgreSQL 中创建表查询–**
这将在数据库中创建一个新的、最初为空的表。
**语法:**

```
CREATE TABLE table_name
(
column1 datatype(size), 
column2 datatype(size),...
columnN datatype(size)
);
```

**示例:**

```
CREATE TABLE GFG
(
order_no int, 
about varchar(20),
fields text
);
```

**输出:**

```
CREATE TABLE
Query returned successfully in 100ms.
```

**在 PostgreSQL 中的 INSERT INTO 查询–**
INSERT 命令用于将数据插入表中。
**语法:**

```
INSERT INTO table_name 
values
(value1,value2,...value N);
```

**例**:

```
INSERT INTO GFG 
values
(1,'CSE portal','DBMS');
```

**输出**:

```
INSERT 0 1
Query returned successfully in 57 msec.
```

**在 PostgreSQL 中没有 WHERE 关键字的 SELECT 查询–**
在没有 WHERE 条件的情况下使用 SELECT 命令时，会从表中获取所有数据。
**语法**:

```
SELECT * FROM table_name;
```

**例**:

```
SELECT * FROM GFG;
```

**输出:**

<figure class="table">

| 

订单编号

(整数)

 | 

关于；在…各处 ；大约

(字符变化(20))

 | 

田地（复数）；场；域；字段

(文本)

 |
| --- | --- | --- |
| one | CSE 门户网站 | 数据库管理系统 |
| Two | 最佳组织 | 编程语言 |
| three | 查找所有解决方案 | 学校学习 |
| four | 使用方便 | GATE 练习问题 |

</figure>

**注意–**
如前所述，该表已经使用插入命令填充了数据。

**在 PostgreSQL 中使用 WHERE 关键字的 SELECT 查询–**
SELECT 命令与 WHERE 条件一起使用时，从表中提取选定的行。
**语法**:

```
SELECT * FROM table_name 
WHERE condition;
```

**例**:

```
SELECT * FROM GFG 
WHERE fields='DBMS';
```

**输出**:

<figure class="table">

| 

订单编号

(整数)

 | 

关于；在…各处 ；大约

(字符变化(20))

 | 

田地（复数）；场；域；字段

(文本)

 |
| --- | --- | --- |
| one | CSE 门户网站 | 数据库管理系统 |

</figure>

**更新 PostgreSQL 中的查询–**
更新命令用于更新数据库表的数据或行。
**语法**:

```
UPDATE table_name 
SET column_name = NewValue 
WHERE condition;
```

**例**:

```
UPDATE GFG 
SET fields = 'Data analysis' 
WHERE order_no = 3;
```

**输出**:

```
UPDATE 1
Query returned successfully in 65 msec.
```

要查看 UPDATE 命令后成功进行的更改，请运行 SELECT 命令显示整个表，如下所示:

<figure class="table">

| 

订单编号

(整数)

 | 

关于；在…各处 ；大约

(字符变化(20))

 | 

田地（复数）；场；域；字段

(文本)

 |
| --- | --- | --- |
| one | CSE 门户网站 | 数据库管理系统 |
| Two | 最佳组织 | 编程语言 |
| four | 使用方便 | GATE 练习问题 |
| three | 查找所有解决方案 | 数据分析 |

**PostgreSQL 中的 delete 查询–**
用于从表中删除行数据，在 DELETE 查询中 WHERE 子句条件是可选的。
**语法**:

```
DELETE FROM table_name 
WHERE condition;
```

**例**:

```
DELETE FROM GFG 
WHERE order_no = 4;
```

**输出**:

```
DELETE 1
Query returned successfully in 61 msec.
```

要查看在 DELETE 命令后成功进行的更改，请运行 SELECT 命令显示整个表，如下所示。

<figure class="table">

| 

订单编号

(整数)

 | 

关于；在…各处 ；大约

(字符变化(20))

 | 

田地（复数）；场；域；字段

(文本)

 |
| --- | --- | --- |
| one | CSE 门户网站 | 数据库管理系统 |
| Two | 最佳组织 | 编程语言 |
| three | 查找所有解决方案 | 数据分析 |

</figure>

**使用 PL/pgSQL 的优势:**

*   PL/SQL 与 SQL 紧密集成，即 PL/SQL 允许您使用所有的 SQL 数据操作，以及所有的 SQL 函数和运算符。
*   PL/SQL 允许您运行 SQL 查询并一次处理一行结果集。
*   PL/SQL 应用程序可以在任何运行 Oracle 数据库的操作系统上运行。
*   它提高了可管理性，因为在这种情况下，您只能在数据库服务器上维护子程序的一个副本。
*   通过集中应用程序处理，它有助于提高数据库服务器的可伸缩性。

**使用 PL/pgSQL 的缺点:**

*   PL/pgSQL 需要许多开发人员不具备的专门技能，这就是为什么它在 [SDLC](https://www.geeksforgeeks.org/software-engineering-sdlc-v-model/) 过程中速度较慢的原因。
*   版本难管理，调试难。
*   它可能无法移植到其他数据库管理系统。

</figure>