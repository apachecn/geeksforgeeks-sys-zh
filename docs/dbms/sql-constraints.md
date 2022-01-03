# SQL |约束

> 原文:[https://www.geeksforgeeks.org/sql-constraints/](https://www.geeksforgeeks.org/sql-constraints/)

约束是我们可以应用于表中数据类型的规则。也就是说，我们可以使用约束来指定可以存储在表的特定列中的数据类型的限制。

SQL 中可用的约束有:

*   **不为空**:这个约束告诉我们不能在列中存储空值。也就是说，如果一个列被指定为非空，那么我们将不能再在这个特定的列中存储空值。
*   **UNIQUE** :当用一列指定时，这个约束告诉列中的所有值必须是唯一的。也就是说，列的任何一行中的值都不能重复。
*   **主键**:主键是一个可以唯一标识表中每一行的字段。此约束用于将表中的字段指定为主键。
*   **外键**:外键是一个字段，可以唯一地标识另一个表中的每一行。此约束用于将字段指定为外键。
*   **检查**:该约束有助于验证列的值以满足特定条件。也就是说，它有助于确保存储在列中的值满足特定条件。
*   **DEFAULT** :当用户没有指定值时，该约束为列指定默认值。

**如何指定约束？**
我们可以使用 CREATE TABLE 语句在创建表时指定约束。我们还可以在使用 ALTER TABLE 语句创建表之后指定约束。

**语法** :
下面是创建表时使用 CREATE TABLE 语句创建约束的语法。

```
CREATE TABLE sample_table
(
column1 data_type(size) constraint_name,
column2 data_type(size) constraint_name,
column3 data_type(size) constraint_name,
....
);

sample_table: Name of the table to be created.
data_type: Type of data that can be stored in the field.
constraint_name: Name of the constraint. for example- NOT NULL, UNIQUE, PRIMARY KEY etc. 
```

让我们详细看看每个约束。

**1。不为空-**
如果我们在表中指定一个字段不为空。那么该字段将永远不接受空值。也就是说，在没有为该字段指定任何值的情况下，不允许在表中插入新行。
例如，下面的查询创建了一个学生表，字段标识和名称不为空。也就是说，每次我们希望插入新行时，我们都必须为这两个字段指定值。

```
CREATE TABLE Student
(
ID int(6) NOT NULL,
NAME varchar(10) NOT NULL,
ADDRESS varchar(20)
);
```

**2。唯一的****–**
该约束有助于唯一地标识表格中的每一行。即对于特定的列，所有的行应该具有唯一的值。一个表中可以有多个 UNIQUE 列。
例如，下面的查询创建了一个表 Student，其中字段 ID 被指定为 UNIQUE。也就是说，没有两个学生可以有相同的身份证。[细节上的独特约束。](https://www.geeksforgeeks.org/sql-unique-constraint/)

```
CREATE TABLE Student
(
ID int(6) NOT NULL UNIQUE,
NAME varchar(10),
ADDRESS varchar(20)
);
```

**3。主键-**
主键是唯一标识表中每一行的字段。如果表中的某个字段作为主键，则该字段将不能包含空值，并且该字段的所有行都应该具有唯一值。换句话说，我们可以说这是非空约束和唯一约束的组合。
一个表只能有一个字段作为主键。下面的查询将创建一个名为 Student 的表，并将字段 ID 指定为主键。

```
CREATE TABLE Student
(
ID int(6) NOT NULL UNIQUE,
NAME varchar(10),
ADDRESS varchar(20),
PRIMARY KEY(ID)
);
```

**4。外键–**
外键是表中唯一标识另一个表的每一行的字段。也就是说，该字段指向另一个表的主键。这通常会在表之间创建一种链接。
考虑如下所示的两个表格:

**命令**

<figure class="table">

| O_ID | 订单编号 | C_ID |
| one | Two thousand two hundred and fifty-three | three |
| Two | Three thousand three hundred and twenty-five | three |
| three | Four thousand five hundred and twenty-one | Two |
| four | Eight thousand five hundred and thirty-two | one |

**客户**

<figure class="table">

| C_ID | 名字 | 地址 |
| one | RAMESH | 德里 |
| Two | SURESH | 无聊死了 |
| three | 达摩克利斯 | 古尔冈 |

我们可以清楚地看到，Orders 表中的字段 C_ID 是 Customers 表中的主键，即它唯一标识 Customers 表中的每一行。因此，它是订单表中的外键。
语法:

```
CREATE TABLE Orders
(
O_ID int NOT NULL,
ORDER_NO int NOT NULL,
C_ID int,
PRIMARY KEY (O_ID),
FOREIGN KEY (C_ID) REFERENCES Customers(C_ID)
)
```

**(I)CHECK–**
使用 CHECK 约束，我们可以为字段指定一个条件，在为该字段输入值时应该满足该条件。
例如，下面的查询创建了一个表 Student，并将字段 AGE 的条件指定为(AGE > = 18)。也就是说，用户将不被允许在带有年龄< 18 的表格中输入任何记录。[详细检查约束](https://www.geeksforgeeks.org/sql-check-constraint/)

```
CREATE TABLE Student
(
ID int(6) NOT NULL,
NAME varchar(10) NOT NULL,
AGE int NOT NULL CHECK (AGE >= 18)
);
```

**(ii)DEFAULT–**
该约束用于为字段提供默认值。也就是说，如果在表中输入新记录时，如果用户没有为这些字段指定任何值，那么默认值将被分配给它们。
例如，下面的查询将创建一个名为 Student 的表，并将字段 AGE 的默认值指定为 18。

```
CREATE TABLE Student
(
ID int(6) NOT NULL,
NAME varchar(10) NOT NULL,
AGE int DEFAULT 18
);
```

本文由 [**哈什·阿加瓦尔**](https://www.facebook.com/harsh.agarwal.16752) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。
如果你喜欢 GeeksforGeeks 并想投稿，你也可以写一篇文章，把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息

</figure>

</figure>