# 无损连接和依赖保持分解

> 原文:[https://www . geesforgeks . org/无损连接和依赖保持分解/](https://www.geeksforgeeks.org/lossless-join-and-dependency-preserving-decomposition/)

当关系模型中的关系不是合适的范式时，关系的分解就完成了。如果分解是无损连接和依赖保持，则关系 R 被分解成两个或多个关系。

**无损连接分解**

如果我们把关系分解成 R1 和 R2 的关系，

*   如果 R1 ⋈ R2 ⊃ R，分解是有损耗的
*   如果 R1 ⋈ R2 = R，分解是无损的

**要使用 FD 集检查无损连接分解，必须满足以下条件:**

1.  R1 和 R2 的属性联合必须等于 R 的属性。R 的每个属性必须在 R1 或 R2。

    ```
     Att(R1) U Att(R2) = Att(R)
    ```

2.  R1 和 R2 属性的交集不能为空。

    ```
     Att(R1) ∩ Att(R2) ≠ Φ
    ```

3.  公共属性必须是至少一个关系(R1 或 R2)

    ```
     Att(R1) ∩ Att(R2) -> Att(R1) or Att(R1) ∩ Att(R2) -> Att(R2)
    ```

    的关键字

例如，具有 FD 集{A->BC}的关系 R (A，B，C，D)被分解为 R1(ABC)和 R2(AD)，这是无损连接分解，如下所示:

1.  第一个条件成立，因为 Att(R1)U Att(R2)=(ABC)U(AD)=(ABCD)= Att(R)。
2.  第二个条件成立，因为 Att(R1)∞；Att(R2)=(ABC)∞(AD)≠φ
3.  第三个条件成立，因为 Att(R1) ∩ Att(R2) = A 是 R1(ABC)的一个键，因为给出了 A->BC。

**依赖保持分解**

如果我们把关系 R 分解成关系 R1 和 R2，那么 R 的所有从属关系要么必须是 R1 或 R2 的一部分，要么必须是 R1 和 R2 的 FD 的组合。
例如，具有 FD 集{A- > BC}的关系 R (A，B，C，D)被分解为 R1(ABC)和 R2(AD)，这是因为 FD A- > BC 是 R1(ABC)的一部分，所以保持了依赖性。

**GATE 问题:考虑一个模式 R(A，B，C，D)和函数依赖 A- > B 和 C- > D，那么 R 分解成 R1(AB)和 R2(CD)就是【GATE-CS-2001】**
A .依赖保持和无损连接
B .无损连接但不保持依赖
C .依赖保持但不无损连接
D .不保持依赖且不无损连接

**回答:**对于无损连接分解，这三个条件必须成立:

1.  使(R1) U 使(R2) = ABCD =使(r)成为
2.  Att(R1)∞；Att(R2)=φ，违反了无损连接分解的条件。因此，分解不是无损的。

对于依赖保持分解，在 R1(AB)可以保证
A- > B，在 R2(CD)可以保证 C- > D。因此它是依赖保持分解。
那么，正确的选项是
本文由 **Sonal Tuteja** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。