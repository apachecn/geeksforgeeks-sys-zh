# MySQL |排名函数

> 原文:[https://www.geeksforgeeks.org/mysql-ranking-functions/](https://www.geeksforgeeks.org/mysql-ranking-functions/)

MySql 中的排名函数用于对分区的每一行进行排名。排名函数也是 MySQL 窗口函数列表的一部分。

*   这些函数总是与 **OVER()** 子句一起使用。
*   排名函数总是根据 **ORDER BY** 子句来分配排名。
*   等级按顺序分配给行。
*   对于每个新分区，对行的等级分配总是从 1 开始。

MySQL 支持 3 种排名函数-

1.  **dense_rank():**
    该功能将为分区**内的每一行分配等级，没有间隙**。基本上，等级是以连续的方式分配的，即如果值之间有联系，那么它们将被分配相同的等级，并且下一个等级值将比先前分配的等级大一个等级。
2.  **rank():**
    该函数将为一个分区**内的每一行分配等级，该分区带有间隙**。这里，等级是以非连续的方式分配的，即如果值之间有联系，那么它们将被分配相同的等级，并且下一个等级值将是前一等级+对等体的数量(重复)。
3.  **percent_rank():**
    它返回分区内一行的百分位数，范围从 0 到 1。它显示小于当前行中值的分区值的百分比，不包括最高值。

为了更好地理解这些功能。
让我们考虑一张表**“结果”**–

<center>

| s_name | 学科 | 标记 |
| --- | --- | --- |
| 普拉蒂巴 | 数学 | One hundred |
| 安塔 | 科学 | Eighty |
| 斯瓦尔纳 | 英语 | One hundred |
| 安塔 | 数学 | Sixty-five |
| 普拉蒂巴 | 科学 | Eighty |
| 斯瓦尔纳 | 科学 | Fifty |
| 普拉蒂巴 | 英语 | Seventy |
| 斯瓦尔纳 | 数学 | eighty-five |
| 安塔 | 英语 | Ninety |

**查询:**

1.  **dense_rank()** function-

    ```
    SELECT subjects, s_name, mark, dense_rank() 
    OVER ( partition by subjects order by mark desc ) 
    AS 'dense_rank' FROM result;

    ```

    **输出-**

    <center>

    | 学科 | 名字 | 标记 | 密集等级 |
    | --- | --- | --- | --- |
    | 英语 | 斯瓦尔纳 | One hundred | one |
    | 英语 | 安塔 | Ninety | Two |
    | 英语 | 普拉蒂巴 | Seventy | three |
    | 数学 | 普拉蒂巴 | One hundred | one |
    | 数学 | 斯瓦尔纳 | eighty-five | Two |
    | 数学 | 安塔 | Sixty-five | three |
    | 科学 | 安塔 | Eighty | one |
    | 科学 | 普拉蒂巴 | Eighty | one |
    | 科学 | 斯瓦尔纳 | Fifty | Two |

    </center>

    **解释-**

    这里，表是根据“主题”来划分的。

    **order by** 子句用于按“mark”降序排列每个分区的行。

    **dense_rank()** 用于对各科学生进行排名。

    **注意，**对于科学学科来说，安基塔和普拉蒂巴之间是有联系的，所以他们都被分配了相同的等级。下一个等级值增加 1，即 Swarna 增加 2。

2.  **rank()** function-

    ```
    SELECT subjects, s_name, mark, rank() 
    OVER ( partition by subjects order by mark desc ) 
    AS 'rank' FROM result;

    ```

    **输出-**

    <center>

    | 学科 | 名字 | 标记 | 等级 |
    | --- | --- | --- | --- |
    | 英语 | 斯瓦尔纳 | One hundred | one |
    | 英语 | 安塔 | Ninety | Two |
    | 英语 | 普拉蒂巴 | Seventy | three |
    | 数学 | 普拉蒂巴 | One hundred | one |
    | 数学 | 斯瓦尔纳 | eighty-five | Two |
    | 数学 | 安塔 | Sixty-five | three |
    | 科学 | 安塔 | Eighty | one |
    | 科学 | 普拉蒂巴 | Eighty | one |
    | 科学 | 斯瓦尔纳 | Fifty | three |

    </center>

    **解释-**

    它的输出类似于 dense_rank()函数。

    除此之外，在安基塔和普拉蒂巴打成平手的情况下，科学科目的下一个等级值增加 2，也就是斯沃那的 3。

3.  **percent_rank()** function-

    ```
    SELECT subjects, s_name, mark, percent_rank() 
    OVER ( partition by subjects order by mark ) 
    AS 'percent_rank' FROM result;

    ```

    **输出-**

    <center>

    | 学科 | 名字 | 标记 | 百分比 _ 等级 |
    | --- | --- | --- | --- |
    | 英语 | 普拉蒂巴 | Seventy | Zero |
    | 英语 | 安塔 | Ninety | Zero point five |
    | 英语 | 斯瓦尔纳 | One hundred | one |
    | 数学 | 安塔 | Sixty-five | Zero |
    | 数学 | 斯瓦尔纳 | eighty-five | Zero point five |
    | 数学 | 普拉蒂巴 | One hundred | one |
    | 科学 | 斯瓦尔纳 | Fifty | Zero |
    | 科学 | 普拉蒂巴 | Eighty | Zero point five |
    | 科学 | 安塔 | Eighty | Zero point five |

    **说明:**

    **这里，**percent _ rank()函数通过“标记”列按升序计算百分位数排名。

    percent_rank 使用以下公式计算-

    ```
    (rank - 1) / (rows - 1)

    ```

    **秩**是使用 rank()函数得到的分区的每行的秩。

    **行**代表该分区的行数。

    要清除此公式，请考虑以下查询-

    ```
    SELECT subjects, s_name, mark, rank() 
    OVER ( partition by subjects order by mark )-1 
    AS 'rank-1', count(*) over (partition by subjects)-1
    AS 'total_rows-1', percent_rank()
    OVER ( partition by subjects order by mark ) AS 'percenr_rank'
    FROM result;

    ```

    **输出-**

    <center>

    | 学科 | 名字 | 标记 | 排名-1 | total_rows-1 | 百分比 _ 等级 |
    | --- | --- | --- | --- | --- | --- |
    | 英语 | 普拉蒂巴 | Seventy | Zero | Two | Zero |
    | 英语 | 安塔 | Ninety | one | Two | Zero point five |
    | 英语 | 斯瓦尔纳 | One hundred | Two | Two | one |
    | 数学 | 安塔 | Sixty-five | Zero | Two | Zero |
    | 数学 | 斯瓦尔纳 | eighty-five | one | Two | Zero point five |
    | 数学 | 普拉蒂巴 | One hundred | Two | Two | one |
    | 科学 | 斯瓦尔纳 | Fifty | Zero | Two | Zero |
    | 科学 | 安塔 | Eighty | one | Two | Zero point five |
    | 科学 | 普拉蒂巴 | Eighty | one | Two | Zero point five |

    </center>

    **注意:**在使用排名函数时，在 MySQL 查询中，order by 子句的使用是必须的，否则所有行都被认为是对等的(即重复的)，并且所有行都被赋予相同的排名，即 1。

    </center>

</center>