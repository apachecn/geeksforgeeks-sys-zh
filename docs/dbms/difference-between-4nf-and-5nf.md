# 4NF 和 5NF 的区别

> 原文:[https://www . geesforgeks . org/difference-4nf 和-5nf/](https://www.geeksforgeeks.org/difference-between-4nf-and-5nf/)

先决条件–[第四和第五范式](https://www.geeksforgeeks.org/introduction-of-4th-and-5th-normal-form-in-dbms/)

**1。第四范式(4NF) :**
当任何关系满足下列条件时，称为第四范式:

*   必须是 [Boyce Codd 范式(BCNF)](https://www.geeksforgeeks.org/boyce-codd-normal-form-bcnf/) 。
*   应该没有[多值依赖](https://practice.geeksforgeeks.org/problems/explain-multi-valued-dependencies)。

当一个表中有两个属性依赖于第三个属性但又相互独立时，称为多值依赖。
对于函数依赖 X- > Y，如果 X 的单个值存在多个 Y 值，则存在多值依赖。
因此，如果一个关系在 BCNF，并且也不存在任何多值依赖，则该关系将在 4NF。
为了表示多值从属关系，使用了“- > - >”这个符号。

**示例–**
考虑以下关系:

<center>

| 学生证 | 课程 | 业余爱好 |
| --- | --- | --- |
| One hundred | 科学 | 舞蹈 |
| One hundred | 数学 | 唱歌 |
| One hundred and one | C# | 舞蹈 |
| One hundred and one | 服务器端编程语言（Professional Hypertext Preprocessor 的缩写） | 唱歌 |

</center>

在这种关系下，学生证 1 选择了两门课程，有两个爱好。同样，学生证 2 选择了两门课程，有两个爱好。因此它包含多值依赖。它不在 4NF，为了把它转换成 4NF，它可以分解成两种关系:

<center>**Table –** R1</center>

<center>

| 学生证 | 课程 |
| --- | --- |
| One hundred | 科学 |
| One hundred | 数学 |
| One hundred and one | C# |
| One hundred and one | 服务器端编程语言（Professional Hypertext Preprocessor 的缩写） |

</center>

<center>**Table –** R2</center>

<center>

| 学生证 | 业余爱好 |
| --- | --- |
| One hundred | 舞蹈 |
| One hundred | 唱歌 |
| One hundred and one | 舞蹈 |
| One hundred and one | 唱歌 |

</center>

现在这种关系就在 4NF。一个关系可以包含一个函数依赖和一个多值依赖。因此，当出现这种情况时，功能相关的列被移动到单独的表中，多值相关的列被移动到单独的表中。这就把关系转换成了 4NF。

**2。第五范式(5NF) :**
任何关系要处于第五范式必须满足以下条件:

*   它必须是第四范式(4NF)。
*   它应该没有[连接依赖](https://practice-stage.geeksforgeeks.org/problems/what-is-join-dependency-and-inclusion-dependency)，并且连接必须是无损的。

在第五范式中，必须将关系分解成尽可能多的子关系，以避免任何类型的冗余，并且当通过使用自然连接将子关系组合在一起时，不能产生额外的元组。

5NF 中的关系如果没有任何意义或事实上的修改，就不能被进一步分解。5NF 也称为**项目连接范式(PJNF)** 。

**示例–**

<center>

| 学生证 | 手机号码 | 业余爱好 |
| --- | --- | --- |
| One hundred and twenty-three | Nine billion nine hundred and ninety-nine million nine hundred thousand | 舞蹈 |
| One hundred and twenty-four | Nine billion nine hundred and ninety-nine million nine hundred thousand | 唱歌 |
| One hundred and twenty-four | Nine billion nine hundred and ninety-nine million nine hundred thousand | 舞蹈 |
| One hundred and twenty-three | Eight billion nine hundred and seventy-five million six hundred and twenty-two thousand one hundred and twenty-two | 唱歌 |
| One hundred and twenty-three | Nine billion nine hundred and ninety-nine million nine hundred thousand | 唱歌 |

</center>

This can be further decomposed into three relations:

<center>**Table –** R1</center>

<center>

| 学生证 | 手机号码 |
| --- | --- |
| One hundred and twenty-three | Nine billion nine hundred and ninety-nine million nine hundred thousand |
| One hundred and twenty-three | Eight billion nine hundred and seventy-five million six hundred and twenty-two thousand one hundred and twenty-two |
| One hundred and twenty-four | Nine billion nine hundred and ninety-nine million nine hundred thousand |

</center>

<center>**Table –** R2</center>

<center>

| 学生证 | 业余爱好 |
| --- | --- |
| One hundred and twenty-three | 舞蹈 |
| One hundred and twenty-three | 唱歌 |
| One hundred and twenty-four | 唱歌 |
| One hundred and twenty-four | 舞蹈 |

</center>

<center>**Table –** R3</center>

<center>

| 手机号码 | 业余爱好 |
| --- | --- |
| Nine billion nine hundred and ninety-nine million nine hundred thousand | 舞蹈 |
| Nine billion nine hundred and ninety-nine million nine hundred thousand | 唱歌 |
| Eight billion nine hundred and seventy-five million six hundred and twenty-two thousand one hundred and twenty-two | 唱歌 |

</center>

因此，如果对所有三个关系执行自然连接，那么就不会有额外的元组。因此，R1、R2 和 R3 处于第五范式(5NF)。

**4NF 和 5NF 的区别:**

<center>

| S.NO | 4NF | 5NF |
| --- | --- | --- |
| 1. | 4NF 的关系也必须在 BCNF。 | 5NF 中的关系也必须在 4NF(第四范式)。 |
| 2. | 4NF 的关系不能有任何多值依赖关系。 | 5NF 中的关系不能有任何连接依赖关系。 |
| 3. | 4NF 的关系可能在 5NF，也可能不在 5NF。 | 5NF 中的一个关系总是在 4NF |
| 4. | 与第五范式相比，第四范式没有那么强。 | 第五范式比第四范式更强。 |
| 5. | 如果一个关系是第四范式，那么它将有更多的冗余。 | 如果一个关系是在第五范式，那么它将减少冗余。 |
| 6. | 如果一个关系是第四范式，那么它可以进一步分解为子关系。 | 如果一个关系处于第五范式，那么如果没有任何意义或事实上的修改，它就不能进一步分解为子关系。 |

</center>