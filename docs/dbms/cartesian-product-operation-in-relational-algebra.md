# 关系代数中的笛卡尔乘积运算

> 原文:[https://www . geesforgeks . org/cartesian-product-operation-in-relational-代数/](https://www.geeksforgeeks.org/cartesian-product-operation-in-relational-algebra/)

先决条件–[关系代数](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/)
我们已经意识到关系只不过是一组元组，这里我们将有 2 组元组。

在对两组元组上的两个关系应用笛卡尔乘积时，它将从左集合(关系)中逐个取出每个元组，并将它与右集合(关系)中的所有元组配对。

所以，具有 p 度的两个关系 A(R1，R2，R3，…，Rp)和具有 n 度的 B(S1，S2，S3，…，Sn)的 CROSS PRODUCT，是具有 p + n 度属性的关系 C(R1，R2，R3，…，Rp，S1，S2，S3，…，Sn)。

CROSS PRODUCT 是一种二元集合运算手段，一次我们可以对两个关系应用该运算。但是我们正在执行操作的两个关系没有相同类型的元组，这意味着这两个关系的联合兼容性(或类型兼容性)不是必需的。

**符号:**

```
A ✕ S
```

其中 a 和 s 是关系，
符号'✕'用于表示叉积运算符。

**示例:**
考虑下面的两个关系 STUDENT(SNO，FNAME，LNAME)和 DETAIL(ROLLNO，AGE):

<center>

| SNO | 姓氏 | LNAME |
| --- | --- | --- |
| one | 艾伯特 | 辛格 |
| --- | --- | --- |
| Two | Honora | 嘿，嘿 |
| --- | --- | --- |

</center>

<center>

| 罗龙 | 年龄 |
| --- | --- |
| five | Eighteen |
| --- | --- |
| nine | Twenty-one |
| --- | --- |

</center>

在学生和细节上应用叉积:

```
STUDENT ✕ DETAILS
```

<center>

| SNO | 姓氏 | LNAME | 罗龙 | 年龄 |
| --- | --- | --- | --- | --- |
| one | 艾伯特 | 辛格 | five | Eighteen |
| --- | --- | --- | --- | --- |
| one | 艾伯特 | 辛格 | nine | Twenty-one |
| --- | --- | --- | --- | --- |
| Two | Honora | 嘿，嘿 | five | Eighteen |
| --- | --- | --- | --- | --- |
| Two | Honora | 嘿，嘿 | nine | Twenty-one |
| --- | --- | --- | --- | --- |

</center>

我们可以观察到 STUDENT 关系中的元组个数是 2，DETAIL 中的元组个数是 2。因此，在执行 CROSS PRODUCT 的结果关系中，元组的数量是 2*2 = 4。

笛卡尔乘积运算的要点:

1.  叉积运算得到的关系的基数(元组数)等于第一个关系中的属性数(比如 m)乘以第二个关系中的属性数(比如 n)。

    ```
    Cardinality = m*n
    ```

2.  具有 p 度的两个关系 A(R1、R2、R3、…、Rp)和具有 n 度的 B(S1、S2、S3、…、Sn)的叉积，是具有 p + n 度属性的关系 C(R1、R2、R3、…、Rp、S1、S2、S3、…、Sn)。

    ```
    Degree = p+n
    ```

3.  在 [SQL](https://www.geeksforgeeks.org/sql-tutorial/) 中，可以使用交叉连接应用笛卡尔乘积(叉积)。
4.  In general, we don’t use cartesian Product unnecessarily, which means without proper meaning we don’t use Cartesian Product. Generally, we use Cartesian Product followed by a Selection operation and comparison on the operators as shown below :

    ```
    σ A=D (A ✕ B)
    ```

    上面的查询给出了有意义的结果。

    而 Select 和 Cross Product 操作的这种组合非常受欢迎，JOIN 操作就是受这种组合的启发。

5.  CROSS PRODUCT 是一种二元集合运算手段，一次我们可以对两个关系应用该运算。