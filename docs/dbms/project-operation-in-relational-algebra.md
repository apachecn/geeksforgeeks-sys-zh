# 关系代数中的项目运算

> 原文:[https://www . geesforgeks . org/project-operation-in-relational-代数/](https://www.geeksforgeeks.org/project-operation-in-relational-algebra/)

先决条件–[关系代数](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)
**项目操作**选择(或选择)某些属性，丢弃其他属性。项目操作也称为垂直分区，因为它垂直分区关系或表，丢弃其他列或属性。

**符号:**

```
πA(R)
```

其中‘A’是属性列表，它是来自关系(R)的属性的期望属性集，
符号‘π(pi)’用来表示 Project 运算符，
R 一般是关系代数表达式，它产生一个关系。

**示例–**

```
πAge(Student)
```

```
πDept, Sex(Emp)
```

**示例–**
给定一个具有以下元组的关系院系(班级、院系、职位):

<center>

| 班级 | 处 | 位置 |
| --- | --- | --- |
| five | 中学生毕业考试 | 助理教授 |
| five | 中学生毕业考试 | 助理教授 |
| six | 电子工程师 | 助理教授 |
| six | 电子工程师 | 助理教授 |

</center>

**1。教员的项目班级和部门–**

```
πClass, Dept(Faculty)
```

<center>

| 班级 | 处 |
| --- | --- |
| five | 中学生毕业考试 |
| six | 电子工程师 |

</center>

在这里，我们可以观察到结果关系的度(属性数)是 2，而教员关系的度是 3，因此由此我们可以得出结论，在对关系应用项目操作时，我们可以得到不同程度的关系。

因此，结果关系的程度等于属性列表“A”中的属性数量。

**2。教员项目职位–**

```
πPosition(Faculty)
```

<center>

| 位置 |
| --- |
| 助理教授 |

</center>

Here, we can observe that all the duplicate tuples are removed from the relation in the resulting relation. This is called as Duplicate elimination.

**3。教员项目课–**

```
πClass(Faculty)
```

<center>

| 班级 |
| --- |
| five |
| six |

</center>

**重要点:**

1.  项目操作删除重复的元组。
2.  项目操作不可交换，即:

    ```
    πAttribute List 1(πAttribute List2(R)) != πAttribute List 2 (πAttribute List1(R))
    ```

3.  The following expression is valid only if Attribute List 1 is a subset of Attribute List 2. 

    ```
    πAttribute List 1(πAttribute List2(R))
    ```

    而且，写上面的表达式和写下面的表达式一样好:

    ```
    πAttribute List 1(πAttribute List2(R)) = πAttribute List 1 (R)
    ```

4.  项目操作产生的关系的基数(元组数)为:

    ```
    1 <= πA(R) <= |R|
    ```

5.  项目操作产生的关系的程度(属性数)等于属性列表“A”中的属性数。
6.  在 SQL 中，SELECT DISTINCT 查询与这里的 PROJECT 完全相同。