# MySQL | DEFAULT()函数

> 原文:[https://www.geeksforgeeks.org/mysql-default-function/](https://www.geeksforgeeks.org/mysql-default-function/)

**DEFAULT()** 函数返回表列的默认值。

**默认值**一列的值是在用户没有指定值的情况下使用的值。

为了使用这个函数，应该给列分配一个默认值。否则，会产生错误。

**语法:**

```
DEFAULT ( column_name)

column_name: Name of column whose default value is written.

```

**例:**考虑两个关系**学生**和**成绩**–

“学生”表的结构

<center>

| 田 | 类型 | 空 | 默认 |
| --- | --- | --- | --- |
| （同 suddenionosphericdisturbance）电离层的突然骚扰 | int(11) | 是 | 空 |
| sname | varchar(10) | 是 | 空 |
| 科目 | varchar(10) | 是 | 空 |
| 记号 | int(11) | 是 | Zero |

</center>

表“结果”的结构

<center>

| 田 | 类型 | 空 | 默认 |
| --- | --- | --- | --- |
| 最低分 | int(11) | 是 | 空 |
| 最高分数 | int(11) | 是 | 空 |
| 等级 | varchar(5) | 是 | 失败 |

</center>

表格中的数据-

```
Select * from student;

```

<center>

| （同 suddenionosphericdisturbance）电离层的突然骚扰 | sname | 科目 | 记号 |
| --- | --- | --- | --- |
| one | aayushi | O.S | eighty-nine |
| Two | 约格什 | D.答:答 | Seventy-five |
| three | 切斯特沙 | T.首席执行官 | Zero |
| four | 马纳维 | O.S | Sixty |
| five | 哈弟 | D.答:答 | Ninety-nine |
| six | 沙努 | E.标准偏差 | Thirty-five |

</center>

```
Select * from result;

```

<center>

| 最低分 | 最高分 | 等级 |
| --- | --- | --- |
| eighty-five | One hundred | A |
| Sixty | eighty-five | B |
| Forty | Sixty | C |

</center>

**问题描述:**我们要找到所有学生的成绩-

**查询:**

```
Select sid, sname, subject, marks, 
    IF ( grade is NULL, DEFAULT ( grade ), grade )
AS grade  FROM  student LEFT JOIN result 
    ON marks > lowest_marks 
AND marks < = highest_marks;

```

**输出:**

<center>

| （同 suddenionosphericdisturbance）电离层的突然骚扰 | sname | 科目 | 记号 | 等级 |
| --- | --- | --- | --- | --- |
| one | aayushi | O.S | eighty-nine | A |
| Two | 约格什 | D.答:答 | Seventy-five | B |
| three | 切斯特沙 | T.首席执行官 | Zero | 失败 |
| three | 切斯特沙 | T.首席执行官 | Zero | 失败 |
| four | 马纳维 | O.S | Sixty | C |
| five | 哈弟 | D.答:答 | Ninety-nine | A |
| six | 沙努 | E.标准偏差 | Thirty-five | 失败 |

</center>

**说明:**这里使用 default()函数返回默认等级，即“FAIL”。此默认值用于学生分数与加入条件不符的地方。那些学生的成绩显示为不及格。

**注意:**带有 select 语句的默认函数将返回所有行的默认值。这意味着，我们将获得该列的默认值列表，而不是获得该列的单个默认值。

例如上表**结果**，查询输出为-

```
Select default ( grade) from result;

```

**输出:**

<center>

| 默认(等级) |
| --- |
| 失败 |
| 失败 |
| 失败 |

</center>