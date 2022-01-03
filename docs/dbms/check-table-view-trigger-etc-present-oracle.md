# 检查 Oracle 中是否存在表、视图、触发器等

> 原文:[https://www . geesforgeks . org/check-table-view-trigger-etc-present-Oracle/](https://www.geeksforgeeks.org/check-table-view-trigger-etc-present-oracle/)

有时在使用 SQL 时，我们经常忘记我们之前创建的视图、序列、索引、同义词或触发器的名称。也可能会发生，我们希望在未来验证它们。

**验证**意味着我们正在检查该特定模式中的所有当前数据库对象或触发器。
这首先可以使用下面提到的查询来完成:

**先决条件:** [数据库对象](https://www.geeksforgeeks.org/dbms-database-objects/)
[触发器](https://practice.geeksforgeeks.org/problems/what-are-mysql-triggers-and-how-to-use-them)

**1。验证视图**

**SYNTAX:**

```
SELECT VIEW_NAME FROM USER_VIEWS;

        *OR*

SELECT * FROM USER_VIEWS;

```

```
Input : SELECT VIEW_NAME FROM USER_VIEWS;
Output :

```

```
Input : SELECT * FROM USER_VIEWS;
Output :

```

**2。验证序列**

**SYNTAX:**

```
SELECT SEQUENCE_NAME FROM USER_SEQUENCES;

        *OR*

SELECT * FROM USER_SEQUENCES;

```

```
Input : SELECT SEQUENCE_NAME FROM USER_SEQUENCES;
Output :

```

```
Input : SELECT * FROM USER_SEQUENCES;
Output :

```

**3。验证索引**

**SYNTAX:**

```
SELECT INDEX_NAME FROM USER_INDEXES;

        *OR*

SELECT * FROM USER_INDEXS;

```

```
Input : SELECT INDEX_NAME FROM USER_INDEXES;
Output :

```

```
Input : SELECT * FROM USER_INDEXES;
Output :

```

**4。验证表格**

**SYNTAX:**

```
SELECT TABLE_NAME FROM USER_TABLES;

        *OR*

SELECT * FROM USER_TABLES;

```

```
Input : SELECT TABLE_NAME FROM USER_TABLES;
Output :

```

```
Input : SELECT * FROM USER_TABLES;
Output :

```

**5。验证同义词**

**SYNTAX:**

```
SELECT SYNONYM_NAME FROM USER_SYNONYMS;

        *OR*

SELECT * FROM USER_SYNONYMS;

```

```
Input : SELECT SYNONYM_NAME FROM USER_SYNONYMS;
Output : 

```

```
Input : SELECT * FROM USER_SYNONYMS;
Output : 

```

**6。验证触发器**

**SYNTAX:**

```
SELECT TRIGGER_NAME FROM USER_TRIGGERS;

        *OR*

SELECT * FROM USER_TRIGGERS;

```

```
Input : SELECT TRIGGER_NAME FROM USER_TRIGGERS;
Output : 

```

```
Input : SELECT * FROM USER_TRIGGERS;
Output : 

```

***注意:使用*意味着我们需要该数据库对象或触发器的所有属性才能显示**。*