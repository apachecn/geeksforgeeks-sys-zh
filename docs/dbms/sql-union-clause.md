# SQL |联合条款

> 原文:[https://www.geeksforgeeks.org/sql-union-clause/](https://www.geeksforgeeks.org/sql-union-clause/)

Union 子句用于组合两个单独的 select 语句，并将结果集生成为两个 select 语句的并集。
**注:**

1.  两个 select 语句中使用的字段必须顺序相同、编号相同、数据类型相同。
2.  Union 子句在结果集中产生不同的值，要获取重复的值，必须使用 UNION ALL，而不仅仅是 UNION。

**基本语法:**

```
SELECT column_name(s) FROM table1 UNION SELECT column_name(s) FROM table2;

Resultant set consists of distinct values.

```

```
SELECT column_name(s) FROM table1 UNION ALL SELECT column_name(s) FROM table2;

Resultant set consists of duplicate values too.

```

[![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/table11.jpg)

[![table12](img/097eb0c76bb102d02b0717c299d32bdc.png)](https://media.geeksforgeeks.org/wp-content/uploads/table12.jpg)

**查询**

*   To fetch distinct ROLL_NO from Student and Student_Details table.

    ```
    SELECT ROLL_NO FROM Student UNION SELECT ROLL_NO FROM Student_Details; 

    ```

    输出:

    | **滚动 _ 否** |
    | --- |
    | one |
    | Two |
    | three |
    | four |

*   To fetch ROLL_NO from Student and Student_Details table including duplicate values.

    ```
    SELECT ROLL_NO FROM Student UNION ALL SELECT ROLL_NO FROM Student_Details; 

    ```

    输出:

    | **滚动 _ 否** |
    | --- |
    | one |
    | Two |
    | three |
    | four |
    | three |
    | Two |

*   To fetch ROLL_NO , NAME from Student table WHERE ROLL_NO is greater than 3 and ROLL_NO , Branch from Student_Details table WHERE ROLL_NO is less than 3 , including duplicate values and finally sorting the data by ROLL_NO.

    ```
    SELECT ROLL_NO,NAME FROM Student WHERE ROLL_NO>3 
    UNION ALL
    SELECT ROLL_NO,Branch FROM Student_Details WHERE ROLL_NO<3
    ORDER BY 1; 

    Note:The column names in both the select statements can be different but the
     data type must be same.And in the result set the name of column used in the first
     select statement will appear. 

    ```

    输出:

    | **滚动 _ 否** | **名称** |
    | --- | --- |
    | one | 信息技术 |
    | Two | 计算机科学 |
    | four | SURESH |

本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。