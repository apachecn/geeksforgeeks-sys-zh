# 布尔代数的性质

> 原文:[https://www . geesforgeks . org/properties-of-boolean-代数/](https://www.geeksforgeeks.org/properties-of-boolean-algebra/)

**开关代数**也被称为**布尔代数**。它用于分析数字门和电路。它是对二进制数，即“0”和“1”进行数学运算的逻辑。布尔代数包含基本运算符，如与、或、非等。操作用“.”表示代表“与”，代表“或”。可以对用大写字母如“A”、“B”等表示的变量进行运算。

**开关代数的性质–**

*   **Annulment law –** a variable ANDed with 0 gives 0, while a variable ORed with 1 gives 1, i.e.,

    A.0 = 0
    A + 1 = 1

*   **Identity law –** in this law variable remain unchanged it is ORed with ‘0’ or ANDed with ‘1’, i.e.,

    a1 = A
    A+0 = A

*   **Idempotent law –** a variable remain unchanged when it is ORed or ANDed with itself, i.e.,

    A + A = A
    A.A = A

*   **Complement law –** in this Law if a complement is added to a variable it gives one, if a variable is multiplied with its complement it results in ‘0’, i.e.,

    A + A' = 1
    A.A' = 0

*   **Double negation law –** a variable with two negation its symbol gets cancelled out and original variable is obtained, i.e.,

    ((甲)')' =甲

*   **Commutative law –** a variable order does not matter in this law, i.e.,

    A + B = B + A
    A.B = B.A

*   **Associative law –** the order of operation does not matter if the priority of variables are same like ‘*’ and ‘/’, i.e.,

    A+(b+ C)=(A+B)+C
    A(B . C)=(A . B)。C

*   **Distributive law –** this law governs opening up of brackets, i.e.,

    A.(b+ C)=(A . B)+(A . C)
    A+(B . C)=(A+B)。(甲+丙)

*   **Absorption law –**:-This law involved absorbing the similar variables, i.e.,

    A.(A+B) = A
    A + AB = A

*   **De Morgan law –** the operation of an AND or OR logic circuit is unchanged if all inputs are inverted, the operator is changed from AND to OR, the output is inverted, i.e.,

    (甲.乙)' =甲'+乙'
    (甲+乙)' =甲'。' b '

    **GATE CS 角题**

    练习下列问题将帮助你测试你的知识。所有的问题在前几年的 GATE 考试或 GATE 模拟考试中都被问过。强烈建议你练习一下。

    1.  [GATE CS 2013，第 65 题](https://www.geeksforgeeks.org/gate-gate-cs-2013-question-21/)
    2.  [GATE CS 2009，问题 6](https://www.geeksforgeeks.org/gate-gate-cs-2009-question-6/)
    3.  [GATE CS 2007，问题 85](https://www.geeksforgeeks.org/gate-gate-cs-2007-question-33/)

    **参考文献–**
    [布尔代数–维基百科](https://en.wikipedia.org/wiki/Boolean_algebra)
    [德摩根定律–维基百科](https://en.wikipedia.org/wiki/De_Morgan%27s_laws)

    本文由**瓦伊沙里·巴蒂亚**供稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。