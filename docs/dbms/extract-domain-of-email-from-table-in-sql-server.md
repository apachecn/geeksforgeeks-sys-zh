# 从 SQL Server 的表中提取邮件的域

> 原文:[https://www . geesforgeks . org/extract-domain-of-of-email-from-in-table-in-SQL-server/](https://www.geeksforgeeks.org/extract-domain-of-email-from-table-in-sql-server/)

**简介** :
作为数据库管理员，您可能会遇到一个请求，您需要提取电子邮件地址的域，即存储在数据库表中的电子邮件地址。如果您想从任何给定的表中的电子邮件地址中统计最常用的域名，您可以统计从 SQL Server 的电子邮件中提取的域的数量，如下所示。

SQL 查询可用于从电子邮件地址中提取域。
让我们创建一个名为“ **email_demo** ”的表–

```
create table (ID int, Email varchar (200));
```

在表格中插入值 email _ demo–

```
insert into email_demo values(
(1, 'Sam@gfg.com'), (2, 'Khushi@gfg.com'),
(3, 'Komal@gfg.org'), (4, 'Priya@xyz.com'),
(5, 'Sam@xyz.com'), (6, 'Krish@xyz.com'),
(7, 'Neha@gfg.com'), (8, 'Pam@gfg.com'),
(9, 'Mohan@abc.com'), (10, 'Ankit@mno.com'),
(11, 'Kumari@gfg.com'), (12, 'Hina@abc.com'),
(13, 'Jaya@mno.com'), (14, 'Piyush@abc.com'),
(15, 'Khushi@xyz.com'), (16, 'Mona@gfg.org'),
(17, 'Roza@abc.com'));
```

显示表格内容–

```
select * from email_demo;
```

| 身份证明 | 电子邮件 |
| --- | --- |
| one | 山姆@gfg.com |
| Two | Khushi@gfg.com(中文) |
| three | Komal@gfg.org |
| four | Priya@xyz.com |
| five | Sam@xyz.com |
| six | Krish@xyz.com |
| seven | Neha@gfg.com |
| eight | Pam@gfg.com |
| nine | Mohan@abc.com |
| Ten | 安凯特@mno.com |
| Eleven | Kumari@gfg.com |
| Twelve | Hina@abc.com |
| Thirteen | Jaya@mno.com |
| Fourteen | Piyush@abc.com |
| Fifteen | Khushi@xyz.com(中文) |
| Sixteen | Mona@gfg.org |
| Seventeen | 萝扎@abc.com |

**1。在下面的例子中，我们将使用 [SUBSTRING 函数](https://www.geeksforgeeks.org/substring-function-in-sql-server/)来选择每个值中@符号之后的字符串。**

**SQL 从电子邮件中提取域–**

```
SELECT ID,
SUBSTRING ([Email], CHARINDEX( '@', [Email]) + 1,
LEN([Email])) AS [Domain]
FROM [email_demo];
```

**输出:**

| 身份证明 | 领域 |
| --- | --- |
| one | gfg.com |
| Two | gfg.com |
| three | gfg.org |
| four | xyz.com |
| five | xyz.com |
| six | xyz.com |
| seven | gfg.com |
| eight | gfg.com |
| nine | abc.com |
| Ten | mno.com |
| Eleven | gfg.com |
| Twelve | abc.com |
| Thirteen | mno.com |
| Fourteen | abc.com |
| Fifteen | xyz.com |
| Sixteen | gfg.org |
| Seventeen | abc.com |

**接近使用:**

*   这里，我们在 SUBSTRING 函数中将 Source 指定为我们的列名“Email”。
*   接下来，我们使用 CHARINDEX 函数找到@符号，然后添加 1，这样起点就在@符号之后。
*   然后，我们使用 LEN 函数来指定结束值。

**2。在 SQL Server 中统计从电子邮件中提取的域名数量:**
**方法 1 :** SQL 查询统计从电子邮件中提取域名的记录数量–

```
SELECT RIGHT ([Email],
LEN([Email]) - CHARINDEX( '@', [Email])) AS [Domain],
COUNT(*) AS [Total Number of Domain]
FROM [email_demo]
WHERE LEN([Email ]) > 0
GROUP BY RIGHT([Email],
LEN([Email]) - CHARINDEX( '@', [Email]));
```

**输出:**

| 领域 | 域总数 |
| --- | --- |
| abc.com | four |
| gfg.com | five |
| gfg.org | Two |
| mno.com | Two |
| xyz.com | four |

**方法 2 :** 统计从电子邮件中提取域名的记录数量的 SQL 查询–

```
SELECT SUBSTRING ([Email],
CHARINDEX( '@', [Email] ) + 1, LEN([Email])) AS [Domain],
COUNT(*) AS [Total Number of Domain]
FROM [email_demo]
WHERE LEN([Email]) > 1
GROUP BY SUBSTRING ([Email], CHARINDEX( '@', [Email] ) + 1,
LEN([Email]));
```

**输出:**

| 领域 | 域总数 |
| --- | --- |
| abc.com | four |
| gfg.com | five |
| gfg.org | Two |
| mno.com | Two |
| xyz.com | four |