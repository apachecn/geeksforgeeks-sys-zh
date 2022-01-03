# 关系代数中的查询优化

> 原文:[https://www . geesforgeks . org/query-optimization-in-relational-代数/](https://www.geeksforgeeks.org/query-optimization-in-relational-algebra/)

**查询:**查询是从数据库中获取信息的请求。

**查询计划:**查询计划(或查询执行计划)是用于访问 SQL 关系数据库管理系统中的数据的一组有序步骤。

**查询优化:**单个查询可以通过不同的算法执行，也可以用不同的形式和结构重写。因此，查询优化的问题就出现了——这些形式或路径中哪一个是最理想的？查询优化器试图通过考虑可能的查询计划来确定执行给定查询的最有效方式。

**重要性:**查询优化的目标是减少完成查询所需的系统资源，最终更快地为用户提供正确的结果集。

*   首先，它为用户提供了更快的结果，这使得应用程序对用户来说似乎更快。
*   其次，它允许系统在相同的时间内服务更多的查询，因为每个请求比未优化的查询花费更少的时间。
*   第三，查询优化最终减少了硬件(例如磁盘驱动器)的磨损量，并允许服务器更高效地运行(例如更低的功耗、更少的内存使用)。

**查询优化大致有两种方式:**

1.  分析和转换等价的关系表达式:尽量减少中间和最终查询过程的元组和列数(在此讨论)。
2.  对每个操作使用不同的算法:这些底层算法决定了如何从存储元组的数据结构中访问元组、索引、散列、数据检索，并因此影响磁盘和块访问的数量(在查询处理中讨论)。

**分析并转换等价关系表达式。**
在这里，我们将讨论生成最小等价表达式。为了分析等价表达式，列出了一组等价规则。这些函数为用关系代数编写的查询生成等价表达式。为了优化查询，只要满足等价规则，我们就必须将查询转换为它的等价形式。

1.  **Conjunctive selection operations can be written as a sequence of individual selections. This is called a sigma-cascade.** 

    ![\sigma_{\theta_{1}\Lambda\theta_{2} }(E)=\sigma_{\theta_{1}}(\sigma_{\theta_{2}}(E))  ](img/8b964307e3c281b0babde55b24a9e7dd.png "Rendered by QuickLaTeX.com")

    **说明:**申请条件![\theta_{1}  ](img/531fac85db0b0f064424b91c43ec2a44.png "Rendered by QuickLaTeX.com")路口![\theta_{2}  ](img/22c2036b7047e18102be7628590e88ef.png "Rendered by QuickLaTeX.com")贵。相反，过滤出满足条件![\theta_{2}  ](img/22c2036b7047e18102be7628590e88ef.png "Rendered by QuickLaTeX.com")(内部选择)的元组，然后将条件![\theta_{1}  ](img/531fac85db0b0f064424b91c43ec2a44.png "Rendered by QuickLaTeX.com")(外部选择)应用于随后产生的较少元组。这使得我们第二次处理的元组更少。这可以扩展到两个或多个相交的选择。因为我们将一个单一的条件分解成一系列的选择或级联，所以它被称为“级联”。

2.  **Selection is commutative.** 
    ![\sigma_{\theta_{1}}(\sigma_{\theta_{2}}(E))=\sigma_{\theta_{2}}(\sigma_{\theta_{1}}(E))  ](img/bda5cdfd08f84b0ea3dd87ac0bfedb4a.png "Rendered by QuickLaTeX.com")

    **解释:** ![\sigma  ](img/2ddc808843576a8a8672d642ff701ce6.png "Rendered by QuickLaTeX.com")条件本质上是可交换的。这意味着，我们先申请![\sigma_{1}  ](img/739b70ac46d7ef7ed28b0bd3ead60865.png "Rendered by QuickLaTeX.com")还是先申请![\sigma_{2}  ](img/dab3ae516406429e0a63503703189682.png "Rendered by QuickLaTeX.com")并不重要。在实践中，首先应用产生较少数量元组的选择是更好和更优化的。这节省了我们外部选择的时间。

3.  **All following projections can be omitted, only the first projection is required. This is called a pi-cascade.** 
    ![\pi_{L_{1}}(\pi_{L_{2}}(...(\pi_{L_{n}}(E))...)) = \pi_{L_{1}}(E)  ](img/8c90d9d0cd1fdaec61662cd83d74203c.png "Rendered by QuickLaTeX.com")

    **解释:**一个级联或者一系列的投射是没有意义的。这是因为最终，我们只选择最后一个或最外层投影中指定的那些列。因此，最好将所有投影折叠成一个，即最外面的投影。

4.  **笛卡尔乘积上的选择可以重写为θ连接。**
    *   **Equivalence 1** 
        ![\sigma_{\theta}(E_{1} \times E_{2}) = E_{1} \bowtie_{\theta} E_{2}  ](img/015b5efe2e20405a67d25b7ffc1ace96.png "Rendered by QuickLaTeX.com")

        **说明:**众所周知，叉积操作非常昂贵。这是因为它将 E1 的每个元组(总共 m 个元组)与 E2 的每个元组(总共 n 个元组)相匹配。这产生 m*n 个条目。如果我们在此之后应用选择操作，我们将不得不扫描 m*n 个条目以找到满足条件![\theta  ](img/b5e04cb8ab03d9b0e599fd3290012ddb.png "Rendered by QuickLaTeX.com")的合适元组。与其做所有这些，不如使用 Theta Join，这是一种专门设计的 Join，只选择叉积中满足 Theta 条件的条目，而不首先评估整个叉积。

    *   **Equivalence 2** 
        ![\sigma_{\theta_{1}}(E_{1} \bowtie_{\theta_{2}} E_{2}) = E_{1} \bowtie_{\theta_{1} \Lambda \theta_{2}} E_{2}  ](img/d3c1ea2d67bf1df5691eeed544f16e27.png "Rendered by QuickLaTeX.com")

        **解释:** Theta Join 从根本上减少了结果元组的数量，因此如果我们将两个连接条件(即![\theta_{1}  ](img/531fac85db0b0f064424b91c43ec2a44.png "Rendered by QuickLaTeX.com")和![\theta_{2}  ](img/22c2036b7047e18102be7628590e88ef.png "Rendered by QuickLaTeX.com")的交集应用到 Theta Join 本身，我们需要做的扫描会更少。另一方面，外部的![\sigma_{1}  ](img/739b70ac46d7ef7ed28b0bd3ead60865.png "Rendered by QuickLaTeX.com")条件不必要地增加了要扫描的元组。

5.  **Theta Joins are commutative.** 
    ![E_{1} \bowtie_{\theta} E_{2} = E_{2} \bowtie_{\theta} E_{1}  ](img/b1973cad4d131dbd16e2409520a46be9.png "Rendered by QuickLaTeX.com")

    **说明:** Theta 联接是可交换的，查询处理时间在某种程度上取决于联接过程中哪个表用作外循环，哪个表用作内循环(基于索引结构和块)。

6.  **连接操作是关联的。**
    *   **Natural Join** 
        ![(E_{1} \bowtie E_{2}) \bowtie E_{3} = E_{1} \bowtie (E_{2} \bowtie E_{3})  ](img/ad9d9ebc32b51dfda927b55c9df9df8e.png "Rendered by QuickLaTeX.com")

        **说明:**连接既可以是交换的，也可以是关联的，因此必须先连接这两个表，这样产生的条目数就更少，然后再应用另一个连接。

    *   **Theta Join** 
        ![(E_{1} \bowtie_{\theta_{1}} E_{2}) \bowtie_{\theta_{2} \Lambda \theta_{3}} E_{3} = E_{1} \bowtie_{\theta_{1} \Lambda \theta_{3}} (E_{2} \bowtie_{\theta_{2}} E_{3})  ](img/20edad34b2331c5179bf2b9224bed90a.png "Rendered by QuickLaTeX.com")

        **解释:** Theta 联接以上述方式关联，其中![\theta_{2}  ](img/22c2036b7047e18102be7628590e88ef.png "Rendered by QuickLaTeX.com")仅涉及来自 E2 和 E3 的属性。

7.  **选择操作可以分配。**
    *   **Equivalence 1** 
        ![\sigma_{\theta_{1}\Lambda\theta_{2}}(E_{1}\bowtie_{\theta}E_{2})=(\sigma_{\theta_{1}}(E_{1}))\bowtie_{\theta}(\sigma_{\theta_{2}}(E_{2}))  ](img/cd8cf0ba6a35eb6a099add8feed63019.png "Rendered by QuickLaTeX.com")

        **解释:**在执行 Theta Join 后应用选择会导致 Theta Join 返回的所有元组在连接后被监控。如果这个选择只包含来自 E1 的属性，最好将这个选择应用于 E1(因此导致元组数量较少)，然后将其与 E2 连接。

    *   **Equivalence 2** 
        ![\sigma_{\theta_{0}}(E_{1}\bowtie_{\theta}E_{2})=(\sigma_{\theta_{0}}(E_{1}))\bowtie_{\theta}E_{2}  ](img/89ea55b15efcfa78c54501721b53201a.png "Rendered by QuickLaTeX.com")

        **说明:**这个可以扩展到两个选择条件，![\theta_{1}  ](img/531fac85db0b0f064424b91c43ec2a44.png "Rendered by QuickLaTeX.com")和![\theta_{2}  ](img/22c2036b7047e18102be7628590e88ef.png "Rendered by QuickLaTeX.com")，其中 Theta1 只包含 E1 的属性，![\theta_{2}  ](img/22c2036b7047e18102be7628590e88ef.png "Rendered by QuickLaTeX.com")只包含 E2 的属性。因此，我们可以在加入之前单独应用选择标准，以大幅减少加入的元组数量。

8.  **投影分布在θ连接上。**
    *   **Equivalence 1** 
        ![\pi_{L_{1}\cup L_{2}}(E_{1}\bowtie_{\theta}E_{2})=(\pi_{L_{1}}(E_{1}))\bowtie_{\theta}(\pi_{L_{2}}(E_{2}))  ](img/a9c17150fd7f52322219ab1fadf29432.png "Rendered by QuickLaTeX.com")

        **说明:**讨论选择的思路也可以用于投影。在这里，如果 L1 是一个只包含 E1 列的投影，而 L2 是另一个只包含 E2 列的投影，那么最好在连接之前在两个表上分别应用投影。这使得我们两边的列数量更少，从而有助于更容易的连接。

    *   **Equivalence 2** 
        ![\pi_{L_{1}\cup L_{2}}(E_{1}\bowtie_{\theta}E_{2})=\pi_{L_{1}\cup L_{2}}((\pi_{L_{1}\cup L_{3}}))\bowtie_{\theta}(\pi_{L_{2}\cup L_{4}}(E_{2})))  ](img/2202afcea0fdbb8c2b2c144304eeaab2.png "Rendered by QuickLaTeX.com")

        **解释:**这里，当在连接上应用投影 L1 和 L2 时，其中 L1 只包含 E1 的列，L2 只包含 E2 的列，我们可以引入另一列 E3(这在两个表之间是常见的)。然后，我们可以将 L1 和 L2 的投影分别应用于 E1 和 E2，以及添加的列 L3。L3 使我们能够加入。

9.  **Union and Intersection are commutative.** 
    ![E_{1}\ \cup E_{2}\ =\ E_{2}\ \cup\ E_{1}  ](img/9f3b45c604b9c98cb84b646122e89a33.png "Rendered by QuickLaTeX.com")
    ![E_{1}\ \cap E_{2}\ =\ E_{2}\ \cap\ E_{1}  ](img/3230f4ca8cb1dea6576ce2b508518a05.png "Rendered by QuickLaTeX.com")

    **说明:**并和交都是分配的；我们可以根据需要和方便的访问将任何表格括在括号中。

10.  **Union and Intersection are associative.** 
    ![(E_{1}\ \cup E_{2})\ \cup\ E_{3}=E_{1}\ \cup\ (E_{2}\ \cup\ E_{3})  ](img/9710ffcd627cf6a599d95608e07009ce.png "Rendered by QuickLaTeX.com")
    ![(E_{1}\ \cap E_{2})\ \cap\ E_{3}=E_{1}\ \cap\ (E_{2}\ \cap\ E_{3})  ](img/a077495864dc3d4897de772237814e9b.png "Rendered by QuickLaTeX.com")

    **说明:**并和交都是分配的；我们可以根据需要和方便的访问将任何表格括在括号中。

11.  **Selection operation distributes over the union, intersection, and difference operations.** 
    ![\sigma_{P}(E_{1}\ -\ E_{2})=\sigma_{P}(E_{1})\ -\ \sigma_{P}(E_{2})  ](img/cd8576016f763217b825cc344d7125b7.png "Rendered by QuickLaTeX.com")

    **说明:**在集合差中，我们知道只显示那些属于表 E1 而不属于表 E2 的元组。因此，对整个集合差应用选择条件相当于对单个表应用选择条件，然后应用集合差。这将减少设置差异步骤中的比较次数。

12.  **Projection operation distributes over the union operation.** 
    ![\pi_{L}(E_{1}\ \cup\ E_{2})=(\pi_{L}(E_{1}))\ \cup\ (\pi_{L}(E_{2}))  ](img/cd31c153a62322a81f53ab913059e909.png "Rendered by QuickLaTeX.com")

    **说明:**在计算 E1 和 E2 的并集之前应用单个投影比左表达式更优，即在并集步骤之后应用投影。

**极小性–**
如果没有规则可以从其他规则的任何组合中导出，那么一组等价规则被称为极小。当查询最小时，称之为最佳查询。

**示例–**
假设以下表格:

```
instructor(ID, name, dept_name, salary)
teaches(ID, course_id, sec_id, semester, year)
course(course_id, title, dept_name, credits)
```

**查询 1:找到音乐系所有导师的名字，以及他们所教课程的名称**

![$\pi_{name, title}(\sigma_{dept\_name=``Music"}(instructor \bowtie (teaches \bowtie \pi_{course\_id, title}(course))))$  ](img/34d110b3de140738c4a7f04cdabeecf9.png "Rendered by QuickLaTeX.com")

这里，dept_name 只是教师表的一个字段。因此，我们可以在加入表之前选择音乐教师，从而减少查询时间。

**优化查询:**
使用规则 7a，尽可能早地执行选择会减小要连接的关系的大小。
![$\pi_{name, title}((\sigma_{dept\_name=``Music"(instructor)}\bowtie(teaches\bowtie\pi_{course\_id, title}(course)))$  ](img/1f07b8db429baf7fd36762ad15930ee3.png "Rendered by QuickLaTeX.com")

**查询 2:找到 2009 年在 CSE 部门教过一门课程的所有导师的名字，以及他们教过的课程名称**

![$\sigma_{dept\_name=``CSE"}(\sigma_{year=2009}(instructor\bowtie teaches))$  ](img/8502c150656e19502958fa075dc53304.png "Rendered by QuickLaTeX.com")

**优化查询:**
我们可以进行“提前选择”，因此优化查询变成:
![$\sigma_{dept\_name=``CSE"}(instructor)\bowtie \sigma_{year=2009}(teaches)$  ](img/a279e274bc48f7d1157e90ee224a8160.png "Rendered by QuickLaTeX.com")

本文由**阿南尼亚·乌拜伊**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。