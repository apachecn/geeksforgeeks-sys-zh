# SQL |默认约束

> 原文:[https://www.geeksforgeeks.org/sql-default-constraint/](https://www.geeksforgeeks.org/sql-default-constraint/)

**默认约束**用于用默认值和固定值填充列。当没有提供其他值时，该值将被添加到所有新记录中。

**1。在创建表格时使用默认值:**

**语法:**

```
CREATE TABLE tablename (
Columnname DEFAULT 'defaultvalue' );
```

**示例–**
创建“极客”表时，为“位置”列设置默认值–

```
CREATE TABLE Geeks (
ID int NOT NULL,
Name varchar(255),
Age int,
Location varchar(255) DEFAULT 'Noida');
```

```
INSERT INTO Geeks VALUES (4, 'Mira', 23, 'Delhi');
INSERT INTO Geeks VALUES (5, 'Hema', 27);
INSERT INTO Geeks VALUES (6, 'Neha', 25, 'Delhi');
INSERT INTO Geeks VALUES (7, 'Khushi', 26);
```

**输出–**

```
select *
from Geeks;
```

<center>

| 身份证明 | 名字 | 年龄 | 位置 |
| --- | --- | --- | --- |
| four | 蒭藁增二 | Twenty-three | 德里 |
| five | Hema | Twenty-seven | 无聊死了 |
| six | 停止 | Twenty-five | 德里 |
| seven | 库希 | Twenty-six | 无聊死了 |

</center>

**2。删除默认约束:**

**语法:**

```
ALTER TABLE tablename
ALTER COLUMN columnname 
DROP DEFAULT;
```

**示例–**

```
ALTER TABLE Geeks
ALTER COLUMN Location
DROP DEFAULT;
```

让我们在极客表中添加 2 个新行:

```
INSERT INTO Geeks VALUES (8, 'Komal', 24, 'Delhi');
INSERT INTO Geeks VALUES (9, 'Payal', 26);
```

**注意–**
删除默认约束不会影响表中的当前数据，它只适用于新行。

**输出–**

```
Select * 
from Geeks;
```

<center>

| 身份证明 | 名字 | 年龄 | 位置 |
| --- | --- | --- | --- |
| four | 蒭藁增二 | Twenty-three | 德里 |
| five | Hema | Twenty-seven | 无聊死了 |
| six | 停止 | Twenty-five | 德里 |
| seven | 库希 | Twenty-six | 无聊死了 |
| eight | 科马尔 | Twenty-four | 德里 |
| nine | 帕帕尔 | Twenty-six | 空 |

</center>