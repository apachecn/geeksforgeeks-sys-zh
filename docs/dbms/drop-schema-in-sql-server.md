# 在 SQL Server 中删除模式

> 原文:[https://www.geeksforgeeks.org/drop-schema-in-sql-server/](https://www.geeksforgeeks.org/drop-schema-in-sql-server/)

可以使用 **DROP SCHEMA** 语句从数据库中删除一个模式。 [SQL Server](https://www.geeksforgeeks.org/sql-tutorial/#sql-server) 有一些内置的模式，比如:dbo、guest、sys、INFORMATION_SCHEMA，不能删除。

**语法:**

```
DROP SCHEMA [IF EXISTS] schema_name;

```

**注意:**删除模式前，删除模式中的所有对象。如果模式中有任何对象，输出将是一个错误。

**示例:**
让我们创建一个名为 geek sh([https://www.geeksforgeeks.org/create-schema-in-sql-server/](https://www.geeksforgeeks.org/create-schema-in-sql-server/))的新模式；

```
CREATE SCHEMA geeksh;
GO

```

现在在**极客**模式中创建一个名为**极客标签**的表:

```
CREATE TABLE geeksh.geektab
(id INT PRIMARY KEY,
date DATE NOT NULL,
city varchar(200) NOT NULL);

```

**放下模式极客:**

DROP SCHEMA geeksh
由于模式不为空，SQL Server 将抛出类似的错误。

```
Msg 3729, Level 16, State 1, Line 1
Cannot drop schema 'geeksh' because it is being referenced by object 'geektab'.

```

让我们放下表 geeksh.geektab:

```
DROP TABLE geeksh.geektab;

```

再次运行 DROP SCHEMA 来删除 geeksh 模式:

```
DROP SCHEMA IF EXISTS geeksh;

```

现在，geeksh 模式已经从数据库中删除了。