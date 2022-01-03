# Mysql |用户定义变量

> 原文:[https://www.geeksforgeeks.org/mysql-user-defined-variables/](https://www.geeksforgeeks.org/mysql-user-defined-variables/)

Mysql 还支持用户定义变量的概念，允许将一个值从一条语句传递到另一条语句。Mysql 中的用户定义变量被写成 **@var_name** ，其中， **var_name** 是变量的名称，可以由字母数字字符组成。，_，和$。

*   用户定义的变量是会话特定的，即一个客户端定义的变量不会共享给其他客户端，当会话结束时，这些变量会自动过期。
*   这些变量不区分大小写。所以，**@标记**或者**@标记**都是指同一个值。
*   变量的最大长度可以是 64 个字符。
*   变量名可以包含其他字符，如- {！, #, ^, -, ..}在其名称中，如果引用它们。例如@'var@1 '或@"var^2″或@ ' var @`。
*   这些变量不能被声明，它们只被初始化，即在声明时，它们应该被赋值。
*   未声明的变量也可以在 SQL 语句中访问，但是它们的值被设置为**空**。
*   这些变量可以从以下一组数据类型中取值- {整数、浮点、十进制、二进制、非二进制字符串或空值。

**语法:**

```
SET @var_name = expression 
```

**示例:**

1.使用**设置**命令为变量赋值。

```
mysql>SET @var1 = 2+6;
mysql>SET @var2 := @var1-2;
```

这些变量的值可以通过在 SELECT 语句中引用它们来显示

```
mysql>SELECT @var1, @var2;
```

**输出:**

```
+-------+-------+
| @var1 | @var2 |
+-------+-------+
|   8   |   6   |
+-------+-------+
```

2.访问未声明的变量

```
mysql>SELECT @var3;
```

**输出:**

```
+-------+
| @var3 | 
+-------+
|  NULL |  
+-------+
```

这里变量 **@var3** 是未声明的，所以默认值为 NULL。

3.不使用**设置**为变量赋值。

```
mysql>SELECT @var3 := 4;
```

**输出:**

```
+----------+
| @var3:=4 | 
+----------+
|    4     |  
+----------+
```

在上例中-变量 **@var3** 应该只使用 **:=** 而不是 **=** 赋值，后者在非 **SET** 语句中被视为比较。就像-

```
mysql>SELECT @var4 = 5;
```

**输出:**

```
+----------+
| @var4=5  | 
+----------+
|   NULL   |  
+----------+
```

**这些变量是如何用来存储值的，这些值将在未来使用。**

考虑以下学生表-

<figure class="table">

| s_id | s_name | 标记 |
| --- | --- | --- |
| one | 沙根 | Fifteen |
| Two | 塔鲁纳 | five |
| three | 里亚 | Fifteen |
| four | 菠菜 | Ten |
| five | 停止 | seven |
| six | 加里马 | Seventeen |

现在，我们要用用户定义的变量找到这些学生的**排名**。

为此，我们初始化两个变量- **@rank** 和 **@prev_mark** 。

```
mysql>SET @rank=0, @prev_mark=0;
```

**查询:**

```
mysql>Select s_name, if (@prev_mark != mark, @rank:=@rank+1, @rank) as 'rank',
                    @prev_mark:=mark as 'marks' from student order by mark desc;
```

这里，变量 **@rank** 用于存储学生的排名， **@prev_mark** 用于存储之前学生成绩的分数。

对分数进行比较，以便在两个学生分数相等的情况下，可以避免增加 **@rank** 变量。

在学生表按“标记”列降序排序后，两个变量都发生了变化。

**输出:**

<figure class="table">

| s_name | 等级 | 记号 |
| --- | --- | --- |
| 加里马 | one | Seventeen |
| 沙根 | Two | Fifteen |
| 里亚 | Two | Fifteen |
| 菠菜 | three | Ten |
| 停止 | four | seven |
| 塔鲁纳 | five | five |

因此，我们得到的学生表按照“分数”列按照学生的排名降序排列。

**注意:**在上面的查询中，注意 select 语句中列的顺序。如果“标记”列写在“排名”列之前，那么我们得不到想要的输出。因为每次 **@prev_mark** 被分配当前学生的分数，结果评价@prev_mark！=标记为**假**。因此，每个学生的排名都显示为不递增，即它将保持为 0。

</figure>

</figure>