# SQL |同义词

> 原文:[https://www.geeksforgeeks.org/sql-synonym/](https://www.geeksforgeeks.org/sql-synonym/)

**同义词**为数据库对象提供了另一个名称，称为原始对象，它可能存在于本地或另一个服务器上。同义词属于架构，同义词的名称应该是唯一的。同义词不能是附加同义词的原始对象，并且同义词不能引用用户定义的函数。

下面的查询为数据库中的每个同义词生成一个条目。此查询提供了有关同义词元数据的详细信息，例如同义词的名称和基本对象的名称。

```
select * 
from sys.synonyms ;
```

**注意:**同义词依赖于数据库，不能被其他数据库访问。

**语法–**

```
CREATE SYNONYM synonymname 
FOR servername.databasename.schemaname.objectname;
GO
```

**示例–**
让我们假设 GFGdatabase 的 Geeekshschema 位于名为 Server1 的服务器上。要从另一台服务器(服务器 2)引用该表，应用程序必须使用名为 Server1.GFG.Geeeksh.Geektab 的四部分。此外，如果要更改表的位置，例如更改到另一台服务器，应用程序必须进行修改以反映该更改。

为了解决这两个问题，可以在服务器 2 上为服务器 1 上的极客表创建同义词极客表。现在，应用程序只需要使用单部分名称极客表来指向极客表。此外，如果极客表的位置发生变化，您必须修改同义词极客表，以指向极客表的新位置。

现在，让我们为 GFG 数据库的极客表创建一个同义词:服务器 1 上的 Geeeksh 模式。

```
CREATE SYNONYM Geektable  
FOR Server1.GFG.Geeeksh.Geektab;  
GO
```

使用同义词在服务器 2 中查找输出。

```
SELECT ID, Name    
FROM Geektable;
```

**输出–**

| 身份证明 | 名字 |
| --- | --- |
| one | 妮莎 |
| Two | 蒭藁增二 |
| three | Punit |
| four | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) |

```
(4 row(s) affected)
```