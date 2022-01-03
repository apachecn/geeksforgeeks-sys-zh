# 数据综合的基本方法

> 原文:[https://www . geesforgeks . org/basic-approach-for-data-generation-DWDM/](https://www.geeksforgeeks.org/basic-approaches-for-data-generalization-dwdm/)

**数据概化**是用更高层次的概念代替相对低层次的值来汇总数据的过程。这是一种描述性的[数据挖掘](https://www.geeksforgeeks.org/data-mining/)的形式。

数据泛化有两种基本方法:

**1。数据立方体方法:**

*   这也被称为 OLAP 方法。
*   这是一种有效的方法，因为它有助于制作过去的销售图。
*   在这种方法中，计算和结果存储在数据立方体中。
*   它对数据立方体使用上滚和下钻操作。
*   这些操作通常涉及聚合函数，例如 count()、sum()、average()和 max()。
*   然后，这些物化视图可以用于决策支持、知识发现和许多其他应用。

**2。属性导向归纳:**

*   它是一种在线数据分析、面向查询和基于泛化的方法。
*   在这种方法中，我们根据相关数据集中每个属性的不同值来执行泛化。在相同元组被合并且它们各自的计数被累加以便执行聚合之后。
*   它在提交 OLAP 或数据挖掘查询进行处理之前执行离线聚合。
*   另一方面，面向属性的归纳方法，至少在其最初的提议中，是一种面向关系数据库查询的、通用的基础(在线数据分析技术)。
*   它不限于特定的测量或分类数据。
*   Attribute oriented induction approach uses two method :

    **(一)。**属性移除。
    **(二)。**属性泛化。