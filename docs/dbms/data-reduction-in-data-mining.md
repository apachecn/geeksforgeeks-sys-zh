# 数据挖掘中的数据约简

> 原文:[https://www . geesforgeks . org/data-in-reduction-in-data-mining/](https://www.geeksforgeeks.org/data-reduction-in-data-mining/)

先决条件–[数据挖掘](https://www.geeksforgeeks.org/data-mining/)
数据约简的方法可以实现对原始数据的精简描述，这种描述在数量上要小得多，但保持了原始数据的质量。

**数据约简的方法:**
这些解释如下。

**1。数据立方体聚合:**
该技术用于以更简单的形式聚合数据。例如，假设您为 2012 年至 2014 年的分析收集了信息，这些数据包括您公司每三个月的收入。他们让你参与年度销售，而不是季度平均，所以我们可以这样总结数据，结果数据总结每年的总销售额，而不是每个季度。它总结了数据。

**2。降维:**
每当我们遇到任何弱重要的数据，我们就使用分析所需的属性。它减少了数据量，因为它消除了过时或冗余的功能。

*   **Step-wise Forward Selection –** 
    The selection begins with an empty set of attributes later on we decide best of the original attributes on the set based on their relevance to other attributes. We know it as a p-value in statistics. 

    假设数据集中有以下几个冗余属性。

```
Initial attribute Set: {X1, X2, X3, X4, X5, X6}
Initial reduced attribute set:  { }

Step-1: {X1}
Step-2: {X1, X2}
Step-3: {X1, X2, X5}

Final reduced attribute set: {X1, X2, X5} 
```

*   **Step-wise Backward Selection –** 
    This selection starts with a set of complete attributes in the original data and at each point, it eliminates the worst remaining attribute in the set. 

    假设数据集中有以下几个冗余属性。

```
Initial attribute Set: {X1, X2, X3, X4, X5, X6}
Initial reduced attribute set:  {X1, X2, X3, X4, X5, X6 }

Step-1: {X1, X2, X3, X4, X5}
Step-2: {X1, X2, X3, X5}
Step-3: {X1, X2, X5}

Final reduced attribute set: {X1, X2, X5} 
```

*   **前向和后向选择的结合–**
    它可以让我们去掉最差的属性，选择最好的属性，节省时间，让流程更快。

**3。** [**数据压缩**](https://www.geeksforgeeks.org/difference-between-lossy-compression-and-lossless-compression/) **:**
数据压缩技术使用不同的编码机制(霍夫曼编码&游程编码)来减小文件的大小。我们可以根据它们的压缩技术将其分为两种类型。

*   **无损压缩–**
    编码技术(游程编码)允许简单且最小的数据大小缩减。无损数据压缩使用算法从压缩数据中恢复精确的原始数据。
*   **有损压缩–**
    离散小波变换技术、主成分分析等方法就是这种压缩的例子。例如，JPEG 图像格式是一种有损压缩，但我们可以找到与原始图像等效的含义。在有损数据压缩中，解压缩后的数据可能与原始数据不同，但足以从中检索信息。

**4。** [**【数值简化】**](https://www.geeksforgeeks.org/numerosity-reduction-in-data-mining/) **:**
在这种简化技术中，实际数据用数学模型或数据的较小表示代替实际数据，重要的是只存储模型参数。或者非参数方法，例如聚类、直方图、采样。有关减少数字的更多信息，请访问以下链接:

**5。离散化&概念层次操作:**
数据离散化技术用于将连续性质的属性划分为具有区间的数据。我们用小间隔的标签来代替属性的许多常数值。这意味着挖掘结果以简明易懂的方式显示。

*   **自上而下的离散化–**
    如果你首先考虑一个或几个点(所谓的断点或分裂点)来划分整个属性集，并重复这种方法直到最后，那么这个过程被称为自上而下的离散化，也称为分裂。
*   **自下而上的离散化–**
    如果首先将所有常数值视为分割点，通过组合区间中的邻域值来丢弃一些常数值，这个过程称为自下而上的离散化。

**概念层次:**
它通过收集然后将低级概念(如年龄为 43)替换为高级概念(如中年或高级)来减少数据量。

对于数字数据，可以遵循以下技术:

*   [**【宁滨】**](https://www.geeksforgeeks.org/binning-in-data-mining/)**—**
    宁滨是将数值变量转变为分类对应变量的过程。分类对应项的数量取决于用户指定的箱数。
*   **直方图分析–**
    像宁滨的过程一样，直方图用于将属性 X 的值划分为称为括号的不相交范围。有几种分区规则:
    1.  **等频率划分:**根据数值在数据集中出现的次数划分数值。
    2.  **等宽分割:**根据面元的数量，即 0-20 范围内的一组值，在固定的间隙内对值进行分割。
    3.  **聚类:**将相似的数据分组在一起。