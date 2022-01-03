# 在 SQL 中创建和删除索引语句

> 原文:[https://www . geesforgeks . org/create-and-drop-index-in-SQL 语句/](https://www.geeksforgeeks.org/create-and-drop-index-statement-in-sql/)

**1。CREATE INDEX 语句:**
CREATE INDEX 语句将在表中创建索引。**索引**用于更快地从数据库获取数据。用户看不到索引，它们在查询的后台运行，用于加速搜索/查询。

**语法:**
在表上创建索引:

```
CREATE INDEX indexname
ON tablename (columnname1, columnname2, ...);
```

在表上创建唯一索引–

```
CREATE UNIQUE INDEX indexname
ON tablename (columnname1, columnname2, ...);
```

**示例–**
下面的 SQL 语句将在“GeeksTab”表的“LastName”列上创建一个名为“idx_name”的索引–

```
CREATE INDEX idx_name
ON GeeksTab (LastName);
```

要在多列上创建索引–

```
CREATE INDEX idx_pname
ON GeeksTab (LastName, FirstName);
```

**2。降索引语句:**
降索引语句可用于从任何表中删除索引。

**语法:**

```
DROP INDEX tablename.indexname;
```

**示例–**

```
DROP INDEX GeeksTab.idx_pname;
```