# MS SQL Server–类型转换

> 原文:[https://www . geesforgeks . org/ms-SQL-server-type-conversion/](https://www.geeksforgeeks.org/ms-sql-server-type-conversion/)

有各种各样的数据库收集了大量的数据，我们知道数据是以有组织的方式排列的。[数据库](https://www.geeksforgeeks.org/introduction-of-dbms-database-management-system-set-1/)中的数据可能是数字或字母类型，而少数可能是字母数字(字母和数字的组合)，其他可能是文本、图像等。必须按照实际所属的类别/类型进行排序的数据称为数据类型。数据类型的概念帮助我们对数据进行分类。

**示例:**考虑下面给出的模式，如下所示。

**创建表格:**

```
create table student
(
rollnumber int, 
name varchar2(30), 
marks int
);
```

上面的模式将滚动号作为第一个属性。它被指定为整数，因为卷号通常是按顺序排列的。马克也是如此。该名称被指定为 varchar，最多包含 20 个字符。它也可以容纳字符和数字。

**插入数据:**表中插入了一个值，如下所示。

```
insert into student values('120' ,'Bam' , '2T');
```

由于出现错误，该值不会插入到表中。marks 属性属于整数，但插入了一个字符和一个数字，造成了错误。

**类型转换:**从一种数据类型转换为另一种数据类型的过程称为类型转换或类型转换。有以下两种类型转换。

*   **Implicit conversion:** The conversion that one data type can be automatically converted to another data type is called implicit conversion.
*   **Explicit conversion:** The conversion of data types that must be manually converted is called explicit conversion.

显式转换必须使用**转换**或**转换**函数在 SQL Server 中完成。语法如下。

```
cast(old _datatype as new_datatypename);
convert(old_datatype as new_datatypename);
```

上述任何一个函数都可以用于显式转换。如果一个转换函数符合国际标准化组织(ISO)的标准，那么它可以用来代替转换，如果我们在功能上利用风格的优势，那么它也可以反过来使用。

**例:**

```
cast(150 as decimal2,2));
```

150 是整数类型，必须转换为精度为 2、小数位数为 2 的浮点数。