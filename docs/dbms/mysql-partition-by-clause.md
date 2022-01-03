# MySQL | PARTITION BY 子句

> 原文:[https://www.geeksforgeeks.org/mysql-partition-by-clause/](https://www.geeksforgeeks.org/mysql-partition-by-clause/)

一个 **PARTITION BY** 子句用于将表的行划分成组。当我们必须使用一个组的其他行对该组的单个行执行计算时，这很有用。

*   它总是用在 OVER()子句中。
*   由 partition 子句形成的分区也称为**窗口**。
*   此子句仅适用于 windows 函数。像- RANK()、LEAD()、LAG()等。
*   如果 OVER()子句中省略了此子句，则整个表被视为单个分区。

**语法:**
Partition 子句的语法是-

```
Window_function ( expression ) 
       Over ( partition by expr [order_clause] [frame_clause] ) 

```

这里，order _ 子句和 frame _ 子句是可选的。

**expr** 可以是列名，也可以是 MySQL 中的内置函数。

但是，标准的 SQL 只允许表达式中的列名。

**示例:**

考虑一下，一张表“**黑客**”:

<center>

| h_id | hgame | 挑战 id | 得分 |
| --- | --- | --- | --- |
| three | 舒卜 | One hundred and eleven | Twenty |
| Two | 哦，天啊 | One hundred and eleven | Eighty |
| five | 克里提克 | One hundred and twelve | Forty |
| five | 克里提克 | One hundred and fourteen | Ninety |
| four | 塔斯哈尔 | One hundred and twelve | Thirty |
| one | 聚会 | One hundred and twelve | Forty |

</center>

我们必须找到黑客在每个挑战中的排名。这意味着我们必须列出所有参与挑战的黑客以及他们在挑战中的排名。

**查询:**

```
select challenge_id, h_id, h_name, score, 
   dense_rank() over ( partition by challenge_id order by score desc ) 
       as "rank", from hacker;

```

**说明:**

在上面的查询中， ***通过*** 子句进行分区，将表划分为具有相同 challenge_id 的组。

***按*排序**会按“分数”降序排列每个分区的黑客。

***【over()***子句定义了如何对表的行进行划分和排序，该表将由窗口函数 rank()处理。

***密 _rank()*** 是一个窗口函数，它会在挑战的有序分区中分配等级。如果两个黑客有相同的分数，那么他们将被分配相同的等级。

**输出:**

<center>

| 挑战 id | h_id | hgame | 得分 | 等级 |
| --- | --- | --- | --- | --- |
| One hundred and eleven | Two | 哦，天啊 | Eighty | one |
| One hundred and eleven | three | 舒卜 | Twenty | Two |
| One hundred and twelve | five | 克里提克 | Forty | one |
| One hundred and twelve | one | 聚会 | Forty | one |
| One hundred and twelve | four | 塔斯哈尔 | Thirty | Two |
| One hundred and fourteen | five | 克里提克 | Ninety | one |

</center>

因此，我们得到了所有黑客的名单以及他们在个人挑战中的排名。