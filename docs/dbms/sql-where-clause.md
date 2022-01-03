# SQL | WHERE 子句

> 原文:[https://www.geeksforgeeks.org/sql-where-clause/](https://www.geeksforgeeks.org/sql-where-clause/)

WHERE 关键字用于获取结果集中的**过滤数据**。

*   它用于根据特定标准获取数据。
*   WHERE 关键字也可以通过匹配模式来过滤数据。

**基本语法:**
**选择 column1、column2 FROM 表 _name WHERE 列 _name 运算符值；**

```
column1 , column2: fields int the table
table_name: name of table
column_name: name of field used for filtering the data
operator: operation to be considered for filtering
value: exact value or pattern to get related data in result 
```

**可与 where 子句一起使用的运算符列表:**

| **操作员** | **描述** |
| --- | --- |
| > | 大于 |
| >= | 大于或等于 |
| < | 不到 |
| <= | 小于或等于 |
| = | 等于 |
| <> | 不等于 |
| 在...之间 | 在包括范围内 |
| 喜欢 | 搜索模式 |
| 在…里 | 为一列指定多个可能的值 |

[![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/table11.jpg)

**查询**

*   To fetch record of students with age equal to 20

    ```
    SELECT * FROM Student WHERE Age=20;

    ```

    输出:

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | three | SUJIT | ROHTAK | XXXXXXXXXX | Twenty |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |

*   To fetch Name and Address of students with ROLL_NO greater than 3

    ```
    SELECT ROLL_NO,NAME,ADDRESS FROM Student WHERE ROLL_NO > 3;

    ```

    输出:

    | **滚动 _ 否** | **名称** | **地址** |
    | --- | --- | --- |
    | four | SURESH | 德里 |

**在**运算符之间

它用于获取给定范围(包括两个值)内的过滤数据。
**基本语法:**
**选择列 1、列 2 FROM 表 _name WHERE 列 _name 介于值 1 和值 2 之间；**

```
BETWEEN: operator name 
```

**值 1 和值 2:** 从值 1 到值 2 的精确值，以获得
结果集中的相关数据。

**查询**

*   To fetch records of students where ROLL_NO is between 1 and 3 (inclusive)

    ```
    SELECT * FROM Student WHERE ROLL_NO BETWEEN 1 AND 3;

    ```

    输出:

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |

*   To fetch NAME,ADDRESS of students where Age is between 20 and 30 (inclusive)

    ```
    SELECT NAME,ADDRESS FROM Student WHERE Age BETWEEN 20 AND 30;

    ```

    输出:

    | **名称** | **地址** |
    | --- | --- |
    | SUJIT | 罗塔克 |
    | SUJIT | 罗塔克 |

**像**操作员一样

它用于通过在 where 子句中搜索特定模式来获取过滤后的数据。
**基本语法:**
**SELECT column1、column 2 FROM table _ name WHERE column _ name LIKE 模式；**

```
LIKE: operator name 
```

**模式:**从模式中提取精确值，得到
结果集中的相关数据。

**注意**:模式中的字符区分大小写。

**查询**

*   To fetch records of students where NAME starts with letter S.

    ```
    SELECT * FROM Student WHERE NAME LIKE 'S%'; 
    ```

    “%”(通配符)表示后面的字符，可以是任何长度和
    值。关于通配符的更多信息将在后面的文章中讨论。

    输出:

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |

*   To fetch records of students where NAME contains the patter ‘AM’.

    ```
    SELECT * FROM Student WHERE NAME LIKE '%AM%';

    ```

    输出:

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |

**输入**操作符

它用于获取过滤后的数据，与由“=”运算符获取的数据相同，不同的是，在这里我们可以指定多个值来获取结果集。
**基本语法:**
**SELECT column1，column 2 FROM table _ name WHERE column _ name IN(值 1，值 2，..);**

```
IN: operator name 
```

**值 1，值 2，..:**与给定值匹配的精确值，并在结果集中获取相关数据。

**查询**

*   To fetch NAME and ADDRESS of students where Age is 18 or 20.

    ```
    SELECT NAME,ADDRESS FROM Student WHERE Age IN (18,20);

    ```

    输出:

    | **名称** | **地址** |
    | --- | --- |
    | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 |
    | RAMESH | 古尔冈 |
    | SUJIT | 罗塔克 |
    | SURESH | 德里 |
    | SUJIT | 罗塔克 |
    | RAMESH | 古尔冈 |

*   To fetch records of students where ROLL_NO is 1 or 4.

    ```
    SELECT * FROM Student WHERE ROLL_NO IN (1,4);

    ```

    输出:

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
    | four | SURESH | 德里 | XXXXXXXXXX | Eighteen |

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。