# 数据分析中的属性及其类型

> 原文:[https://www . geesforgeks . org/attributes-and-its-type-in-data-analytics/](https://www.geeksforgeeks.org/attributes-and-its-types-in-data-analytics/)

在本文中，我们将讨论数据分析中的属性及其各种类型。为了更好地理解，我们还将借助示例介绍属性类型。所以我们一个一个来讨论。

**属性:**
属性是作为数据实体的属性出现的数据项。机器学习文献倾向于使用特征这个术语，而统计学家更喜欢变量这个术语。
**示例–**
让我们考虑一个示例，如姓名、地址、电子邮件等。是联系信息的属性。

给定属性的感知值称为观察值。一个属性的多样性是由一组可行值维持的——名义值、二进制值、序数或数值。

**属性类型:**

*   **Nominal Attributes :**
    Nominal means “relating to names” . The utilities of a nominal attribute are sign or title of objects . Each value represents some kind of category, code or state, and so nominal attributes are also referred to as categorial.

    **例–**
    假设肤色和学历是表达人称对象的两个属性。在我们的实现中，肤色的可能值是黑色、白色、棕色。教育状况的属性可以包含价值观——本科、研究生、预科。肤色和教育程度都是名义属性。

*   **Binary Attributes :**
    A binary attribute is a category of nominal attributes that contains only two classes: 0 or 1, where 0 often tells that the attribute is not present, and 1 tells that it is existing. Binary attributes are mentioned as Boolean if the two conditions agree to true and false.

    **示例–**
    给定属性“饮酒者讲述患者项目”，1 表示饮酒者饮酒，0 表示患者不饮酒。同样，假设患者接受了一项医学测试，该测试有两种可行的结果。

*   **Ordinal Attributes :**
    An ordinal attribute is an attribute with a viable advantage that has a significant sequence or ranking among them, but the enormity between consecutive values is not known.

    **示例–**
    假设食物数量对应于餐厅提供的菜肴种类。名义属性有三个可能的值:开胃菜、主菜、套餐。

    这些值有一个有意义的序列，对应于不同的食物数量，然而，我们不能从这些值中分辨出一个中值比一个大值大多少。

*   **Numeric Attributes :**
    A numeric attribute is calculable, that is, it is a quantifiable amount that constitutes integer or real values.
    Numeric attributes can be of two types as follows: Interval- scaled, and Ratio – scaled.

    我们一个一个来讨论。

    1.  **Interval – Scaled Attributes :**
        Interval – scaled attributes are calculated on a lamella of uniform- size units. The values of interval-scaled attributes have order and can be positive, 0, or negative. Thus, in addition to providing a ranking of values, such attributes allow us to compare and quantify the difference between values.

        **示例–**
        温度属性是一个时间间隔，按比例缩放。我们每一天都有不同的温度值，每一天都是一个整体。通过对这些值进行排序，我们得到了关于温度的实体排列。此外，我们可以量化值与值之间的差异，例如，20 摄氏度的温度比 15 摄氏度的温度高 5 度

    2.  **Ratio – Scaled Attributes :**
        A ratio – scaled attribute is a category of a numeric attribute with imminent or fix zero points. In inclusion, the entities are structured, and we can also compute the difference between values, as well as the mean, median, and mode.

        **示例–**
        开尔文(K)温标具有被认为是真正的零点。正是在这个点上，由物质组成的微小粒子的动能为零。

*   **离散属性:**
    离散属性具有有限或受限的无限值集，这些值可能显示为整数。肤色、饮酒者、医疗报告和饮酒量等属性都有有限的值，因此是离散的。
*   **Continuous Attribute :**
    A continuous attribute has real numbers as attribute values.

    **示例–**
    身高、体重和温度都有真实值。真实值只能用有限的位数来表示和测量。连续属性通常表示为浮点变量。