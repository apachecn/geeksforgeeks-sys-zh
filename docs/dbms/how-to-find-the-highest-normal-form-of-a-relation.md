# 如何求一个关系的最高范式

> 原文:[https://www . geeksforgeeks . org/如何找到关系的最高范式/](https://www.geeksforgeeks.org/how-to-find-the-highest-normal-form-of-a-relation/)

要理解这个话题，你应该对[功能依赖&候选键](https://www.geeksforgeeks.org/finding-attribute-closure-and-candidate-keys-using-functional-dependencies/)和[范式](https://www.geeksforgeeks.org/normal-forms-in-dbms/)有一个基本的了解。

**求关系最高范式的步骤:**

1.  找到关系中所有可能的候选键。
2.  将所有属性分为两类:质数属性和非质数属性。
3.  检查 1 <sup>st</sup> 正常，然后检查 2 <sup>nd</sup> 等。如果不满足第 n <sup>个</sup>范式条件，则最高范式为 n-1。

**实施例 1。求一个关系的最高范式** R(A，B，C，D，E)与 FD 集{A- > D，B- > A，BC- > D，AC- > BE}

**第一步。**我们可以看到，(AC) <sup>+</sup> ={A，C，B，E，D}但是它的子集都不能决定关系的所有属性，所以 AC 会是候选键。A 可以从 B 中派生出来，所以我们可以用 B 替换 AC 中的 A。所以 BC 也将是候选键。所以会有两个候选键{AC，BC}。

**第二步。**在本例中，质数属性是候选关键字{A，B，C}的一部分，其他属性在本例中是非质数{D，E}的属性。

**第三步。**关系 R 处于 1 <sup>st</sup> 范式，因为关系数据库管理系统不允许多值或复合属性。

该关系不在第 2 <sup>和第 1</sup>范式中，因为 A- > D 是部分依赖关系(A 是候选关键字 AC 的子集，确定非素数属性 D)，第 2 <sup>和第 3</sup>范式不允许部分依赖关系。

所以最高的范式将是 1 <sup>st</sup> 范式。

**例 2。**求一个关系的最高范式 **R(A，B，C，D，E)，FD 设为{BC- > D，AC- > BE，B- > E}**

**第一步。**我们可以看到，(AC) <sup>+</sup> ={A，C，B，E，D}但是它的子集都不能决定关系的所有属性，所以 AC 会是候选键。a 或 C 不能从关系的任何其他属性派生，因此将只有 1 个候选键{AC}。

**第二步。**在本例中，质数属性是候选关键字{A，C}的一部分，其他属性在本例中是非质数{B，D，E}。

**第三步。**关系 R 处于 1 <sup>st</sup> 范式，因为关系数据库管理系统不允许多值或复合属性。

该关系处于 2 <sup>nd</sup> 范式，因为 BC- > D 处于 2 <sup>nd</sup> 范式(BC 不是候选键 AC 的适当子集)，AC- > BE 处于 2 <sup>nd</sup> 范式(AC 是候选键)，B- > E 处于 2 <sup>nd</sup> 范式(B 不是候选键 AC 的适当子集)。

这种关系不在 3 <sup>rd</sup> 范式中，因为在 BC->D(BC 既不是超级键，D 也不是质数属性)和 B->E(B 既不是超级键，E 也不是质数属性)中，但是为了满足 3 <sup>rd</sup> 范式，FD 的 LHS 应该是超级键，RHS 应该是质数属性。

所以关系的最高范式将是第 2 <sup>和第 2</sup>范式。

**例 3。**求关系的最高范式 **R(A，B，C，D，E)** 与 **FD 集{B- > A，A- > C，BC- > D，AC- > BE}**

**第一步。**我们可以看到，(B) <sup>+</sup> ={B，A，C，D，E}，所以 B 会是候选键。B 可以通过使用 AC- > B(将 AC- > BE 分解为 AC- > B 和 AC- > E)从 AC 衍生而来。所以 AC 会超级关键但是(C) <sup>+</sup> ={C}和(A) <sup>+</sup> ={A，C，B，E，D}。所以 A(AC 的子集)将是候选键。所以会有两个候选键{A，B}。

**第二步。**在本例中，质数属性是候选关键字{A，B}的一部分，其他属性在本例中是非质数{C，D，E}。

**第三步**。关系 R 是 1 <sup>st</sup> 范式，因为关系数据库管理系统不允许多值或复合属性。

这种关系处于 2 <sup>nd</sup> 范式，因为 B- > A 处于 2 <sup>nd</sup> 范式(B 为超键)，A- > C 处于 2 <sup>nd</sup> 范式(A 为超键)，BC- > D 处于 2 <sup>nd</sup> 范式(BC 为超键)，AC- > BE 处于 2 <sup>nd</sup> 范式(AC 为超键)。

关系是 3 <sup>第 3</sup>范式，因为所有 FD 的 LHS 都是超级键。这种关系在 BCNF，因为所有 FD 的所有 LHS 都是超级钥匙。所以最高范式是 BCNF。

Sonal Tuteja 供稿。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。