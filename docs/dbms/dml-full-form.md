# DML 完整格式

> 原文:[https://www.geeksforgeeks.org/dml-full-form/](https://www.geeksforgeeks.org/dml-full-form/)

DML 代表**数据操作语言**。当通过 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 与存储在数据库中的数据进行通信时，表格和公式是很有帮助的，但是当我们实际上想要执行一些相当复杂的数据交互时，情况就来了。在这种情况下，我们还需要数据操作语言。DML 是一种准确通知数据库我们想要它做什么的方法，它通过一种从头开始理解的方式进行对话。当涉及到在现有数据中进行交互时，无论是添加、移动还是删除数据，它都提供了一种方便的方式。

**数据库管理系统**提供了一个修改或改变数据的功能或方言框架，称为数据操作语言。数据操作可以通过输入 SQL 查询或者使用一个典型的名为[示例查询(QBE)](https://www.geeksforgeeks.org/query-by-example-qbe/) 的图形界面来完成。这些声明用于修改表中的数据。这些声明将对结果产生作用。这些语句与表的结构没有关系。数据操作包括将数据引入表中、更改表的数据以及从表中删除数据。

DML 语句需要事务控制。DML 语句对数据库所做的任何修改都将被称为事务。因此，由 DML 语句进行的任何调整都必须由 **TCL 语句(事务控制语言)**控制。DML 是改变存储在表中的信息的 SQL 语句的子集。因此，它主要关注数据库性能，并利用了 HDFS (Hadoop 分布式文件系统)存储的仅附加特性。

**数据操作语言类型:**

<center>

| 高级或非程序性 DML | 低级或程序性 DML |
| --- | --- |
| 它也被称为一次设置或面向序列的 DML。 | 它也被称为一次跟踪 DML。 |
| 它可以单独用于精确指定数据库中的复杂操作。 | 它必须集成到通用编程语言中。 |
| 它本质上是规定性的。 | 它在自然界中是不可缺少的。 |
| 它要求用户必须清楚地说明需要哪些数据，而不清楚如何以及何时获取这些数据。

 | 它要求用户必须清楚地说明需要哪些数据以及如何获得这些数据。 |
| **例如:**每一条 SQL 语句都是一个规定性的命令。 | **例如:** DB2 的 SQL PL，Oracle 的 PL/SQL。 |

</center>

**特性:**
它执行仅解释的数据查询。它在数据库模式中用于调用和操作信息。它是一种方言，用于选择、插入、删除和更新数据库中的数据。

数据操作语言命令如下:

1.  **SELECT Command –**
    This command is used to get data out of the database. It helps users of the database to access from an operating system, the significant data they need. It sends a track result set from one tables or more.

    **语法:**

    ```
    SELECT * 
    FROM <table_name>; 
    ```

    **示例:**

    ```
    SELECT * 
    FROM students;

    OR

    SELECT * 
    FROM students
    where due_fees <=20000;
    ```

2.  **插入命令–**
    该命令用于将信息或值输入一行。我们可以使用这条指令将一个或多个记录连接到存储库中的单个表。这通常用于将未使用的标签连接到文档。

**语法:**

```
INSERT INTO <table_name> ('column_name1' <datatype>, 'column_name2' <datatype>)

VALUES ('value1', 'value2'); 
```

**示例:**

```
INSERT INTO students ('stu_id' int, 'stu_name' varchar(20), 'city' varchar(20))

VALUES ('1', 'Nirmit', 'Gorakhpur'); 
```

9.  **UPDATE Command –**
    This command is used to alter existing table records. Within a table, it modifies data from one or more records. This command is used to alter the data which is already present in a table.

    **语法:**

    ```
    UPDATE <table_name>

    SET <column_name = value>

    WHERE condition; 
    ```

    **示例:**

    ```
    UPDATE students

    SET due_fees = 20000

    WHERE stu_name = 'Mini'; 
    ```

10.  **DELETE Command –**
    It deletes all archives from a table. This command is used to erase some or all of the previous table’s records. If we do not specify the ‘WHERE’ condition then all the rows would be erased or deleted.

    **语法:**

    ```
    DELETE FROM <table_name>

    WHERE <condition>; 
    ```

    **示例:**

    ```
    DELETE FROM students

    WHERE stu_id = '001'; 
    ```

**优势:**

1.  DML 语句可能会改变数据库中包含或存储的数据。
2.  它提供了人与机器的有效接触。
3.  用户可以指定需要什么数据。
4.  DML 的目标是在提供数据库的供应商之间拥有许多不同的种类和功能。

**缺点:**

1.  我们不能使用 DML 来改变数据库的结构。
2.  限制表视图，即它可以隐藏表中的一些列。
3.  在对象中没有存储数据的情况下访问数据。
4.  无法使用 DML 构建或擦除列表或节。