# 从日期开始查找年份的 SQL 查询

> 原文:[https://www . geesforgeks . org/SQL-查询查找年初至今/](https://www.geeksforgeeks.org/sql-query-to-find-the-year-from-date/)

**概述:**
借助一个例子，你就能理解 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 中的【从日期中查找年份】的实现了。在这里我们将看到，如何借助于 SQL 查询在 MS SQL Server 的数据库表中从给定的日期中查找或提取年份。为了演示，我们将在名为“极客”的数据库中创建一个 *demo_orders* 表。

**实现从日期开始查找年份的 SQL 查询的步骤:**
这里，我们将讨论实现从日期开始查找年份的 SQL 查询的步骤如下。

**第一步:创建数据库:**
使用下面的 SQL 语句创建一个名为 geeks 的数据库，如下所示。

```
CREATE DATABASE geeks;
```

**步骤 2:使用数据库:**
使用下面的 SQL 语句将数据库上下文切换到极客，如下所示。

```
USE geeks;
```

**第三步:创建表:**
我们的极客数据库中有以下演示表。

```
CREATE TABLE demo_orders(
 ORDER_ID INT IDENTITY(1,1) PRIMARY KEY, 
 --IDENTITY(1,1) is same as AUTO_INCREMENT in MySQL.
 --Starts from 1 and increases by 1 with each inserted row.
 ITEM_NAME VARCHAR(30) NOT NULL,
 ORDER_DATE DATE
);
```

**第 4 步:验证表:**
可以使用下面的语句查询创建的表的描述，如下所示。

```
EXEC SP_COLUMNS demo_orders;
```

**输出:**

<figure class="table">

| 表名 | 列名 | 数据类型 | 类型名 | 精确 | 长度 | 评论 |
| --- | --- | --- | --- | --- | --- | --- |
| 演示订单 | 订单标识 | four | 整数标识 | Ten | four | 空 |
| 演示订单 | 项目名称 | Twelve | 可变长字符串 | Thirty | Thirty | 空 |
| 演示订单 | 订单 _ 日期 | -9 | 日期 | Ten | Twenty | 空 |

**第 5 步:向表中添加数据:**
使用下面的语句向 demo_orders 表中添加数据，如下所示。

```
INSERT INTO demo_orders 
--no need to mention columns explicitly as we are inserting into all columns and ID gets 
--automatically incremented.
VALUES
('Maserati', '2007-10-03'),
('BMW', '2010-07-23'),
('Mercedes Benz', '2012-11-12'),
('Ferrari', '2016-05-09'),
('Lamborghini', '2020-10-20');
```

**第 6 步:验证插入的数据:**
要验证表格的内容，请使用以下语句。

```
SELECT * FROM demo_orders;
```

**输出:**

<figure class="table">

| 订单标识 | 项目名称 | 订单 _ 日期 |
| --- | --- | --- |
| one | 玛莎拉蒂 | 2007-10-03T00:00:00.000Z |
| Two | 德国宝马汽车公司(Bavarian Motor Works) | 2010-07-23T00:00:00.000Z |
| three | 奔驰 | 2012-11-12T00:00:00.000Z |
| four | 法拉利 | 2016-05-09T00:00:00.000Z |
| five | 兰博基尼 | 2020-10-20T00:00:00.000Z |

**第 7 步:执行查询以查找起始日期的年份:**
现在让我们借助 Year()函数查找订单的年份，ITEM_NAME 为“玛莎拉蒂”。下面是从给定日期检索年份的语法。

**语法–**

```
SELECT YEAR(<date_string>);
--or within a table--
SELECT YEAR(<column_table>) FROM <table_name>;
```

**示例–**

```
SELECT YEAR(ORDER_DATE) AS YEAR_OF_ORDER
FROM demo_orders
WHERE ITEM_NAME='Maserati';
```

**输出:**

<figure class="table">

| 订单年份 |
| --- |
| Two thousand and seven |

**第 8 步:实现查询以从日期中查找日、月和年:**
同样，我们可以使用 day()和 month()函数来查找给定日期的相应日和月。

**示例–**

```
SELECT day(order_date)[day], --here [day] is the identifier name for the column in the output.
       month(order_date)[month], 
       year(order_date)[year]
FROM demo_orders 
WHERE ITEM_NAME='Lamborghini';
```

**输出:**

<figure class="table">

| 天 | 月 | 年 |
| --- | --- | --- |
| Twenty | Ten | Two thousand and twenty |

</figure>

</figure>

</figure>

</figure>