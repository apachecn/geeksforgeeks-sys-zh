# DDL 完整格式

> 原文:[https://www.geeksforgeeks.org/ddl-full-form/](https://www.geeksforgeeks.org/ddl-full-form/)

**DDL** 代表**数据定义语言**。
这些命令用于改变数据库和数据库对象的结构。例如， **DDL** 命令可用于添加、删除或修改数据库中的表。

DDL 命令为:

1.  创造
2.  改变
3.  滴
4.  缩短
5.  重新命名

**1。创建:**
该命令用于在关系数据库中创建表。
这可以通过指定各种列的名称和数据类型来实现。

**语法** :

```
CREATE TABLE TABLE_NAME
(
    column_name1 datatype1,
    column_name2 datatype2,
    column_name3 datatype3,
    column_name4 datatype4
);
```

create table 命令中的 column_name 将告诉列的名称，相应的数据类型将指定该列的数据类型。在此表中，三个列名即–学生标识为 int 类型，名称为 varchar 类型，标记为 int 类型。
例如:

```
CREATE TABLE 
Employee
(Student_id INT, 
Name VARCHAR(100), 
Marks INT); 
```

<figure class="table">

| 

> 学生
> 
> 身份证

 | 

> Name

 | 

> Max (English surname)

 |
| --- | --- | --- |

</figure>

**2。ALTER :**
Alter 命令用于以多种形式更改表格，例如:

1.  添加列
2.  重命名现有列
3.  放下一列
4.  修改列的大小或更改列的数据类型

*   **使用 ALTER–**
    语法添加列:

```
ALTER TABLE table_name ADD(
    column_name datatype); 
```

上面的命令将向表中添加一个新列。生成的表将多一列，如下所示:

```
ALTER TABLE Student 
ADD
(Address  VARCHAR(200)); 
```

在这里，这个命令将在数据类型为 varchar(200)的表 Student 中添加一个新列“Address”；

<figure class="table">

| 

> 学生
> 
> 身份证
> T4

 | 

> Name

 | 

> Max (English surname)

 | 

> Address

 |
| --- | --- | --- | --- |

*   **使用 ALTER–**
    语法重命名列:

```
ALTER TABLE 
table_name 
RENAME 
old_column_name TO new_column_name; 
```

上述命令会将现有列重命名为新列。

```
ALTER TABLE 
Employee 
RENAME 
Marks TO Age; 
```

上面的命令将列名从标记更改为年龄；

<figure class="table">

| 

> 学生
> 
> 身份证

 | 

> Name

 | 

> Age

 | 

> Address

 |
| --- | --- | --- | --- |

*   **使用 ALTER–**
    语法删除列:

```
ALTER TABLE
table_name
DROp
(column_name); 
```

上述命令将删除现有列。
例如:

```
ALTER TABLE Employee 
DROP
(Age);  
```

此处列 _ name =“Age”，已被该命令删除；

<figure class="table">

| 

> 学生
> 
> 身份证

 | 

> Name

 | 

> Address

 |
| --- | --- | --- |

*   **使用 ALTER–**
    语法修改列:

```
ALTER TABLE
Employee MODIFY
(column_name datatype); 
```

上述命令将修改现有列。
例如:

```
ALTER TABLE 
student 
MODIFY
(name varchar(300)); 
```

上述命令将通过更改列的大小来修改列名“名称”。

<figure class="table">

| 

> 学生
> 
> 身份证

 | 

> Name

 | 

> Address

 |
| --- | --- | --- |

**3。TRUNCATE :**
该命令从表中删除所有记录。但是这个命令不会破坏表的结构。
**语法**:

```
TRUNCATE TABLE table_name
```

这将从表中删除所有记录。例如，下面的命令将从学生表中删除所有记录。

示例:

```
TRUNCATE TABLE Student; 
```

**4。DROP :**
该命令将表从数据库中完全移除，同时销毁表结构。

**语法–**

```
DROP TABLE table_name
```

这将删除所有记录以及表的结构。
这是**截断**和**下降**的主要区别。-TRUNATE 只删除记录，而 DROP 则完全销毁表。

示例:

```
DROP TABLE Student; 
```

该命令将删除表记录，并破坏模式。

这都是关于 **DDL** 命令。

</figure>

</figure>

</figure>

</figure>