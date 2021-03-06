# 数据挖掘:数据属性和质量

> 原文:[https://www . geesforgeks . org/data-mining-data-attributes-and-quality/](https://www.geeksforgeeks.org/data-mining-data-attributes-and-quality/)

先决条件–[数据挖掘](https://www.geeksforgeeks.org/data-mining/)
**数据:**是数据对象及其属性的存储方式。

*   **属性**是对象的属性或特征。比如说。一个人的发色、空气湿度等。
*   属性集定义了一个**对象**。**对象**也被称为实例或实体的记录。

不同**类型的属性或数据类型:**

1.  **名义属性:**
    名义属性只能提供足够的属性来区分一个对象和另一个对象。比如学生证号，人的性别。

2.  **序数属性:**
    序数属性值提供了足够的信息来对对象进行排序。如排名、成绩、身高
3.  **二元属性:**
    这是 0 和 1。其中 0 表示没有任何特征，1 表示包含任何特征。
4.  **数值属性:**它是定量的，这样的量可以用整数值或实数值来度量和表示，有两种类型
    **区间缩放属性:**
    它是以等尺寸单位的刻度来度量的，这些属性让我们可以比较如以 C 或 F 为单位的温度，从而属性值有顺序。

5.  **比率缩放属性:**
    比率的差异和比率都很显著。例如年龄、长度、体重。

**数据质量:为什么要对数据进行预处理？**
很多特征都是数据质量的决定因素，比如不完整、信息不连贯，这些都是现实世界中大数据库的共性。用于数据质量评估的因素有:

*   **准确性:**
    这里有很多可能导致数据有缺陷或不准确的原因。即具有可能是人为或计算机错误的错误属性值。

*   **完整性:**
    由于某些原因，可能会出现数据不完整的情况，例如销售的客户信息等感兴趣的属性&交易数据可能并不总是可用的。

*   **一致性:**
    不正确的数据也可能是由于命名约定或数据代码不一致，或输入字段格式不一致造成的。重复的元组也需要清理细节。

*   **时效性:**
    也影响数据质量。月底，几名销售代表未能按时提交销售记录。这些也是几个修正&调整流入月底之后。存储在数据库中的数据在每月之后的一段时间内是不完整的。

*   **可信度:**
    它反映了用户对数据的信任程度。

*   **可解释性:**
    它反映了用户理解数据的难易程度。