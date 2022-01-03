# SQL 完整格式

> 原文:[https://www.geeksforgeeks.org/sql-full-form/](https://www.geeksforgeeks.org/sql-full-form/)

[SQL](https://www.geeksforgeeks.org/sql-tutorial/) 是一种声明性语言，它以关系代数为基础。它是所有主要商业数据库支持的标准化语言。查询优化器是 SQL 的一个重要组成部分，它接受 SQL 查询的输入并以最快的方式执行它。

以下是 SQL 查询的主要分类:

1.  **数据操作语言(DML)–**
    它处理与插入、删除和修改行相关的查询。
2.  **数据定义语言(DDL)–**
    它处理表和视图定义的创建、删除和修改。

基本的 SQL 查询具有以下语法:

```
SELECT (attribute list)
FROM   (table list)
[WHERE (condition)]
[GROUP BY (grouping attributes)]
[HAVING (group condition)]
[ORDER BY (attribute list)] 
```

其中选择和从条款是强制性的。

1.  SELECT 子句列出了要检索的属性。
2.  from 子句指定了所有表
3.  WHERE 子句指定从这些表中选择记录的条件，包括连接条件。
4.  按指定的分组属性分组
5.  HAVING 指定了检索组的条件。

各种[聚合器功能](https://www.geeksforgeeks.org/aggregate-functions-in-sql/) COUNT、SUM、MIN、MAX 和 AVG 可以结合分组。ORDER BY 指定显示查询结果的顺序。

**特征:**

*   表，也称为关系，由一个名称表示，长度不超过 20 个字符。
*   表名和列字段应该具有唯一的名称。
*   在表定义时，字段列表用逗号分隔，每个字段名由一个数据类型后跟一个用括号括起来的长度属性组成。
*   SQL 语句必须以分号结束。

**优势:**

*   高性能。
*   轻松兼容大多数数据库，如微软 Access、微软 SQL server。
*   在创建新的数据库表和删除冗余表方面具有良好的灵活性。
*   可以处理大型记录和多个事务。
*   以开源编程语言的形式易于访问。
*   高安全性:使用权限可以轻松保护表、过程和视图
*   易于学习和理解的数据

**缺点:**

*   复杂的界面来理解和处理它。
*   设置所需的成本更高。
*   这是一种依赖于平台的复合语言。
*   每个记录存储都需要额外的空间。
*   由于隐藏的权限，对数据库的部分控制。