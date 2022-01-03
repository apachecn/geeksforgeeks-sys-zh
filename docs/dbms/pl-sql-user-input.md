# PL/SQL |用户输入

> 原文:[https://www.geeksforgeeks.org/pl-sql-user-input/](https://www.geeksforgeeks.org/pl-sql-user-input/)

先决条件–[PL/SQL 简介](https://www.geeksforgeeks.org/plsql-introduction/)
在 PL/SQL 中，可以提示用户使用 **&** 字符输入值。&可用于提示输入不同的数据类型。考虑下表:

<center>
**Table:** GFG

| 身份证明（identification） | 作者 | 喜欢 |
| one | 萨姆（男子名） | Ten |
| Two | 玛丽亚 | Thirty |
| three | 河口 | Forty |

</center>

以下查询将在数据库中创建一个名为 GFG 的新表。

```
SQL> create table GFG (id number(4), author varchar2(50), 
                                          likes number(4)) 
```

```
Table created.
SQL> insert into GFG values(1, 'sam', 10);
1 row created.
SQL> insert into GFG values(2, 'maria', 30);
1 row created.
SQL> insert into GFG values(3, 'ria', 40);
1 row created. 
```

```
SQL> select * from GFG;
```

<center>

| 身份证明（identification） | 作者 | 喜欢 |
| one | 萨姆（男子名） | Ten |
| Two | 玛丽亚 | Thirty |
| three | 河口 | Forty |

</center>

**1。数值–**
&用于用户输入数值。

**语法:**

```
&value 
```

**例-1:** 考虑一下，表 GFG。让我们选择一个具有给定 id 的记录。(这里，id 是一个数值)

```
SQL> select * from GFG where id=&id;
Enter value for id: 2
old 1: select * from GFG where id=&id
new 1: select * from GFG where id=2 
```

<center>

| 身份证明（identification） | 作者 | 喜欢 |
| Two | 玛丽亚 | Thirty |

</center>

**示例-2:** 让我们用给定的 id 更新一条记录。(这里，id 是一个数值)

```
SQL> update GFG set likes=50 where id=&id;
Enter value for id: 1
old 1: update GFG set likes=50 where id=&id
new 1: update GFG set likes=50 where id=1
1 row updated. 
```

```
SQL> select * from GFG; 
```

<center>

| 身份证明（identification） | 作者 | 喜欢 |
| one | 萨姆（男子名） | Fifty |
| Two | 玛丽亚 | Thirty |
| three | 河口 | Forty |

</center>

**2。文本值–**
&也可用于从用户输入文本值。

**语法:**

```
'&value' 
```

**例-1:** 考虑一下，表 GFG。让我们选择一个给定作者的记录。(这里，作者是文本值)

```
SQL> select * from GFG where author='&author';
Enter value for author: maria
old 1: select * from GFG where author='&author'
new 1: select * from GFG where author='maria' 
```

<center>

| 身份证明（identification） | 作者 | 喜欢 |
| Two | 玛丽亚 | Thirty |

</center>

**示例-2:** 让我们用给定的作者更新一条记录。(这里，作者是文本值)

```
SQL> update GFG set likes=10 where author='&author';
Enter value for author: sam
old 1: update GFG set likes=10 where author='&author'
new 1: update GFG set likes=10 where author='sam' 
1 row updated. 
```

```
SQL> select * from GFG; 
```

<center>

| 身份证明（identification） | 作者 | 喜欢 |
| one | 萨姆（男子名） | Ten |
| Two | 玛丽亚 | Thirty |
| three | 河口 | Forty |

</center>