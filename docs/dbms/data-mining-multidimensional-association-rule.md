# 数据挖掘多维关联规则

> 原文:[https://www . geesforgeks . org/data-mining-多维-关联-rule/](https://www.geeksforgeeks.org/data-mining-multidimensional-association-rule/)

在本文中，我们将讨论多维关联规则。此外，我们将讨论每个例子。我们一个一个来讨论。

**多维[关联规则](https://www.geeksforgeeks.org/association-rule/) :**

在多维关联规则中，质量可以是绝对的，也可以是定量的。

*   数量特征是数字的，并且巩固了顺序。
*   数字特征应该离散化。
*   多维关联规则包含多个度量。
*   **示例–**购买(X，“IBM 笔记本电脑”)购买(X，“惠普喷墨打印机”)

**挖掘多维隶属规则的途径:**
挖掘多维隶属规则的三种途径如下。

1.  **Using static discretization of quantitative qualities :**
    *   离散化是静态的，发生在挖掘之前。
    *   离散化的归因被视为未减轻的。
    *   使用 apriori 计算来定位所有 k 正则谓词集(这需要 k 或 k+1 个表输出)。正则谓词集的每个子集都应该是连续的。

    **示例–**
    如果在信息块中，3D 长方体(年龄、支付、购买)是连续的，则表明(年龄、支付)、(年龄、购买)、(支付、购买)同样是规则的。

    **注意–**
    信息块适合挖掘，因为它们可以加快挖掘速度。n 维信息立方体的单元与谓词单元相关。

2.  **Using powerful discretization of quantitative traits :**
    *   称为挖掘定量关联规则。
    *   数值属性逐渐离散化。

    **示例–**:

    ```
    age(X, "20..25") Λ income(X, "30K..41K")buys ( X, "Laptop Computer") 
    ```

3.  **Grid FOR TUPLES :**
    **Using distance based discretization with bunching –**
    This id dynamic discretization measure that considers the distance between information focuses. It includes a two stage mining measure as following.
    *   执行群聚以发现包含的时间段。
    *   通过寻找发生在一起的群体聚会来获得隶属规则。

    **由此产生的指南可能满足–**

    *   标准前驱中的束与后续中的规则组明确相连。
    *   先驱中的聚在一起。
    *   一束束在随后发生在一起。