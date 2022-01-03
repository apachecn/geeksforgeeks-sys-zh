# 数字逻辑中的半加法器

> 原文:[https://www.geeksforgeeks.org/half-adder-in-digital-logic/](https://www.geeksforgeeks.org/half-adder-in-digital-logic/)

半加法器

2 位的加法是用一种叫做半加法器的组合电路完成的。输入变量是被加数和加数位，输出变量是求和和进位位。a 和 B 是两个输入位。

![halfadder1](img/7517f06b805a88613a80070b0196be8a.png)

**真值表:**

![ha_truth](img/4ecaa9ecf1ac5a53e373d3a6db20819e.png)

这里我们执行两个运算求和和进位，因此我们需要两个 K-映射，每个映射一个来导出表达式。

**逻辑表达式:**

**1)为 Sum:**

![](img/ba25c2e8687a3626e977b1d6b44daa6f.png)

**和=甲异或乙**

**2)为进位:**

![](img/dd7e52bbdc0e53b5356d9223cdbff0fa.png)

**进位= A 和 B**

**实施:**

![halfadder](img/b70bd3e49fb7c4a060ab429ed3cd600d.png)

**注:**

半加法器只有两个输入端，当执行多重加法时，不需要添加来自低位的进位。

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息