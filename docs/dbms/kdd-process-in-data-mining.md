# 数据挖掘中的 KDD 过程

> 原文:[https://www.geeksforgeeks.org/kdd-process-in-data-mining/](https://www.geeksforgeeks.org/kdd-process-in-data-mining/)

[**【数据挖掘】**](https://www.geeksforgeeks.org/data-mining/)**–数据库中的知识发现** (KDD)。

**我们为什么需要数据挖掘？**
我们每天可以处理的来自商业交易、科学数据、传感器数据、图片、视频等信息量不断增加。因此，我们需要一个能够提取可用信息本质并自动生成报告、
视图或数据摘要的系统，以便更好地进行决策。

**为什么在商业中使用数据挖掘？**
数据挖掘通过以下方式在商业中用于做出更好的管理决策:

*   **数据自动汇总**
*   **提取存储信息的本质**。
*   **发现原始数据中的模式。**

**数据挖掘**也称为数据库中的知识发现，是指从存储在数据库中的数据中提取隐含的、以前未知的和潜在有用的信息。

**KDD 进程涉及的步骤:**

![](img/d1c66712f4945325955e792343c95ecf.png)

KDD 进程

1.  ***数据清理*** :数据清理定义为从采集中去除有噪声和不相关的数据。
    *   ***缺失值*** 情况下的清理。
    *   清理**数据，其中噪声是随机或方差误差。**
    *   **使用 ***数据差异检测*** 和 ***数据转换工具*** 进行清理。**
2.  *****数据集成*** :数据集成定义为多个来源的异构数据组合在一个公共来源(DataWarehouse)中。

    *   数据集成使用 ***数据迁移工具*** 。
    *   数据集成使用 ***数据同步工具*** 。
    *   数据集成使用**(提取-加载-转换)流程。**** 
3.  *******数据选择*** :数据选择定义为从数据集合中决定和检索与分析相关的数据的过程。

    *   数据选择使用 ***神经网络*** 。
    *   数据选择使用 ***决策树*** 。
    *   数据选择使用 ***朴素贝叶斯*** 。
    *   数据选择使用 ***聚类******回归*** 等。**** 
4.  *******Data Transformation***: Data Transformation is defined as the process of transforming data into appropriate form required by mining procedure. 

    数据转换是一个两步过程:

    *   ***【数据映射】*** :将元素从源库分配到目的地以捕获转换。
    *   ***代码生成*** :实际转化程序的创建。**** 
5.  *******数据挖掘*** :数据挖掘被定义为用于提取潜在有用模式的巧妙技术。

    *   将任务相关数据转换为 ***模式*** 。
    *   使用 ***分类*** 或 ***表征*** 决定模型目的。**** 
6.  *******模式评估*** :模式评估定义为基于给定的度量来识别表示知识的严格递增的模式。

    *   找到每个图案的 ***兴趣度评分*** 。
    *   使用*****可视化*** 使数据易于用户理解。****** 
7.  *******知识表示*** :知识表示定义为利用可视化工具表示数据挖掘结果的技术。

    *   生成 ***报告*** 。
    *   生成 ***表*** 。
    *   生成 ***判别规则******分类规则******表征规则*** 等。**** 

******注** :**** 

*   ****KDD 是一个****迭代的过程**，在这个过程中，可以增强评估措施、细化挖掘、整合和转化新数据，以获得不同的、更合适的结果。******
*   ****数据库的 ***预处理*** **由**数据清理**和**数据集成**组成。******

*****参考文献*** :
[数据挖掘:概念和技术](https://books.google.co.in/books/about/Data_Mining_Concepts_and_Techniques.html?id=pQws07tdpjoC)**