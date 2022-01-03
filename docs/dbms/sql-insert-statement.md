# SQL |插入语句

> 原文:[https://www.geeksforgeeks.org/sql-insert-statement/](https://www.geeksforgeeks.org/sql-insert-statement/)

SQL 的 INSERT INTO 语句用于在表中插入一个新行。使用 INSERT INTO 语句插入行有两种方式:

1.  **仅值:**第一种方法是只指定要插入的数据的值，而不指定列名。

    > **INSERT INTO table _ name VALUES(value 1，value2，value3，…)；**
    > **表 _ 名**:表的名称
    > **值 1、值 2、..**:新记录的第一列、第二列、…的值

2.  **列名和值两者:**在第二种方法中，我们将指定要填充的列及其对应的值，如下所示:

    > **INSERT INTO table _ name(第一列,第 2 列,第 3 列,..)值(值 1，值 2，值 3，..);**
    > **表 _ 名**:表的名称
    > **列 1** :第一列、第二列的名称……
    > T14】值 1、值 2、值 3 :新记录的第一列、第二列的值……

[![table1](img/4fab6fceee0b1d1b256c3430eb713844.png)](https://media.geeksforgeeks.org/wp-content/cdn-uploads/table11.jpg)

**查询:**

**方法 1(仅插入值):**

> 在学生价值观中插入(‘5’，‘严厉’，‘西孟加拉邦’，‘XXXXXXXXXX’，‘19’)；

**输出:**
表格**学生**现在看起来像:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
| Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
| four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
| Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
| five | 严厉的 | 西孟加拉邦 | XXXXXXXXXX | Nineteen |

**方法 2(仅在指定的列中插入值):**

> 插入学生(卷号、姓名、年龄)值(‘5’，‘PRATIK’，‘19’)；

**输出:**
表格**学生**现在看起来像:

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
| Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
| four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
| three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
| Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
| five | 我在练习 | 空 | 空 | Nineteen |

请注意，未提供值的列由 null 填充。这是这些列的默认值。

在插入语句中使用选择

**我们可以使用 SELECT 语句和 INSERT INTO 语句从一个表中复制行，然后将它们插入另一个表中。该语句的用法类似于 INSERT INTO 语句。不同之处在于，这里使用 SELECT 语句从不同的表中选择数据。使用插入选择语句的不同方式如下所示:**

*   ****Inserting all columns of a table:** We can copy all the data of a table and insert into in a different table.

    > **插入第一个 _ 表格选择*从第二个 _ 表格；** 
    > **首 _ 表**:首表名称。
    > **秒 _ 表**:秒表名称。

    我们使用 SELECT 语句从一个表中复制数据，并使用 INSERT INTO 语句插入到另一个表中。** 
*   ****Inserting specific columns of a table:** We can copy only those columns of a table which we want to insert into in a different table.
    **Syntax:**

    > **INSERT INTO first _ table(name _ of _ columns 1)SELECT name _ of _ columns 2 FROM second _ table；**
    > **首 _ 表**:首表名称。
    > **秒 _ 表**:秒表名称。
    > **列名 1** :表 1 中用逗号(，)分隔的列名。
    > **列名 2** :表 2 中用逗号(，)分隔的列名。

    我们使用 SELECT 语句只从第二个表中复制选定列的数据，使用 INSERT INTO 语句插入第一个表。** 
*   ****从表中复制特定行**:我们可以通过 SELECT 语句使用 WHERE 子句从一个表中复制特定行插入到另一个表中。我们必须在 WHERE 子句中提供适当的条件来选择特定的行。

    > **在表一中插入从表 2 中选择*的条件；**
    > **首 _ 表**:首表名称
    > **秒 _ 表**:秒表名称
    > **条件:**条件选择具体行** 

**表 2:后期研究**

| **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
| --- | --- | --- | --- | --- |
| seven | 我是维克 | 达姆弹 | XXXXXXXXXX | Eighteen |
| eight | 尼拉吉 | 无聊死了 | XXXXXXXXXX | Nineteen |
| nine | 索梅什 | 罗塔克 | XXXXXXXXXX | Twenty |

****查询:****

*   ****Method 1(Inserting all rows and columns):**

    > 插入学生选择*从以后的学习；

    **输出:**
    该查询会将 LateralStudent 表的所有数据插入到 Student 表中。学生表现在看起来像，

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | seven | 我是维克 | 达姆弹 | XXXXXXXXXX | Eighteen |
    | eight | 尼拉吉 | 无聊死了 | XXXXXXXXXX | Nineteen |
    | nine | 索梅什 | 罗塔克 | XXXXXXXXXX | Twenty |** 

*   ****Method 2(Inserting specific columns):**

    > 插入学生(卷号、姓名、年龄)从以后的学习中选择卷号、姓名、年龄；

    **输出:**
    该查询会将表的 ROLL_NO、NAME 和 Age 列中的数据插入到 Student 表中的 LateralStudent 中，Student 表中的其余列将由 *null* 填充，这是其余列的默认值。学生表现在看起来像，

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | seven | 我是维克 | 空 | 空 | Eighteen |
    | eight | 尼拉吉 | 空 | 空 | Nineteen |
    | nine | 索梅什 | 空 | 空 | Twenty |** 
*   ****Select specific rows to insert**:

    > 插入学生选择*从年龄= 18 岁的学生中选择；

    **输出:**
    该查询将只选择表格 LateralStudent 中的第一行插入学生表格。学生表现在看起来像，

    | **滚动 _ 否** | **名称** | **地址** | **PHONE** | **年龄** |
    | --- | --- | --- | --- | --- |
    | one | 随机存取存储器(random access memory 的缩写)ˌ随机访问内存(random-access memory 的缩写) | 德里 | XXXXXXXXXX | Eighteen |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | four | SURESH | 德里 | XXXXXXXXXX | Eighteen |
    | three | SUJIT | 罗塔克 | XXXXXXXXXX | Twenty |
    | Two | RAMESH | 古尔冈 | XXXXXXXXXX | Eighteen |
    | seven | 我是维克 | 达姆弹 | XXXXXXXXXX | Eighteen |** 

*   ****To insert multiple rows in a table using Single SQL Statement**

    ```

    INSERT INTO table_name(Column1,Column2,Column3,.......) 
    VALUES (Value1, Value2,Value3,.....),
            (Value1, Value2,Value3,.....),
             (Value1, Value2,Value3,.....),
             ............................. ;
    table_name: name of the table
    Column1: name of first column, second column …
    Value1, Value2, Value3 : value of first column, second column,… for each new row inserted  
    You need To provide Multiple lists of values where each list is separated by ",". Every list of value corresponds to values to be inserted in each new row of the table. 
    Values in the next list tells values to be inserted in the next Row of the table.     

    ```

    **示例:**

    以下 SQL 语句在学生表中插入多行。

    ```
    Input :
    INSERT INTO STUDENT(ID, NAME,AGE,GRADE,CITY) VALUES(1,"AMIT KUMAR",15,10,"DELHI"),
                                                       (2,"GAURI RAO",18,12,"BANGALORE"),
                                                       (3,"MANAV BHATT",17,11,"NEW DELHI"),
                                                        (4,"RIYA KAPOOR",10,5,"UDAIPUR");

    ```

    **输出:学生表**
    该查询将在学生表的每一连续行中插入所有值。因此，学生表将如下所示:

    | **ID** | **名称** | **年龄** | **等级** | **城市** |
    | --- | --- | --- | --- | --- |
    | one | 库马 | Fifteen | Ten | 德里 |
    | Two | 高丽·拉奥 | Sixteen | Twelve | [军]爆破筒 |
    | three | 马纳夫·巴哈特 | Seventeen | Eleven | 新德里 |
    | four | 里雅·卡普尔 | Ten | five | 乌代浦 |

    本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**