# 结构化查询语言(SQL)

> 原文:[https://www.geeksforgeeks.org/structured-query-language/](https://www.geeksforgeeks.org/structured-query-language/)

结构化查询语言是一种标准的数据库语言，用于创建、维护和检索关系数据库。以下是一些关于 SQL 的有趣事实。

*   SQL 不区分大小写。但是建议使用大写字母的关键字(如 SELECT、UPDATE、CREATE 等)，使用小写字母的用户定义的东西(如表名、列名等)。
*   我们可以在任何一行的开头使用“-”(双连字符)在 SQL 中编写注释。
*   SQL 是关系数据库的编程语言(解释如下)，如 MySQL、Oracle、Sybase、SQL Server、Postgre 等。其他非关系数据库(也称为 NoSQL)如蒙古数据库、动力数据库等不使用 SQL
*   Although there is an ISO standard for SQL, most of the implementations slightly vary in syntax. So we may encounter queries that work in SQL Server but do not work in MySQL.

    。

    **什么是关系数据库？**

    关系数据库意味着数据以关系(表)的形式存储和检索。表 1 显示了只有一个名为 **STUDENT** 的关系数据库，其中存储了学生的 **ROLL_NO** 、 **NAME** 、 **ADDRESS** 、 **PHONE** 和 **AGE** 。

    **学生**

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
    | Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen |
    | three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |
    | four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

    **表 1**

    这些是关系中使用的一些重要术语。

    **属性:**属性是定义关系的属性。例如: **ROLL_NO** 、 **NAME** 等。

    **元组:**关系中的每一行都称为元组。上述关系包含 4 个元组，其中一个元组如下所示:

    | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |

    **度:**关系中属性的个数称为关系的度。上面定义的**学生**关系为 5 级。

    **基数:**关系中元组的数量称为基数。上面定义的**学生**关系的基数为 4。

    **列:**列表示特定属性的一组值。 **ROLL_NO** 一栏摘自关系学生。

    | **滚动 _ 否** |
    | one |
    | Two |
    | three |
    | four |

    处理关系数据库的查询可以分为以下几类:

    **数据定义语言:**用于定义数据库的结构。例如；创建表格、添加列、删除列等等。

    **数据操作语言:**用于操作关系中的数据。例如:插入、删除、更新等等。

    **数据查询语言:**用于从关系中提取数据。例如:挑选

    因此，首先我们将考虑数据查询语言。从关系数据库中检索的一般查询是:

    1.  **从 R2 R1 选择** [ **DISTINCT** ]属性列表**。空间**
    2.  [ **其中**条件]
    3.  [ **分组依据**(属性)[ **具备**条件]]
    4.  【**订单 BY** (属性)【**desc**】；

    如果要从关系数据库中检索，由语句 1 表示的部分查询是必需的。[]中的语句是可选的。我们将在表 1 所示的关系上查看可能的查询组合。

    **案例 1:** 如果要检索所有学生的属性 **ROLL_NO** 和 **NAME** ，查询将为:

    ```
    SELECT ROLL_NO, NAME FROM STUDENT;
    ```

    | **滚动 _ 否** | **名称** |
    | one | 随机存取存储 |
    | Two | RAMESH |
    | three | SUJIT |
    | four | SURESH |

    **案例 2:** 如果要检索 **ROLL_NO** 大于 2 的学生的 **ROLL_NO** 和 **NAME** ，查询将为:

    ```
    SELECT ROLL_NO, NAME FROM STUDENT 
    WHERE ROLL_NO>2;
    ```

    | **滚动 _ 否** | **名称** |
    | three | SUJIT |
    | four | SURESH |

    **案例 3:** 如果我们想要检索学生的所有属性，我们可以写*来代替将所有属性写成:

    ```
    SELECT * FROM STUDENT 
    WHERE ROLL_NO>2;
    ```

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |
    | four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

    **案例 4:** 如果我们想用 **AGE** 来表示关系的升序，我们可以用 order by 子句表示为:

    ```
    SELECT * FROM STUDENT ORDER BY AGE;
    ```

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | one | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
    | Two | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen |
    | four | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |
    | three | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |

    **注:**按**年龄**订购相当于按**年龄** ASC 订购。如果我们想要按照 **AGE** 的降序检索结果，我们可以使用 ORDER BY **AGE** DESC。

    **案例 5:** 如果我们想要检索属性或属性组的不同值，distinct 的用法如下:

    ```
    SELECT DISTINCT ADDRESS FROM STUDENT;
    ```

    | **地址** |
    | 德里 |
    | 古尔冈 |
    | 罗塔克 |

    如果不使用 DISTINCT，那么在结果集中会重复两次 DELHI。在理解 GROUP BY 和 HAVING 之前，我们需要了解 SQL 中的聚合函数。

    **强化函数:**聚合函数用于对关系的数据值进行数学运算。SQL 中使用的一些常见聚合函数有:

    *   **COUNT:** Count 函数用于统计关系中的行数。例如；

    ```
    SELECT COUNT (PHONE) FROM STUDENT;
    ```

    | **计数(电话)** |
    | four |

    *   **SUM:** SUM 函数用于将关系中某个属性的值相加。例如；

    **从**学生中选择 **和**(年龄)**；**

    | **总和(年龄)** |
    | Seventy-four |

    同样，可以使用最小、最大和 AVG。正如我们在上面看到的，所有聚合函数只返回 1 行。

    平均值:它给出了样本的平均值。它也被定义为总和除以计数值。
    语法:AVG(属性名)
    或
    语法:SUM(属性名)/COUNT(属性名)
    上述语法还检索了 tupples 的平均值。

    最大值:它提取一组样本中的最大值。
    语法:MAX(属性名)

    最小值:它提取所有样本集中的最小值。
    语法:MIN(属性名)

    **GROUP BY:** Group by 用于根据属性或属性组对关系的元组进行分组。它总是与在组上计算的聚合函数相结合。例如:

    ```
    SELECT ADDRESS, SUM(AGE) FROM STUDENT
    GROUP BY (ADDRESS);
    ```

    在这个查询中，SUM( **AGE** )将被计算，但不是针对整个表，而是针对每个地址。即:地址德里(18+18=36)的年龄总和，其他地址也是如此。输出结果是:

    | **地址** | **总和(年龄)** |
    | 德里 | Thirty-six |
    | 古尔冈 | Eighteen |
    | 罗塔克 | Twenty |

    如果我们尝试执行下面给出的查询，它将导致错误，因为尽管我们已经为每个地址计算了 SUM(AGE)，但是对于我们分组的每个地址，都有 1 个以上的 ROLL_NO。所以不能在结果集中显示。每当我们使用 GROUP BY 时，我们需要在 SELECT 语句之后的列上使用聚合函数来理解结果集。

    ```
    SELECT ROLL_NO, ADDRESS, SUM(AGE) FROM STUDENT
    GROUP BY (ADDRESS); 
    ```

    **注意:**不属于 GROUP BY 子句的属性不能用于选择。作为 GROUP BY 子句一部分的任何属性都可以用于选择，但不是强制性的。但是我们可以在聚合函数中使用不属于 GROUP BY 子句的属性。
    [**SQL 小测验**](https://www.geeksforgeeks.org/dbms-gq/sql-gq/)

    Sonal Tuteja 撰写的文章。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。