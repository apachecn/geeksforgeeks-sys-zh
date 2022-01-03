# 属性闭包算法及其应用

> 原文:[https://www . geesforgeks . org/attribute-闭包-算法-及其利用/](https://www.geeksforgeeks.org/attribute-closure-algorithm-and-its-utilization/)

一组功能描述符的闭包是从 F 可以推断出的所有功能描述符的集合 F <sup>+</sup> ，也称为完整的一组[功能依赖](https://www.geeksforgeeks.org/functional-dependency-and-attribute-closure/)。用 F <sup>+</sup> 表示。

**算法:属性闭包集**

```
Algorithm to compute a+, the closure of a under F
Result:= a;
while (changes to Result) do  
    for each B → Y in F do
        Begin
            if B ⊆  Result  then  Result := Result ∪  Y  
        End
```

**属性闭包的利用–**

*   [测试给定属性是否为超级键/候选键。](https://www.geeksforgeeks.org/finding-attribute-closure-and-candidate-keys-using-functional-dependencies/)
*   我们可以检查 FD X → Y 是否成立。
*   找出 F <sup>+</sup> 的另一种方法。

1.  Test whether attribute is superkey or not.

    **例:**
    设 R = (A，B，C，G，H，I)和 FD 的集合为 F = { A → B，A → C，CG → H，CG → I，B → H}

    **找出(AG) <sup>+</sup> 。**

    **结果=** {A，G}

    **第一个循环:**

    ```
    A → B includes B in the Result as A⊆ Result (which is AG), so Result := Result ∪ B. 
    Hence Result = {A, G, B}
    A → C causes Result to become ABCG.
    CG → H causes the Result to become ABCGH.
    CG → I causes the Result to become ABCGHI.
    B → H causes Result to become ABCGHI.
    ```

    **第二个循环:**

    ```
    A → B causes the Result to be unchanged i.e. ABCGHI (B is already part of the Result).
    A → C causes Result to be unchanged.
    CG → H causes the Result to be unchanged.
    CG → I causes the Result to be unchanged.
    B → H causes Result to be unchanged.
    ```

    在第二个循环结束时，结果不会改变，因此退出循环。

    **<sup>+</sup>= { a，b，c，g，h，I}**

    **结论:** AG 是一个超级键，因为其他所有属性都可以由其决定。
    T3】

2.  Check whether Fd exists :

    **例:**
    设 R = (A，B，C，G，H，I)和 FD 的集合为 F = { A →B，A → C，CG → H，CG → I，B → H}

    **检查 HB → I 是否成立**

    **结果=** {H，B}

    **第一个循环:**

    ```
    In A → B as A ⊆ Result (which is HB) so nothing will be added.
    In A → C nothing added.
    CG → H (CG ⊆ Result (which is HB) so nothing added)
    CG → I nothing added.
    B → H nothing added.
    ```

    在第一个循环结束时，结果不会改变，因此退出循环。

    **结论:** HB → I 不成立。
    T3】

3.  An alternate way to find Closure of FDs (F<sup>+</sup>).

    **示例:**
    给定关系 R (A，B，C，D，E，F)和一组 FDs F: {A → BC，E → CF，B → E，CD → EF}

    **查明{A，B }<sup>+</sup>T3 的关闭情况**

    **第一步:结果= AB**

    **第二步:第一个循环**

    ```
    Result = ABC for A → BC, A ⊆ Result so Result = Result ∪ BC.
    Result = ABC for E→ CF, E ∉ Result so Result = Result.
    Result = ABCE for B → E, B ⊆Result so Result = Result ∪ E.
    Result = ABCE for CD → EF, CD ∉ Result so Result = Result.
    ```

    步骤 2 之前的结果是 AB，步骤 2 之后的结果是 ABCE，两者不同，所以重复步骤 2。

    **第三步:第二次循环**

    ```
    Result = ABCE for A → BC, A ⊆ Result so Result = Result ∪ BC.
    Result = ABCEF for E → CF, E ⊆ Result so Result = Result ∪ CF.
    Result = ABCEF for B → E, B ⊆ Result so Result = Result ∪ E.
    Result = ABCEF for CD → EF, CD ∉ Result so Result = Result.
    ```

    步骤 3 之前的结果是 ABCE，步骤 3 之后的结果是 ABCEF，这是不同的，所以重复与步骤 3 相同的步骤。

    **第四步:第三个循环**

    ```
    Result = ABCEF for A → BC, A ⊆ Result so Result = Result ∪ BC.
    Result = ABCEF for E → CF, E ⊆ Result so Result = Result ∪ CF.
    Result = ABCEF for B → E, B ⊆ Result so Result = Result ∪ E.
    Result = ABCEF for CD → EF, CD ∉ Result so Result = Result.
    ```

    步骤 4 之前的结果是 ABCEF，步骤 3 之后的结果是 ABCEF，二者相同，所以停止。

    **所以{A，B} <sup>+</sup> 的闭合为{A，B，C，E，F}。**

    **结论:**对于每个属性/属性集，我们都能找到闭包。这导致 F <sup>+</sup> 。