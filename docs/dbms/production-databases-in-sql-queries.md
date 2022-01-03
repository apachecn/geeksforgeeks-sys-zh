# SQL 查询中的生产数据库

> 原文:[https://www . geesforgeks . org/production-databases-in-SQL-query/](https://www.geeksforgeeks.org/production-databases-in-sql-queries/)

[SQL](https://www.geeksforgeeks.org/sql-tutorial/) 是一种结构化查询语言，它是一种用于存储、操作和检索存储在关系数据库中的数据的计算机语言。SQL 是最强大的数据处理工具。可操作的建议，帮助您获得最通用的语言，并创建美观、有效的查询。SQL 被有效地用于插入、搜索、更新、删除、修改数据库记录。这并不意味着 SQL 不能做超出这个范围的事情。它还可以做很多其他的事情。在 SQL 中，数据以关系的形式存储。这种关系理论是由博伊斯和钱伯林提出的。第一家发布和修改 SQL 版本的公司是关系软件，它被称为甲骨文 V2。SQL 于 1986 年成为美国国家标准协会(ANSI)的标准，1987 年成为国际标准化组织(ISO)的标准。

让我们借助例子来理解。

**示例-1 :**
创建个人信息客户表的 SQL 查询如下。

```
CREATE TABLE CUSTOMERS (
ID INT NOT NULL,
NAME VARCHAR (20) NOT NULL,
AGE INT NOT NULL,
ADDRESS CHAR (25),
ORDERS VARCHAR (155)
);
```

**示例-2 :**
创建客户表的 SQL 查询如下。

```
CREATE TABLE CUSTOMERS (
CUS_ID INT NOT NULL,
CUST_NAME VARCHAR(20) NOT NULL,
DOB DATE,
STREET VARCHAR (200),
CITY VARCHAR (100),
STATE VARCHAR (100),
EMAIL_ID VARCHAR (256),
PRIMARY KEY ( CUST_ID)
);
```

**生产数据库在 SQL 查询中的使用:**

**1。业务需求–**
确定利益相关方，关注业务成果，讨论最佳需求，提出重大问题和具体需求，并与利益相关方确认。

**2。选择字段–**
使用 SELECT 语句将使数据库只查询满足业务需求所需的数据。让我们借助例子来理解。例如–

效率低下–

```
SELECT * FROM Customers     
```

高效–

```
SELECT FirstName, Last name, Address,City,State,Zip  
FROM Customers       
```

**3。避免使用 SELECT DISTINCT–**
SELECT DISTINCT 是一种从查询中删除重复项的方法。SELECT DISTINCT 通过对查询中的所有字段进行分组来工作。

低效且不准确–

```
SELECT DISTINCT FirstName, Last name, State 
FROM Customers       
```

高效准确–

```
SELECT FirstName, LastName, Address, City, State, Zip              
FROM Customers        
```

**4。加入(不是在哪里)–**

```
SELECT Customers.CustomerID, Customers. Name, Sales. Last Sale.Date FROM Customers, Sales 
WHERE Customers.CustomerID = Sales.customerID 
```

这种类型的连接创建笛卡尔连接，也称为笛卡尔乘积或交叉连接

内部连接–

```
SELECT Customers.CustomerID, Customers.Name , Sales.Last SaleDate  
from Customers 
INNER JOIN Sales ON customers.CustomerID  = 
Sales.CustomerID 
```

[数据库管理系统](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)能够识别 WHERE 连接，并自动将它们作为内部连接运行。

**5。使用 where 而不是必须定义过滤器–**
高效的 SQL 查询的目标必须是从数据库中只获取所需的记录。例如，假设 2017 年完成了 300 笔销售，我们想要查询 2017 年每个客户的销售数量。

```
SELECT Customers.customerID,Customers.Name,Count (sales.saleID)
FROM Customers
INNER JOIN Sales       
ON Customers.CustomerID = Sales.CustomerID        
GROUP BY Customers.CustomerID,Customers.Name      
HAVING Sales.Last SaleDate 
BETWEEN     
#1/1/2017# AND #12/31/2017#
```

**6。在结尾使用通配符–**
使用通配符，尤其是与结尾通配符结合使用时，数据库负责在所选字段的任何位置搜索所有匹配记录。

```
SELECT City FROM Customers                     
WHERE city LIKE '%char%' 
```

**7。在非高峰时间运行您的查询–**
提高性能并避免由于其他活动(如更新、修补、错误修复脚本和其他脚本等)而导致的任何生产负载总是一个好主意。必须在非高峰时间运行。

以下标准如下所示。

*   从大型表格中选择
*   笛卡尔连接
*   循环语句
*   嵌套子查询。

**特征:**

*   **高性能–**
    SQL 提供了高性能的编程能力、繁重的工作负载和高使用率的数据库系统。它给出了各种方法来更好地描述数据。
*   **高可用性–**
    兼容 MS Access、微软 SQL Server、MY SQL、Oracle 数据库等数据库。关系数据库管理支持 SQL。为过程编程创建应用程序扩展很容易。
*   **可扩展性和灵活性–**
    创建新表非常容易，以前创建或未使用的表可以在数据库中删除。
*   **高安全性–**
    很容易提供对表、过程和视图的权限，因此它为您的数据提供了安全性。

**结论:**
设计具有可重用查询的对象。其他可以参考的对象可以节省我们的开发时间。我们需要重新开发参考对象。当我们进行更改时，它会跟踪从注释到元数据的引用，然后引入很少的问题。由于查询是临时的或易于开发，有些情况可能不需要引用。