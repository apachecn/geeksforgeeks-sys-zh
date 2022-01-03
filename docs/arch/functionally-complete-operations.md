# 功能完成操作

> 原文:[https://www . geesforgeks . org/functional-complete-operations/](https://www.geeksforgeeks.org/functionally-complete-operations/)

先决条件–[功能完备性](https://www.geeksforgeeks.org/digital-logic-functionality-completeness/)
开关函数由二进制变量、逻辑运算符号以及常数 0 和 1 表示。当每个开关函数都可以用其中的操作来表示时，那么只有一组操作被称为功能完备的。

1.  集合(与、或、非)是一个功能完备的集合。
2.  集合(与，非)被认为是功能完备的。
3.  集合(或，非)也被认为是功能完备的。

这里，
集合(AND，NOT)被认为是功能完整的，因为(OR)可以使用“AND”和“NOT”操作导出。
**例:**

```
(X + Y) = (X'.Y')'
X'= compliment of X.
Y'= compliment of Y.
```

集合(或，非)在功能上是完整的，因为(与)可以用“或”和“非”运算导出。
**例:**

```
(X.Y) = (X' + Y')'
```

**注:**
一个函数可以是完全功能完备的，也可以是部分功能完备的，或者，根本不是功能完备的。

*   **Example-1:**
    If a function, **f(X, Y, Z)= (X’ + YZ’)** then check whether its functionally complete or not?
    Put Z = Y in the above function,
    Therefore,

    ```
     f(X, Y, Y)= (X' + YY')
              = (X' + 0) since, Y.Y'=0
              = X' (It is compliment i.e., NOT)
    ```

    再次，将 X= X '和 Z= Y '放入上述函数中，
    因此，

    ```
    f(X', Y, Y')= (X')'+ Y(Y')'
               = (X + Y.Y) since, (X')'= X and (Y')'= Y
               = (X + Y) since, Y.Y= Y (It is OR operator)
    ```

    因此，您可以从上面的函数中导出“非”和“或”运算符，因此该函数在功能上是完全完整的。

*   **Example-2:**
    If a function, **f(X, Y)= (X’Y)** then check whether it is functionally complete or not?
    Put X= (X’),
    Therefore,

    ```
     f(X', Y)= (X')'.Y = X.Y (It is AND operator)
    ```

    这里，AND 运算符是派生出来的，现在你需要派生 NOT 运算符来使它在功能上完整。
    如果你把 Y= 1，

    ```
    Then f(X, 1)= (X'), It is NOT operator.
    ```

    因此，这个函数在功能上是部分完整的，因为您需要(1)导出 NOT 运算符。
    **注:**每当你借助常数(1 和 0)使一个函数功能完备时，这个函数就被称为部分完备函数。

*   **Example-3:**
    If a function **f(X, Y, Z)= (XY + YZ + ZX)** then check whether this function is functionally complete or not?
    In order to make a function functionally complete, deriving NOT operator is necessary but here, there is no compliment in the function so, it is not possible to derive NOT operator.

    因此，该功能在功能上根本不完整。