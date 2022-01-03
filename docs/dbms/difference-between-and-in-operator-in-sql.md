# SQL 中=和 IN 运算符的区别

> 原文:[https://www . geesforgeks . org/SQL 中运算符的区别/](https://www.geeksforgeeks.org/difference-between-and-in-operator-in-sql/)

先决条件–[SQL 命令](https://www.geeksforgeeks.org/sql-tutorial/)
在本文中，我们将看到 [=](https://www.geeksforgeeks.org/sql-where-clause/) 和 [IN 运算符](https://www.geeksforgeeks.org/sql-between-in-operator/)在 SQL 中的区别。

**1。=运算符:**
运算符与 SQL 中的 Where 子句一起使用。
例如，考虑下面给出的学生表，

<center>

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | xxxxxxxxxx | Eighteen |
| Two | RAMESH | 古尔冈 | xxxxxxxxxx | Eighteen |
| three | SUJIT | 罗塔克 | xxxxxxxxxx | Twenty |
| four | SURESH | 德里 | xxxxxxxxxx | Eighteen |
| three | SUJIT | 罗塔克 | xxxxxxxxxx | Twenty |
| Two | RAMESH | 古尔冈 | xxxxxxxxxx | Eighteen |

</center>

**查询:**
获取地址为德里或罗塔克的学生记录。
使用=运算符的 SQL 查询将是:

```
 SELECT * 
FROM Student 
WHERE ADDRESS='Delhi' OR ADDRESS='ROHTAK'; 
```

**输出:**

<center>

| 滚动 _ 否 | 名字 | 地址 | 电话 | 年龄 |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | xxxxxxxxxx | Eighteen |
| three | SUJIT | 罗塔克 | xxxxxxxxxx | Twenty |
| four | SURESH | 德里 | xxxxxxxxxx | Eighteen |
| three | SUJIT | 罗塔克 | xxxxxxxxxx | Twenty |

</center>

**2。输入运算符:**
输入运算符与 Where 子句一起使用，以测试表达式是否匹配值列表中的任何值。使用 IN 运算符的优点是避免使用多个 or 运算符。

**查询:**
获取地址为德里或罗塔克的学生记录。
使用输入运算符的 SQL 查询将是，

```
SELECT * 
FROM Student 
WHERE ADDRESS IN ('Delhi', 'ROHTAK'); 
```

**输出:**

<center>

| 滚动 _ 否 | 名字 | 地址 | 电话 | 年龄 |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | xxxxxxxxxx | Eighteen |
| three | SUJIT | 罗塔克 | xxxxxxxxxx | Twenty |
| four | SURESH | 德里 | xxxxxxxxxx | Eighteen |
| three | SUJIT | 罗塔克 | xxxxxxxxxx | Twenty |

</center>

**运算符=和输入之间的差异:**

<center>

| **=操作员** | **输入操作符** |
| 它允许比较具有单个值的属性。 | 它允许比较具有多个值的属性。对于单值比较，行为与=相同。 |
| 对于多重比较，我们还必须使用适当的运算符。(即连接、或、与等。) | 不需要额外使用操作员。 |
| 在子查询返回单个值作为结果的情况下很有用。 | 在子查询返回多个值作为结果的情况下很有用。 |
| 如果子查询有多个结果，它将生成一个错误。 | 如果子查询有多个结果，它不会生成错误。 |
| 它比输入操作器更快。 | IN 子句比=慢，因为它与多个值进行比较，直到条件满足。 |

</center>