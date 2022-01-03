# SQL |声明本地临时表

> 原文:[https://www . geesforgeks . org/SQL-declare-local-temporary-table/](https://www.geeksforgeeks.org/sql-declare-local-temporary-table/)

**声明本地临时表**语句用于创建临时表。临时表中的行仅对创建表并插入行的连接可见。

**语法–**

```
DECLARE LOCAL TEMPORARY TABLE table-name
( column-name [ column-value ] );

```

**示例:**

```
DECLARE LOCAL TEMPORARY TABLE TempGeek ( number INT );

INSERT INTO Geeks 
VALUES (1), (2), (3), (4);

Select * 
from TempGeek; 
```

<center>

| 数字 |
| --- |
| one |
| Two |
| three |
| four |

一旦创建了本地临时表，只要该临时表存在，就不能再创建另一个同名的临时表。

**示例–**
您可以通过输入以下命令来创建本地临时表:

```
declare local temporary table Geektable

```

如果您尝试选择“极客表”或再次声明极客表，您会收到一个错误，指示极客表已经存在。

当您声明临时表时，排除所有者规范。

如果在同一个会话中，除了 DECLARE LOCAL TEMPORARY TABLE 语句之外，还指定了相同的 owner.table，则会报告语法错误。

**示例–**

```
DECLARE LOCAL TEMPORARY TABLE user1.Gfgt(col1 int);
DECLARE LOCAL TEMPORARY TABLE user.Gfgt(col1 int);

```

报告错误“项目已存在”:

但是，您可以创建一个与现有基表或全局临时表同名的临时表，但是首先使用本地临时表。

**示例–**
考虑以下顺序:

```
CREATE TABLE Geeks (num int);
INSERT INTO Geeks VALUES (9), (8) ;

```

<center>

| 数字 |
| --- |
| nine |
| eight |

</center>

声明本地临时表极客；

```
INSERT INTO Geeks VALUES (6), (7);

```

<center>

| 数字 |
| --- |
| six |
| seven |

</center>

```
SELECT * 
FROM Geeks; 
```

**输出:**
返回的结果是

<center>

| 数字 |
| --- |
| six |
| seven |

</center>

任何对极客的引用都是指本地临时表极客，直到本地临时表被连接丢弃。

ALTER TABLE 和 DROP INDEX 语句不能用于本地临时表。

</center>