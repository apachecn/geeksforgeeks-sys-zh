# SQL 中的 DUAL 表

> 原文:[https://www.geeksforgeeks.org/dual-table-in-sql/](https://www.geeksforgeeks.org/dual-table-in-sql/)

可能有这样一种情况，我们想要查询不是来自表的东西。例如，获取当前日期或查询一个简单的算术表达式，如 2+2。

在甲骨文中，FROM 子句并不例外。如果我们不在甲骨文中写 FROM 子句，我们会得到一个错误。

**示例-1: Oracle 查询**

```
SELECT SYSDATE;
```

**输出–**

```
ORA-00923: FROM keyword not found where expected
```

**示例-2: Oracle 查询**

```
SELECT 'GeeksforGeeks';
```

**输出–**

```
ORA-00923: FROM keyword not found where expected
```

**DUAL :**
是 Oracle Database 随数据字典自动创建的表。DUAL 在用户 SYS 的模式中，但所有用户都可以通过名称 DUAL 进行访问。它有一列 DUMMY，定义为 VARCHAR2(1)，并包含一行 x 值。

**示例:Oracle 查询**

```
SELECT * 
FROM DUAL ;
```

**输出–**

```
X 
```

从 DUAL 表中进行选择对于使用 SELECT 语句计算常量表达式非常有用。因为 DUAL 只有一行，所以常量只返回一次。

**甲骨文查询:**

```
SELECT 'GeeksforGeeks' 
AS NAME FROM DUAL;
```

**输出–**

```
GeeksforGeeks 
```

**甲骨文查询:**

```
SELECT 2+2 
FROM DUAL;
```

**输出:**

```
2+2 = 4 
```

其他几个数据库，包括 MS SQL Server、MySQL、PostgreSQL 和 SQLite，都允许省略 FROM 子句。这个异常是其他数据库中没有像 DUAL 这样的伪表的原因。