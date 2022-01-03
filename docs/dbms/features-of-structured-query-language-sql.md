# 结构化查询语言(SQL)的特性

> 原文:[https://www . geesforgeks . org/features-of-structured-query-language-SQL/](https://www.geeksforgeeks.org/features-of-structured-query-language-sql/)

[结构化查询语言(SQL)](https://www.geeksforgeeks.org/structured-query-language/) 是用于在数据库中编写查询的标准语言。它获得了国际标准化组织(ISO)和美国国家标准协会(ANSI)的批准。

SQL 包含一些重要的特性，它们是:

1.  **数据定义语言(DDL):**
    它包含定义数据的命令。这些命令是:

*   **创建:**用于创建表格。
    **语法:**

```
create table 
tablename(attribute1 datatype......attributen datatype); 
```

*   **删除:**用于删除包含所有属性的表。
    **语法:**

```
drop table tablename; 
```

*   **alter:** alter 是修饰表结构的保留字。
    **语法:**

```
alter table 
tablename add(new column1 datatype......new columnx datatype); 
```

*   **重命名:**可以使用保留者“重命名”
    **语法:**来更改表名

```
rename old table name to new table name; 
```

2。**数据操作语言(DML):**
数据操作语言包含用于操作数据的命令。
命令是:

*   **插入:**该命令一般用在 create 命令之后，将一组值插入表中。
    **语法:**

```
insert into tablename values(attribute1 datatype);
:
:
:
insert into tablename values (attributen datatype); 
```

*   **delete:** 用于从表中删除特定元组或行或基数的命令。
    **语法:**

```
delete from tablename where condition; 
```

*   **更新:**更新表中的元组。
    **语法:**

```
update tablename set tuplename='attributename'; 
```

*   **Triggers:** 
    Triggers are actions performed when certain conditions are met on the data. 

    触发器由三部分组成。

    *   **(一)。事件–**数据库中激活触发器的变化是事件。

    *   **(二)。条件–**触发器激活时运行的查询或测试。

    *   **(三)。动作–**当触发器被激活且条件满足时执行的程序。

2。**客户端服务器执行和远程数据库访问:**
客户端服务器技术维护客户端(多)和服务器(一)的多对一关系。我们在 SQL 中有控制客户端应用程序如何通过网络访问数据库的命令。

3。**安全和身份验证:**
SQL 提供了一种控制数据库的机制，这意味着它确保只向用户显示数据库的特定细节，并且原始数据库受到数据库管理系统的保护。

4。**嵌入式 SQL:**
SQL 提供了在运行时从宿主语言中嵌入 C、COBOL、Java 等语言进行查询的功能。

5。**事务控制语言:**
事务是数据库管理系统的一个重要元素，为了控制事务，使用了 TCL，它有提交、回滚和保存点等命令。

*   **提交:**只要数据库一致，它就随时保存数据库。
    **语法:**

```
commit; 
```

*   **回滚:**回滚/撤销到事务的上一点。
    **语法:**

```
rollback; 
```

*   **保存点:**它返回到上一个事务，而不返回到整个事务。
    **语法:**

```
savepoint; 
```

6。**高级 SQL:**
目前的特性包括面向对象的特性，如递归查询、决策支持查询，以及查询支持领域，如数据挖掘、空间数据和可扩展标记语言。