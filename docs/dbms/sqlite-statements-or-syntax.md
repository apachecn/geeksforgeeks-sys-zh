# SQLite 语句或语法

> 原文:[https://www.geeksforgeeks.org/sqlite-statements-or-syntax/](https://www.geeksforgeeks.org/sqlite-statements-or-syntax/)

**[【SQlite】](https://www.geeksforgeeks.org/introduction-to-sqlite/)**后面是一套叫做语法的规则和指导方针。

**注意:** SQLite 不区分大小写，即 syntax 和 SYNTAX 两个词在 SQLite 语句中的含义相同。

**SQLite 语句:**
所有的 SQLite 语句都以分号(；).下面列出了所有基本的 SQLite 语法。

**1。分析声明:**

```
ANALYZE;
OR
ANALYZE dbname;
OR
ANALYZE dbname.tablename;

```

**2。和/或条款:**

```
SELECT col1, col2
FROM tablename
WHERE CONDITION-1 {AND|OR} CONDITION-2;

```

**3。更改表格声明:**

```
ALTER TABLE tablename ADD COLUMN coldef;
OR (Rename)
ALTER TABLE tablename RENAME TO newtablename;

```

**4。附加数据库声明:**

```
ATTACH DATABASE 'DbName' As 'AliasName';

```

**5。开始交易声明:**

```
BEGIN;
OR
BEGIN EXCLUSIVE TRANSACTION;

```

**6。条款之间:**

```
SELECT col1, col2
FROM table_name
WHERE colname BETWEEN val1 AND val2;

```

**7。提交交易声明:**

```
COMMIT;

```

**8。创建索引语句:**

```
CREATE INDEX indexname
ON tablename ( colname COLLATE NOCASE );
UNIQUE INDEX 
CREATE UNIQUE INDEX indexname
ON tablename ( col1, col2, ...coln);

```

**9。创建表格声明:**

```
CREATE TABLE tablename(
  col1 datatype,
  col2 datatype,
  PRIMARY KEY( one or more columns )
);

```

**10。创建触发器语句:**

```
CREATE TRIGGER databasename.triggername  
BEFORE INSERT ON tablename FOR EACH ROW
BEGIN  
  stmt1;  
  stmt2;
END;

```

**11 时。创建视图声明:**

```
CREATE VIEW databasename.viewname AS
SELECT statements;

```

**12 时。创建虚拟表语句:**

```
CREATE VIRTUAL TABLE dbname.tablename USING weblog( access.log );
OR
CREATE VIRTUAL TABLE dbname.tablename USING fts3( );

```

**13。删除声明:**

```
DELETE FROM tablename
WHERE {CONDITION};

```

**14。分离数据库语句:**

```
DETACH DATABASE 'AliasName';

```

**15。DROP 语句:**

```
INDEX
DROP INDEX database_name.indexname;
TABLE 
DROP TABLE database_name.tablename;
VIEW 
DROP INDEX database_name.viewname;
TRIGGER 
DROP INDEX database_name.triggername;

```

**16。解释声明:**

```
EXPLAIN INSERT statements;
or  
EXPLAIN QUERY PLAN SELECT statements;

```

**17。在陈述中插入:**

```
INSERT INTO tablename( col1, col2)
VALUES ( val1, val2);

```

**18。PRAGMA 声明:**

```
PRAGMA pragmaname;

```

**19。REINDEX 声明:**

```
REINDEX collationname;
REINDEX dbname.indexname;

```

**20。回滚语句:**

```
ROLLBACK;
OR
ROLLBACK TO SAVEPOINT savepointname;

```

**21。保存点声明:**

```
SAVEPOINT savepointname;

```

**22。释放保存点声明:**

```
RELEASE savepointname;

```

**23。选择声明:**

```
SELECT col1, col2
FROM tablename;

```

**24。更新声明:**

```
UPDATE tablename
SET col1 = val1, col2 = val2
[ WHERE  CONDITION ];

```

**25。真空声明:**

```
VACUUM;

```