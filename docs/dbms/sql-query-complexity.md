# SQL 查询复杂度

> 原文:[https://www.geeksforgeeks.org/sql-query-complexity/](https://www.geeksforgeeks.org/sql-query-complexity/)

[结构化查询语言(SQL)](https://www.geeksforgeeks.org/structured-query-language/) 是用于查询关系数据库的语言。典型的关系数据库由表组成，其中每个表都有行和列。每一列都有特定类型的数据。取决于 SQL 查询复杂性的因素。

**示例–**

```
select * 
from employee 
where id = 77
```

查询可以通过三种不同方式找到结果–

1.  **O(1)**—id 上的哈希索引，或者来自上一次查询的 id = 77 上的缓存结果。
2.  **O(n)**–进行全面扫描，查看每一行，但找不到任何结果。
3.  **O(log(n))**–对 id 进行排序，做一个二分搜索法。

查询的复杂性完全取决于 SQL 引擎将如何处理查询。如果我们的雇员表有 100000000000 行数据，我们需要找出雇员 id 为 77 的行。如果我们扫描整张桌子，那就要花很长时间。如果我们对表进行排序，并对这个表进行二分搜索法运算，那么我们需要大约 36 次查找(1000000000000 的对数基数 2 是~36)来找出我们的值。但是整理桌子需要一些时间。这完全取决于 sql 引擎的优化者。

如果你想了解更多 [SQL 引擎查询处理](https://www.geeksforgeeks.org/sql-query-processing/)，我会推荐这个。

**写好查询要牢记的事情:**

*   **Limit your result –**
    When you can not avoid filtering down your select statement, then you can consider limiting your result. You can limit your result by using limit, top

    **示例–**

    ```
    select TOP 3 
    from employee
    ```

    ```
    select * 
    from employee limit 10
    ```

*   Don’t make the query to be more complex. Try to keep them simple and efficient.

    **示例–**
    考虑以下查询:

    ```
    select * 
    from employee 
    where id = 77 or id = 85 or id = 69
    ```

    因此，您可以通过在中使用**来替换操作员**

    ```
    select * 
    from employee 
    where id in (77, 85, 69)
    ```

*   选择*以避免浪费服务器、数据库和网络资源，尤其是当一个连接至少有一列两次时。
*   理解聚合停止思考循环。
    蕴象–**计数**、**平均值**等。