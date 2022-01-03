# 什么是 SQL 中的临时表？

> 原文:[https://www . geeksforgeeks . org/什么是 sql 中的临时表/](https://www.geeksforgeeks.org/what-is-temporary-table-in-sql/)

**临时表**最有可能作为永久表。临时表在临时数据库中创建，并在最后一次连接终止时自动删除。临时表帮助我们存储和处理中间结果。当我们需要存储临时数据时，临时表非常有用。创建临时表的语法如下:

**创建临时表:**

```
CREATE TABLE #EmpDetails (id INT, name VARCHAR(25))  
```

**将值插入临时表:**

```
INSERT INTO #EmpDetails VALUES (01, 'Lalit'), (02, 'Atharva') 
```

**从临时表中选择值:**

```
SELECT * FROM #EmpDetails 
```

**结果:**

| 身份证明（identification） | 名字 |
| one | 拉利特 |
| Two | 阿萨娃 |

临时表有两种类型:本地临时表和全局临时表。这些解释如下。

1.  **Local Temporary Table:**
    A Local Temp Table is available only for the session that has created it. It is automatically dropped (deleted) when the connection that has created it, is closed. To create Local Temporary Table Single “#” is used as the prefix of a table name.

    此外，用户可以通过使用“删除表#EmpDetails”查询来删除这个临时表。将会有随机数被追加到表名的名称中。如果临时表是在存储过程中创建的，它会在存储过程执行完成时自动删除。

    **示例:**

    ```
    CREATE PROCEDURE ProcTemp 
    AS
    BEGIN
    CREATE TABLE #EmpDetails
    INSERT INTO #EmpDetails VALUES ( 01, 'Lalit'), ( 02, 'Atharva')
    SELECT * FROM #EmpDetails
    END
    EXECUTE ProcTemp 
    ```

2.  **Global Temporary Table:**
    To create a Global Temporary Table, add the “##” symbol before the table name.

    **示例:**

    ```
    CREATE TABLE ##EmpDetails (id INT, name VARCHAR(25)) 
    ```

    全局临时表对所有连接都是可见的，并且在引用该表的最后一个连接关闭时被删除。全局表名必须有唯一的表名。在表名的末尾没有以随机数为后缀。