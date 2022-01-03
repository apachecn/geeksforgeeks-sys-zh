# 关系查询评估|集合 1

> 原文:[https://www . geesforgeks . org/relational-query-evaluation-set-1/](https://www.geeksforgeeks.org/relational-query-evaluation-set-1/)

需要将关系查询转换为代数表达式。对该表达式进行运算，以便接收最终输出。存在的[关系代数运算符](https://www.geeksforgeeks.org/basic-operators-in-relational-algebra-2/)有联合、选择、连接、项目等。这些用于制定关系查询以获得足够的结果。分组、分区和聚合都是[关系查询](https://www.geeksforgeeks.org/query-optimization-in-relational-algebra/)的一部分。

**实现:**
选择合适的算法对于优化存储数据的磁盘的寿命和性能是必要的。如果在磁盘上执行大量读写操作(数据修改和更新)，由于磨损，其寿命会缩短。

**[选择符](https://www.geeksforgeeks.org/select-operation-in-relational-algebra/) :**

1.  **一个选择条件–**
    如果需要使用 select 运算符根据条件选择特定的关系元组，可以做以下事情。如果只有一个选择条件，那么我们需要检查索引的存在。如果属性上存在索引，我们可以很容易地找到基于这些索引的选择，因为索引提供了可用于搜索的记录和块指针。由于任何原因，如果没有索引，那么需要搜索整个文件进行选择。

*   **Multiple Conjunctive Selection Condition –**
    In the case of multiple conjunctive selection condition, if none of attributes have any index, complete file scan needs to be done for selection of relevant tuples. However, if any of attributes do have index, then we need to go to relevant attribute and select tuples whose values for attribute are equivalent to given condition, and then in those records, other conjunctive conditions can be checked.*   **Multiple Disjunctive Selection Condition –**
    In case attributes have multiple disjunctive selection condition, it is of no use if only one attribute has index, rather it is necessary that all attributes have index. Otherwise, complete file scan is necessary to get selections.*   **Selection of Predicates –**
    If index is present for multiple attributes, one can choose highly selective attribute. This can be done by using Selectivity. The selectivity of any particular attribute is ratio of the number of records satisfying condition to total number of records. The selectivity can range anywhere between and including 0 and 1\. The condition is rated as highly selective if it has low value of selectivity.

    对于条件的结合，选择选择性值最小的属性。找到对应于条件的元组，然后在其上实现其他条件。数据库使用时，可以记录选择性值或其估计值。可以放在数据库目录中。数据库目录(数据库目录)由元数据和关于数据的相关统计数据组成，例如选择性。这些由查询优化器使用，查询优化器是[关系数据库管理系统架构](https://www.geeksforgeeks.org/rdbms-architecture/)的一部分。

    估计选择性的公式如下:

    *   如果是关键属性，选择性大致为–

        ```
        1 / (total db records)
        ```

    *   在非关键属性的情况下，选择性大致为–

        ```
        1 / distinct values of columns
        ```

    数据库管理系统中也存在直方图。直方图在横轴上表示不同的属性值或属性值范围。而在纵轴上，它表示与范围内的值相对应的记录数。我们可以使用直方图来估计数据库中与给定条件相对应的记录数量。这些估计也可以离线记录。

    请参考–[关系查询评估|第 2 集](https://www.geeksforgeeks.org/relational-query-evaluation-set-2/)