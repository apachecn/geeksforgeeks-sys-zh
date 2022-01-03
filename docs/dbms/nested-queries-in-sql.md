# SQL 中的嵌套查询

> 原文:[https://www.geeksforgeeks.org/nested-queries-in-sql/](https://www.geeksforgeeks.org/nested-queries-in-sql/)

先决条件:[SQL 基础知识](https://www.geeksforgeeks.org/structured-query-language/)

在嵌套查询中，查询写在查询内部。内部查询的结果用于外部查询的执行。我们将使用 **STUDENT，COURSE，STUDENT_COURSE** 表来理解嵌套查询。

**学生**

| **S_ID** | **S_NAME** | **S_ADDRESS** | **S_PHONE** | **S_AGE** |
| S1 | 随机存取存储 | 德里 | Nine billion four hundred and fifty-five million one hundred and twenty-three thousand four hundred and fifty-one | Eighteen |
| S2 | RAMESH | 古尔冈 | Nine billion six hundred and fifty-two million four hundred and thirty-one thousand five hundred and forty-three | Eighteen |
| S3 | SUJIT | 罗塔克 | Nine billion one hundred and fifty-six million two hundred and fifty-three thousand one hundred and thirty-one | Twenty |
| 第四心音 | SURESH | 德里 | Nine billion one hundred and fifty-six million seven hundred and sixty-eight thousand nine hundred and seventy-one | Eighteen |

**课程**

| **C_ID** | **C_NAME** |
| C1 | 目录系统代理(Directory System Agent) |
| C2 | 编程；编排 |
| C3 | 数据库管理系统 |

**学生 _ 课程**

| **S_ID** | **C_ID** |
| S1 | C1 |
| S1 | C3 |
| S2 | C1 |
| S3 | C2 |
| 第四心音 | C2 |
| 第四心音 | C3 |

嵌套查询主要有两种类型:

*   **Independent Nested Queries: In independent nested queries, query execution starts from innermost query to outermost queries. The execution of inner query is independent of outer query, but the result of inner query is used in execution of outer query. Various operators like IN, NOT IN, ANY, ALL etc are used in writing independent nested queries.

    **IN:** 如果想知道 **S_ID** 在**C _ NAME**‘DSA’或者‘DBMS’注册了哪些人，可以借助独立嵌套查询和 IN 运算符来写。从 **COURSE** 表中，我们可以找到**C _ NAME**‘DSA’或 DBMS’的 **C_ID** ，我们可以使用这些 **C_ID** s 从 **STUDENT_COURSE** 表中找到 **S_ID** s。

    **步骤 1:** 为**查找**C _ ID**C _ NAME**=“DSA”或“DBMS”

    从**课程**中选择 **C_ID** ，其中**C _ NAME**=“DSA”或 **C_NAME** =“数据库管理系统”

    **第二步:**使用第一步的 **C_ID** 寻找 **S_ID**

    从**学生课程**中选择**学生身份**，其中**学生身份**输入

    (从**课程**中选择 **C_ID** ，其中 **C_NAME** =“每日生活津贴”或 **C_NAME** =“数据库管理系统”)；

    内部查询将返回一个成员为 C1 和 C3 的集合，外部查询将返回那些 **C_ID** 等于集合中任何成员(本例中为 C1 和 C3)的 **S_ID** s。因此，它将返回 S1、S2 和 S4。

    **注:**如果我们想知道已经注册“每日生活津贴”或“数据库管理系统”的**学生**的姓名，可以通过以下方式进行:

    从**学生**中选择学生姓名，其中**学生身份**输入

    (从**学生课程**中选择**学生身份**，其中**学生身份**输入

    (从**课程**中选择 **C_ID** ，其中 **C_NAME** =“每日生活津贴”或 **C_NAME** =“数据库管理系统”)；

    **不在:**如果我们想找出既没有注册“DSA”也没有注册“DBMS”的**学生**的 **S_ID** s，可以这样做:

    从**学生**中选择**学生身份**，其中**学生身份**不在

    (从**学生课程**中选择**学生身份**，其中**学生身份**输入

    (从**课程**中选择 **C_ID** ，其中 **C_NAME** =“每日生活津贴”或 **C_NAME** =“数据库管理系统”)；

    最里面的查询将返回一个成员为 C1 和 C3 的集合。第二次内部查询将返回那些 **C_ID** 等于集合中任意成员(在本例中为 C1 和 C3)的 **S_ID** s，即 S1、S2 和 S4。最外面的查询将返回那些 **S_ID** s，其中 **S_ID** 不是 set 的成员(S1、S2 和 S4)。所以它会返回 S3。** 

*****   Related nested queries:****

**在相关嵌套查询中，内部查询的输出取决于外部查询中当前正在执行的行。例如:如果我们想找出**学生**中报名**C _ ID**‘C1’的 **S_NAME** ，可以借助相关嵌套查询来完成，如下所示:

从存在的**学生**中选择 S_NAME

(从 **STUDENT_COURSE** SC 中选择*其中 S. **S_ID** =SC。 **S_ID** 和 SC。**C _ ID**= ' C1 '；

对于 **STUDENT** S 的每一行，它将找到从 **STUDENT_COURSE** 开始的行，其中 S. **S_ID** = SC。 **S_ID** 和 SC。 **C_ID** ='C1 '。如果对于来自 **STUDENT** S 的 **S_ID** ，在 **STUDENT_COURSE** SC 中至少存在一行**C _ ID**=‘C1’，则内部查询将返回 true，相应的 **S_ID** 将作为输出返回。

本文由 Sonal Tuteja 撰写。

如果您发现任何不正确的地方，或者您想分享关于上面讨论的主题的更多信息，请写评论**