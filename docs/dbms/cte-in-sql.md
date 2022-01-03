# SQL 中的 CTE

> 原文:[https://www.geeksforgeeks.org/cte-in-sql/](https://www.geeksforgeeks.org/cte-in-sql/)

**通用表表达式(CTE)** 被引入到标准的 SQL 中，以简化各种类型的 SQL 查询，对于这些查询，派生表是不合适的。CTE 是在 SQL Server 2005 中引入的，通用表表达式(CTE)是一个临时命名结果集，您可以在 SELECT、INSERT、UPDATE 或 DELETE 语句中引用它。您也可以在 CREATE a 视图中使用 CTE，作为视图的 SELECT 查询的一部分。此外，从 SQL Server 2008 开始，您可以向新的 MERGE 语句中添加 CTE。

**使用 CTE–**
我们可以通过在 SELECT、INSERT、UPDATE、DELETE 或 MERGE 语句前直接添加 WITH 子句来定义 CTEs。WITH 子句可以包含一个或多个用逗号分隔的 cte。可以遵循以下语法:

```
[WITH  [, ...]]  

::=
cte_name [(column_name [, ...])]
AS (cte_query) 
```

在用 CTEs 定义了 WITH 子句之后，就可以像引用任何其他表一样引用 CTEs 了。但是，您只能在紧跟 WITH 子句的语句的执行范围内引用 CTE。运行语句后，CTE 结果集对其他语句不可用。

**创建递归公共表表达式–**
递归 CTE 是指在那个 CTE 中引用自己的。递归 CTE 在处理分层数据时非常有用，因为 CTE 会继续执行，直到查询返回整个分层结构。

分层数据的一个典型示例是包含员工列表的表。对于每个员工，该表提供了该人的经理的参考。该引用本身就是同一表中的员工标识。您可以使用递归 CTE 显示员工数据的层次结构。

如果 CTE 创建不正确，它可能会进入无限循环。为了防止这种情况，可以在主 SELECT、INSERT、UPDATE、DELETE 或 MERGE 语句的 OPTION 子句中添加 MAXRECURSION 提示。

**创建一个表:**

```
CREATE TABLE Employees
(
  EmployeeID int NOT NULL PRIMARY KEY,
  FirstName varchar(50) NOT NULL,
  LastName varchar(50) NOT NULL,
  ManagerID int NULL
)

INSERT INTO Employees VALUES (1, 'Ken', 'Thompson', NULL)
INSERT INTO Employees VALUES (2, 'Terri', 'Ryan', 1)
INSERT INTO Employees VALUES (3, 'Robert', 'Durello', 1)
INSERT INTO Employees VALUES (4, 'Rob', 'Bailey', 2)
INSERT INTO Employees VALUES (5, 'Kent', 'Erickson', 2)
INSERT INTO Employees VALUES (6, 'Bill', 'Goldberg', 3)
INSERT INTO Employees VALUES (7, 'Ryan', 'Miller', 3)
INSERT INTO Employees VALUES (8, 'Dane', 'Mark', 5)
INSERT INTO Employees VALUES (9, 'Charles', 'Matthew', 6)
INSERT INTO Employees VALUES (10, 'Michael', 'Jhonson', 6) 
```

创建雇员表后，将创建以下 SELECT 语句，该语句前面有一个 WITH 子句，该子句包含一个名为“字符报告”的 CTE:

```
WITH
  cteReports (EmpID, FirstName, LastName, MgrID, EmpLevel)
  AS
  (
    SELECT EmployeeID, FirstName, LastName, ManagerID, 1
    FROM Employees
    WHERE ManagerID IS NULL
    UNION ALL
    SELECT e.EmployeeID, e.FirstName, e.LastName, e.ManagerID, 
      r.EmpLevel + 1
    FROM Employees e
      INNER JOIN cteReports r
        ON e.ManagerID = r.EmpID
  )
SELECT
  FirstName + ' ' + LastName AS FullName, 
  EmpLevel,
  (SELECT FirstName + ' ' + LastName FROM Employees 
    WHERE EmployeeID = cteReports.MgrID) AS Manager
FROM cteReports 
ORDER BY EmpLevel, MgrID 
```

因此，当您需要生成可以在 SELECT、INSERT、UPDATE、DELETE 或 MERGE 语句中访问的临时结果集时，CTEs 可能是一个有用的工具。