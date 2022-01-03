# SQL | DELETE 语句

> 原文:[https://www.geeksforgeeks.org/sql-delete-statement/](https://www.geeksforgeeks.org/sql-delete-statement/)

SQL 中的 DELETE 语句用于从表中删除现有记录。根据我们在 WHERE 子句中指定的条件，我们可以删除一条记录或多条记录。

**基本语法:**

```
DELETE FROM table_name WHERE some_condition;

table_name: name of the table
some_condition: condition to choose particular record.

```

**注意:**根据我们在 WHERE 子句中提供的条件，我们可以删除单个以及多个记录。如果我们省略 WHERE 子句，那么所有的记录都将被删除，并且表将是空的。

样表:
[![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/table11.jpg)

**示例查询:**

*   **Deleting single record**: Delete the rows where NAME = ‘Ram’. This will delete only the first row.

    ```
    DELETE FROM Student WHERE NAME = 'Ram';

    ```

    **输出:**
    上面的查询将只删除第一行，表**学生**现在看起来像，

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |

*   **Deleting multiple records**: Delete the rows from the table Student where Age is 20\. This will delete 2 rows(third row and fifth row).

    ```
    DELETE FROM Student WHERE Age = 20;

    ```

    **输出:**
    上面的查询将删除两行(第三行和第五行)表**学生**现在看起来像，

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |

*   **Delete all of the records:** There are two queries to do this as shown below,

    ```
    query1: "DELETE FROM Student";

    query2: "DELETE * FROM Student";

    ```

    **输出:**
    表中的所有记录都将被删除，没有剩余的记录可以显示。桌子**学生**会变空！

[SQL 小测验](https://www.geeksforgeeks.org/dbms-gq/sql-gq/)

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。