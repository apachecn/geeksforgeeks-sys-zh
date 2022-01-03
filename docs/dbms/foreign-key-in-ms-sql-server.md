# MS SQL Server 中的外键

> 原文:[https://www.geeksforgeeks.org/foreign-key-in-ms-sql-server/](https://www.geeksforgeeks.org/foreign-key-in-ms-sql-server/)

先决条件–[微软 SQL Server](https://www.geeksforgeeks.org/primary-key-in-ms-sql-server/)
**SQL Server**中的主键有不同的键，用于不同的目的。在本文中，将简要讨论外键。

外键的用途与主键相似，但外键用于两个表。在少数情况下，外键用于自引用单个表。

**外键:**
一个表的单个列或一组列由另一个表的单个列或一组列唯一标识的，称为外键。

**语法–**

```
constraint fk_constraint-name foreign key(col1, col2) 
references parent_table-name(col1, col2)
                                        (OR)
foreign key(col1, col2) 
references parent_table-name(col1, col2)
```

外键有两个表——父表和子表。如果用户想要在子表中插入一列，该列必须是父表的一部分，否则将显示一个错误。在语法中，约束条件不是必须使用的。

当查询中提到外键时，该键会自动创建一个引用约束，这意味着只有当列是父表的一部分时，它才能插入到子表中。

从大学数据库中考虑两个名为学生(父表)和标记(子表)的表。

<center>**Table –** Student

| 名字 | 罗龙 | 年龄 |
| 爱莎 | One hundred and eleven | Eighteen |
| 玛雅人 | One hundred and twelve | Nineteen |
| 法蒂玛 | One hundred and thirteen | Eighteen |

</center>

<center>
**Table –** Marks

| 名字 | 罗龙 | 马克斯（英格兰人姓氏） |
| 爱莎 | One hundred and eleven | Nine point five |
| 玛雅人 | One hundred and twelve | Eight point seven |
| 法蒂玛 | One hundred and thirteen | Seven point seven |

</center>

如果用户想要插入一个新的列，查询给出如下–

```
foreign key('rollno') 
references student('rollno')

insert into marks ('name', 'rollno', 'marks') 
values('Naina, '111', '7.5')
```

由于学生已经使用了学号，因此会显示一个错误。(外键约束)。外键不允许该值再次出现。为了避免此类错误，这些值不得重复，也不得考虑不同的列。