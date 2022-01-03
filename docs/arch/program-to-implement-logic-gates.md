# 实现逻辑门的程序

> 原文:[https://www . geesforgeks . org/program-to-implements-逻辑门/](https://www.geeksforgeeks.org/program-to-implement-logic-gates/)

一个[逻辑门](https://www.geeksforgeeks.org/digital-logic-logic-gates/)是任何数字电路的基本构件。它接受一两个输入，并根据这些输入产生输出。输出可以是高电平(1)或低电平(0)。逻辑门是用二极管或晶体管实现的。它也可以用真空管、光学、分子等电磁元件来构建。在计算机中，大多数电子电路是由逻辑门组成的。逻辑门用于创建执行计算、数据存储或展示面向对象编程的电路，尤其是继承的能力。

定义了七种基本逻辑门，它们是:

1.  与门，
2.  或门，
3.  非门，
4.  与非门，
5.  或非门，
6.  异或门和
7.  x or gate . x or gate . x or gate . x or gate . x or gate . x or gate . x or gate .

以下是关于它们及其实现的简要细节:

1.  **与门**
    如果两个输入都是 1，与门给出 1 的输出，否则给出 0。
    ![](img/a1078207ceede24afed803b4d7bcab90.png)

以下是使用各种方法实现与门的程序:

1.  使用产品方法。
2.  使用 if else 条件。
3.  使用“and (&)”运算符。

## 乘积法

```
// C program implementing the AND gate
// through product method.

#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a[5] = { 1, 0, 1, 0, 1 };
    int b[5] = { 0, 1, 1, 0, 0 };
    int i, product;

    for (i = 0; i < 5; i++) {

        // using product method
        product = a[i] * b[i];

        printf("\n %d AND %d = %d",
               a[i], b[i], product);
    }
}
```

## &操作员

```
// C program implementing the AND gate
// using & operator

#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a[5] = { 1, 0, 1, 0, 1 };
    int b[5] = { 0, 1, 1, 0, 0 };
    int i, and_ans;

    for (i = 0; i < 5; i++) {

        // using the & operator
        and_ans = a[i] & b[i];

        printf("\n %d AND %d = %d",
               a[i], b[i], and_ans);
    }
}
```

## 如果-否则

```
// C program implementing the AND gate
// using if and else condition

#include <stdio.h>
#include <stdlib.h>

int main()
{
    int a[5] = { 1, 0, 1, 0, 1 };
    int b[5] = { 0, 1, 1, 0, 0 };
    int i, ans;

    for (i = 0; i < 5; i++) {
        if (a[i] == 0 && b[i] == 0)
            ans = 0;

        else if (a[i] == 0 && b[i] == 1)
            ans = 0;

        else if (a[i] == 1 && b[i] == 0)
            ans = 0;
        else
            ans = 1;

        printf("\n %d AND %d = %d",
               a[i], b[i], ans);
    }
}
```

**Output:**

```
1 AND 0 = 0
 0 AND 1 = 0
 1 AND 1 = 1
 0 AND 0 = 0
 1 AND 0 = 0

```

*   **OR Gate**
    The OR gate gives an output of 1 if either of the two inputs are 1, it gives 0 otherwise.
    ![](img/79e98946966823cb7d235282ba9cd7d8.png)

    以下是使用各种方法实现与门的程序:

    1.  使用+运算符。
    2.  使用|运算符。
    3.  使用||运算符。
    4.  用 if else。

    ## +运算符

    ```
    // C program implementing the OR gate
    // using + operator

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        int a[5] = { 1, 0, 1, 0, 1 };
        int b[5] = { 0, 1, 1, 0, 0 };
        int i, or_ans;

        for (i = 0; i < 5; i++) {

            // using the + operator
            if (a[i] + b[i] > 0)
                or_ans = 1;
            else
                or_ans = 0;

            printf("\n %d AND %d = %d",
                   a[i], b[i], or_ans);
        }
    }
    ```

    ## |运算符

    ```
    // C program implementing the OR gate
    // using | operator

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        int a[5] = { 1, 0, 1, 0, 1 };
        int b[5] = { 0, 1, 1, 0, 0 };
        int i, or_ans;

        for (i = 0; i < 5; i++) {

            // using the | operator
            or_ans = a[i] | b[i];

            printf("\n %d AND %d = %d",
                   a[i], b[i], or_ans);
        }
    }
    ```

    ## ||运算符

    ```
    // C program implementing the OR gate
    // using || operator

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        int a[5] = { 1, 0, 1, 0, 1 };
        int b[5] = { 0, 1, 1, 0, 0 };
        int i, or_ans;

        for (i = 0; i < 5; i++) {

            // using the || operator
            or_ans = a[i] || b[i];

            printf("\n %d AND %d = %d",
                   a[i], b[i], or_ans);
        }
    }
    ```

    ## 如果-否则

    ```
    // C program implementing the OR gate
    // using if else

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {
        int a[5] = { 1, 0, 1, 0, 1 };
        int b[5] = { 0, 1, 1, 0, 0 };
        int i, or_ans;

        for (i = 0; i < 5; i++) {

            // using the if-else conditions
            if (a[i] == 0 && b[i] == 0)
                or_ans = 0;
            else
                or_ans = 1;

            printf("\n %d AND %d = %d",
                   a[i], b[i], or_ans);
        }
    }
    ```

    **Output:**

    ```
    1 AND 0 = 1
     0 AND 1 = 1
     1 AND 1 = 1
     0 AND 0 = 0
     1 AND 0 = 1

    ```

    *   **NAND Gate**
    The NAND gate (negated AND) gives an output of 0 if both inputs are 1, it gives 1 otherwise.
    ![](img/328c0c458f7964df8cf650d06a760ba2.png)

    以下是使用各种方法实现与非门的程序:

    1.  用 if else。
    2.  使用产品的补码。

    ## 如果-否则

    ```
    // C program implementing the NAND gate

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {

        int a[5] = { 1, 0, 1, 0, 1 };
        int b[5] = { 0, 1, 1, 0, 0 };
        int i, ans;

        for (i = 0; i < 5; i++) {
            if (a[i] == 1 && b[i] == 1)
                ans = 0;
            else
                ans = 1;
            printf("\n %d NAND %d = %d",
                   a[i], b[i], ans);
        }
    }
    ```

    ## 产品的补充

    ```
    // C program implementing the NAND gate

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {

        int a[5] = { 1, 0, 1, 0, 1 };
        int b[5] = { 0, 1, 1, 0, 0 };
        int i, ans;

        for (i = 0; i < 5; i++) {
            ans = !(a[i] * b[i]);
            printf("\n %d NAND %d = %d",
                   a[i], b[i], ans);
        }
    }
    ```

    **Output:**

    ```
    1 NAND 0 = 1
     0 NAND 1 = 1
     1 NAND 1 = 0
     0 NAND 0 = 1
     1 NAND 0 = 1

    ```

    *   **NOR Gate**
    The NOR gate (negated OR) gives an output of 1 if both inputs are 0, it gives 1 otherwise.
    ![](img/4f4b4bb8840542d08f42cb0eb23cb623.png)

    以下是使用各种方法实现或非门的程序:

    1.  使用+运算符。
    2.  用 if else。

    ## +运算符

    ```
    // C program implementing the NOR gate

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {

        int a[5] = { 1, 0, 1, 0, 1 };
        int b[5] = { 0, 1, 1, 0, 0 };
        int i, ans;

        for (i = 0; i < 5; i++) {
            ans = !(a[i] + b[i]);
            printf("\n %d NOR %d = %d",
                   a[i], b[i], ans);
        }
    }
    ```

    ## 如果-否则

    ```
    // C program implementing the NOR gate

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {

        int a[5] = { 1, 0, 1, 0, 1 };
        int b[5] = { 0, 1, 1, 0, 0 };
        int i, ans;

        for (i = 0; i < 5; i++) {
            if (a[i] == 0 && b[i] == 0)
                ans = 1;
            else
                ans = 0;
            printf("\n %d NOR %d = %d",
                   a[i], b[i], ans);
        }
    }
    ```

    **Output:**

    ```
    1 NOR 0 = 0
     0 NOR 1 = 0
     1 NOR 1 = 0
     0 NOR 0 = 1
     1 NOR 0 = 0

    ```

    *   **NOT Gate**

    它充当逆变器。它只需要一个输入。如果输入为 1，它会将结果反转为 0，反之亦然。
    ![](img/5fe3e4b601b311987f7f4b185461ffcd.png)

    以下是使用各种方法实现非门的程序:

    1.  使用！接线员。
    2.  用 if else。

    ## 如果-否则

    ```
    // C program implementing the NOT gate

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {

        int a[5] = { 1, 0, 1, 0, 1 };
        int i, ans;

        for (i = 0; i < 5; i++) {
            if (a[i] == 0)
                ans = 1;
            else
                ans = 0;
            printf("\n  NOT %d = %d", a[i], ans);
        }
    }
    ```

    ## ！操作员

    ```
    // C program implementing the NOT gate

    #include <stdio.h>
    #include <stdlib.h>

    int main()
    {

        int a[5] = { 1, 0, 1, 0, 1 };
        int i, ans;

        for (i = 0; i < 5; i++) {
            ans = !(a[i]);
            printf("\n  NOT %d = %d", a[i], ans);
        }
    }
    ```

    **Output:**

    ```
    NOT 1 = 0
      NOT 0 = 1
      NOT 1 = 0
      NOT 0 = 1
      NOT 1 = 0

    ```