# 关系代数中的选择运算

> 原文:[https://www . geesforgeks . org/select-operation-in-relational-代数/](https://www.geeksforgeeks.org/select-operation-in-relational-algebra/)

先决条件–[关系代数](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)
**选择操作**从满足选择语法中提到的给定条件的关系中选择元组子集。选择操作也称为水平分区，因为它水平分区表或关系。

**符号:**

```
σ c(R)
```

其中‘c’是布尔表达式(条件)的选择条件，我们可以有一个像 Roll= 3 这样的条件或者像 X>2 和 Y <1,
这样的条件的组合，符号‘σ(sigma)’用于表示选择(choose)运算符，

r 是一个关系代数表达式，其结果是一个关系。条件“c”中指定的布尔表达式可以用以下形式编写:

```
<attribute name> <comparison operator> <constant value> or <attribute name>
```

其中，<attribute name="">显然是关系属性的名称，</attribute>

<comparison operator="">是任意一个运算符{ ，=，<=, > =，！=}并且，
<常量值>是取自关系域的常量值。</comparison>

**示例-1:**

```
σ Place = 'Mumbai' or Salary >= 1000000 (Citizen)
σ Department = 'Analytics'(σLocation = 'NewYork'(Manager))
```

上面的查询(立即)被称为嵌套表达式，在这里，像往常一样，我们首先评估内部表达式(这导致关系，比如 Manager1)，然后我们计算 Manager1 上的外部表达式(我们通过评估内部表达式获得的关系)，这再次导致关系，这是我们输入的关系的一个实例。

**示例-2:**

给定具有以下元组的关系学生(名单、姓名、班级、费用、团队):

<center>

| 卷 | 名字 | 部门 | 费用 | 组 |
| --- | --- | --- | --- | --- |
| one | 毕卡什 | 中学生毕业考试 | Twenty-two thousand | A |
| Two | 玩笑 | 中学生毕业考试 | Thirty-four thousand | A |
| three | 凯文 | 欧洲经济委员会 | Thirty-six thousand | C |
| four | 本(男子名) | 欧洲经济委员会 | Fifty-six thousand | D |

</center>

选择甲队的所有学生:

```
σ Team = 'A' (Student)
```

<center>

| 卷 | 名字 | 部门 | 费用 | 组 |
| --- | --- | --- | --- | --- |
| one | 毕卡什 | 中学生毕业考试 | Twenty-two thousand | A |
| Two | 玩笑 | 中学生毕业考试 | Thirty-four thousand | A |

</center>

选择费用大于等于 10000 且属于 a 队以外的系 ECE 所有学生。

```
σ Fees >= 10000(σClass != 'A' (Student))
```

<center>

| 卷 | 名字 | 部门 | 费用 | 组 |
| --- | --- | --- | --- | --- |
| three | 凯文 | 欧洲经济委员会 | Thirty-six thousand | C |
| four | 本(男子名) | 欧洲经济委员会 | Fifty-six thousand | D |

</center>

**关于选择操作的要点:**
选择运算符是一元的，表示它只适用于单个关系。选择操作是可交换的，

```
σ c<sub>1</sub>(σ c<sub>2</sub>(R)) = σ c<sub>2</sub>(σ c<sub>1</sub>(R))
```

选择操作产生的关系的程度(属性数)与给定关系的程度相同。从选择操作得到的关系的基数(元组的数量)是，

```
0 <= σ c (R) <= |R|
```