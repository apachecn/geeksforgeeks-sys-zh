# SQL AND 和 OR 运算符

> 原文:[https://www.geeksforgeeks.org/sql-and-and-or-operators/](https://www.geeksforgeeks.org/sql-and-and-or-operators/)

在 SQL 中，AND & OR 运算符用于过滤数据并根据条件获得精确的结果。SQL**和** & **或** 运算符也用于组合多个条件。这两个运算符可以组合在一起测试 SELECT、INSERT、UPDATE 或 DELETE 语句中的多个条件。

在组合这些条件时，使用括号很重要，这样数据库就知道评估每个条件的顺序。

*   AND 和 OR 运算符与 WHERE 子句一起使用。
*   这两个运算符称为合取运算符。

### **和运算符:**

此运算符仅显示条件条件 1 和条件 2 评估为真的那些记录。

**语法:**

```
SELECT * FROM table_name WHERE condition1 AND condition2 and ...conditionN;

table_name: name of the table
condition1,2,..N : first condition, second condition and so on
```

### **或运算符:**

此运算符显示条件 1 和条件 2 中任一条件评估为真的记录。也就是说，条件 1 为真或条件 2 为真。
**语法:**

```
SELECT * FROM table_name WHERE condition1 OR condition2 OR... conditionN;

table_name: name of the table
condition1,2,..N : first condition, second condition and so on

```

现在，我们考虑一个表数据库来演示具有多种情况的 AND & OR 运算符:

![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)

如果假设我们想从学生表中获取所有记录，其中年龄是 18 岁，地址是德里。那么查询将是:

**查询**:

```
SELECT * FROM Student WHERE Age = 18 AND ADDRESS = 'Delhi';
```

**输出:**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
| four | SURESH | 德里 | XXXXXXXXXX | Eighteen |

再举一个例子，从学生表中获取所有的记录，名字是内存，年龄是 18 岁。

**查询:**

```
SELECT * FROM Student WHERE Age = 18 AND NAME = 'Ram';
```

**输出:**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |

从学生表中获取所有记录，其中名称是内存或名称是 SUJIT。

**查询:**

```
SELECT * FROM Student WHERE NAME = 'Ram' OR NAME = 'SUJIT';
```

**输出:**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |

从“姓名”为“随机”或“年龄”为 20 的“学生”表中获取所有记录。

**查询:**

```
SELECT * FROM Student WHERE NAME = 'Ram' OR Age = 20;
```

**输出:**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |

### **结合“与”和“或”:**

我们可以以下面的方式组合 AND 和 OR 运算符来编写复杂的查询。

**语法:**

```
SELECT * FROM table_name WHERE condition1 AND (condition2 OR condition3);
```

举个例子，从学生表中获取所有记录，其中年龄为 18 岁，姓名为 Ram 或 RAMESH。

**查询:**

```
SELECT * FROM Student WHERE Age = 18 AND (NAME = 'Ram' OR NAME = 'RAMESH');
```

**输出:**

<figure class="table">

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
| Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |

</figure>

</figure>

</figure>

</figure>

</figure>