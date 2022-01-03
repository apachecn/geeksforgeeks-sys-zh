# 存储定义语言(SDL)

> 原文:[https://www . geesforgeks . org/storage-definition-languages-SDL/](https://www.geeksforgeeks.org/storage-definition-languages-sdl/)

[DBMS](https://www.geeksforgeeks.org/dbms-full-form/) 支持多种语言，其中(SDL)就是其中之一。 **SDL** 代表**存储定义语言**。SDL 物质几乎是任何没有被 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 标准规定的东西。它在每个数据库管理系统中都是不同的，每个数据库管理系统都指定了相关表中数据的存储方式和位置。它的应用如下:

*   Used to define the internal mode.
*   Define the physical structure of the database.
*   The order of the fields.
*   The bytes of each field will be used.
*   How the records will be accessed, etc.
*   You can also define a mapping between two patterns.

**示例:**让我们举一些例子来了解存储定义语言(SDL)是如何工作的。

**示例-1 :**

```
CREATE TABLE geeksforgeeks (no_of_articles INT) ENGINE = INNODB;

```

在上面的示例中，我们通过添加 engine 选项来指定要使用的存储引擎。InnoDB 是 MySQL 8.0 的默认存储引擎。

**示例-2 :**

```
CREATE TABLE geeksforgeeks (article_titile varchar(65000) ENGINE = MEMORY;

```

这次使用的引擎是 MEMORY。内存存储引擎(也称为堆)为特定目的创建表，表的内容存储在内存中。因为数据容易受到断电、崩溃或硬件问题的影响，所以只将这些表用作临时工作区或从其他表中提取的数据的只读缓存。

**示例-3 :**

```
CREATE TABLE f (x int, y varchar(25));

```

在上面的陈述中，存储定义语言(SDL)定义了行 **int，varchar(25)** 的存储。

事实上，在大多数关系数据库管理系统中，没有特定的语言来扮演 SDL 的角色。相反，与文件存储相关的函数、参数和规范的组合定义了内部模式。