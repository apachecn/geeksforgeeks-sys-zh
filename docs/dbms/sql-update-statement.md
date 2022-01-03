# SQL |更新语句

> 原文:[https://www.geeksforgeeks.org/sql-update-statement/](https://www.geeksforgeeks.org/sql-update-statement/)

SQL 中的 UPDATE 语句用于更新数据库中现有表的数据。根据我们的需求，我们可以使用 update 语句更新单个列和多个列。

**基本语法**

```
UPDATE table_name SET column1 = value1, column2 = value2,... 
WHERE condition;  table_name: name of the table
column1: name of first , second, third column....
value1: new value for first, second, third column....
condition: condition to select the rows for which the 
values of columns needs to be updated.
```

**注意:**在上面的查询中， **SET** 语句用于为特定列设置新值， **WHERE** 子句用于选择需要更新列的行。如果我们没有使用 WHERE 子句，那么所有行的**列都将被更新。所以 WHERE 子句用于选择特定的行。
[![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/table11.jpg)**

**示例查询**

*   **Updating single column**: Update the column NAME and set the value to ‘PRATIK’ in all the rows where Age is 20.

    ```
    UPDATE Student SET NAME = 'PRATIK' WHERE Age = 20;

    ```

    **输出:**
    该查询将更新两行(第三行和第五行)并且表**学生**现在看起来像，

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | three | 我在练习 | 罗塔克 | XXXXXXXXXX | Twenty |
    | four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
    | three | 我在练习 | 罗塔克 | XXXXXXXXXX | Twenty |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |

*   **Updating multiple columns:** Update the columns NAME to ‘PRATIK’ and ADDRESS to ‘SIKKIM’ where ROLL_NO is 1.

    ```
    UPDATE Student SET NAME = 'PRATIK', ADDRESS = 'SIKKIM' WHERE ROLL_NO = 1;

    ```

    **输出** :
    上面的查询将更新第一行的两列，表**学生**现在看起来像，

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 我在练习 | 锡金 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | three | 我在练习 | 罗塔克 | XXXXXXXXXX | Twenty |
    | four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
    | three | 我在练习 | 罗塔克 | XXXXXXXXXX | Twenty |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |

    **注意:**为了更新多列，我们使用了逗号(，)来分隔两列的名称和值。

*   **Omitting WHERE clause:** If we omit the WHERE clause from the update query then all of the rows will get updated.

    ```
    UPDATE Student SET NAME = 'PRATIK';

    ```

    **输出:**
    表格**学生**现在看起来像，

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 我在练习 | 德里 | XXXXXXXXXX | Eighteen |
    | Two | 我在练习 | 古尔冈 | XXXXXXXXXX | Eighteen |
    | three | 我在练习 | 罗塔克 | XXXXXXXXXX | Twenty |
    | four | 我在练习 | 德里 | XXXXXXXXXX | Eighteen |
    | three | 我在练习 | 罗塔克 | XXXXXXXXXX | Twenty |
    | Two | 我在练习 | 古尔冈 | XXXXXXXXXX | Eighteen |

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。