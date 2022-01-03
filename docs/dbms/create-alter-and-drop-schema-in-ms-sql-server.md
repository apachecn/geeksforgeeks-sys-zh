# 在 MS SQL Server 中创建、更改和删除模式

> 原文:[https://www . geesforgeks . org/create-alter-and-drop-schema-in-ms-SQL-server/](https://www.geeksforgeeks.org/create-alter-and-drop-schema-in-ms-sql-server/)

在本文中，我们将讨论模式以及如何创建、更改和删除模式。

**1。创建模式:**
模式通常是对象的集合。对象可以是表、触发器、视图、过程等。一个数据库可能有一个或多个模式。SQL Server 提供了预定义模式的功能。预定义模式的名称与内置模式的名称非常相似。

用户可以使用下面提到的语法创建模式。

**语法–**

```
create schema schema_name
[AUTHORIZATION owner_name] 
```

授权是一个关键字，它提供了对模式的权限。他/她可以控制可以访问的资源，还可以提供安全性。所有者的名称必须在 owner_name 下提供。也可以使用 alter schema 进行更改，这将在后面进一步讨论。

为了更好地理解，下面举了一个例子–

**示例–**

```
create schema student
GO 
```

**输出–**
GO 命令执行该语句，并创建一个新的模式。

**2。Alter schema :**
Alter 一般用于改变 SQL 中与表相关的内容。对于 SQL Server，alter_schema 用于在同一数据库中将安全对象/内容从一个模式传输到另一个模式。

**语法–**

```
alter schema target_schemaname
TRANSFER [entity_type::] securable name 
```

*   target_schemaname 是应该在其中传输对象/内容的架构的名称。
*   TRANSFER 是将内容从一个模式转移到另一个模式的关键字。
*   entity _type 是要传输的对象的内容或种类。
*   securable _ name 是对象所在的架构的名称。

当用户将模式的内容移动到另一个模式时，SQL server 不会更改模式的名称。如果用户想要更改名称，必须使用 drop_schema，并且需要为新模式重新创建对象。移动对象时，SQL server 不会自动更新，必须由用户手动修改。

**示例–**
一个名为“大学”的表有两个模式:

```
student and lecturer  
```

如果假设学生的分数必须转移到讲师模式，则查询如下–

```
alter schema student
TRANSFER [marks::] lecturer 
```

这样，标记被转移到讲师模式。

**3。删除模式:**
当模式及其相关对象必须从数据库(包括其定义)中完全删除时，将使用 Ddrop_schema。

**语法–**

```
drop schema [IF EXISTS] schema_name 
```

如果用户想检查一个模式是否真的存在于数据库中，那么 IF EXISTS 是可选的。Schema_name 是数据库中模式的名称。

**示例–**

```
drop schema [IF EXISTS] student 
```

*   学生是大学数据库中实际存在的模式。
*   该模式及其定义将从数据库中删除。