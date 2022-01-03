# 在 SQL Server 中更改模式

> 原文:[https://www.geeksforgeeks.org/alter-schema-in-sql-server/](https://www.geeksforgeeks.org/alter-schema-in-sql-server/)

用于将对象从一个模式转移到同一数据库中的另一个模式的 **ALTER SCHEMA** 语句。

**语法:**

```
ALTER SCHEMA target_schema_name    
   TRANSFER [ object_type :: ] object_name;

```

**参数:**

*   **target_schema_name** 是数据库中的模式，对象将被移入其中。
*   **对象类型**表示所有者模式将被更改的对象的类型。
*   **object_name** 是将被移动到 target_schema_name 的对象的名称。

**注意:** SYS 或 INFORMATION_SCHEMA 不能更改。

**示例:**
让我们在 **dbo** 模式中创建名为**极客选项卡**的表:

```
CREATE TABLE dbo.geektab
(id INT PRIMARY KEY IDENTITY,
name NVARCHAR(40) NOT NULL,
address NVARCHAR(255) NOT NULL);

```

现在，在 dbo.geektab 表中插入一些行:

插入 dbo.geektab (id、名称、地址)

```
VALUES (1, 'Neha', 'B-Wing, Delhi'), (2, 'Vineet', 'D-Wing, Noida');

```

让我们创建一个存储过程来查找 id:

```
CREATE PROCEDURE sp_get_id(@id INT
) AS
BEGIN
SELECT *
FROM dbo.geektab
WHERE id = @id;
END;

```

让我们将这个 **dbo.geektab** 表移动到 **geek** 模式:

**ALTER SCHEMA geek TRANSFER OBJECT::dbo . geek tab；**

运行 sp_get_id 存储过程:

**EXEC sp _ get _ id；**

SQL Server 将抛出类似下面提到的错误:

```
strong>Msg 208, Level 16, State 1, Procedure sp_get_id, Line 3
Invalid object name 'dbo.geektab'

```

现在，让我们手动修改存储过程以反映 geek 模式:

```
ALTER PROCEDURE sp_get_id( @id INT
) AS
BEGIN SELECT *
FROM geek.geektab
WHERE id = @id;
END;

```

运行 sp_get_id 存储过程:

```
EXEC sp_get_id 1; 
```

**输出–**

| 身份证明（identification） | 名字 | 地址 |
| --- | --- | --- |
| one | 停止 | 德里 b 翼 |