# 组合电路的构造

> 原文:[https://www . geeksforgeeks . org/组合电路构造/](https://www.geeksforgeeks.org/construction-of-combinational-circuits/)

一个[组合电路](https://www.geeksforgeeks.org/difference-between-combinational-and-sequential-circuit/)由逻辑门组成，其在任何时刻的输出都直接由当前的输入组合决定，而不考虑先前的输入。组合电路的例子:加法器、减法器、转换器和编码器/解码器。

在这里，我们将学习如何使用四个通用步骤来构造和分析任何类型的组合电路。我将借助一个组合电路来解释这个技巧，你可以用同样的技巧来实现其他组合电路。

以下是构造和分析任何组合电路的四个步骤。

*   **步骤-1:** 识别电路的输入和输出数量。
    首先，我们必须考虑电路的输入和输出，考虑我们想对电路执行哪种逻辑操作。
    比如我们要创建一个可以加两位的电路。为此，我们需要两个输入(一个用于第一位(A)，另一个用于第二位(B))和两个输出，一个用于两位的和(S)，另一个用于进位(C)。

我们总共需要 2 个输入和 2 个输出。我们的第一步就完成了。

*   **Step-2:** Creating the Truth Table.
    In this step we have to create truth table for our circuit so for this first we will create input columns and list all the possible combinations of inputs. In our case **2** bits can have maximum **4** combinations **(00 01 10 11)**.
    Now in output, we have two columns (Sum and Carry) as discussed earlier. Now we have to fill output columns in such a way that for which logical operation we are constructing circuit.

    在我们的电路中，我们需要加法，所以我们将这些输入位相加，并将这些位的总和写入(sum)列，如果产生进位，我们将写入 **1** 否则写入。

    **0** 在(进位)列。

    ![](img/b47f2e32081aa7d58f0b8e297189dd93.png)

    *   **Step-3:** Simplify the Boolean function for each output.
    In this step, we have to just create a simplified Boolean function according to inputs and outputs of the truth table obtained in the previous step.
    For Sum,

    ```
    Sum = A'B + AB' = A XOR B 
    ```

    对于进位，

    ```
    Carry = AB = A AND B 
    ```

    *   **Step-4:** Constructing circuit using Boolean function obtained from third step.
    For sum, we have obtained (A XOR B) so we will connect A and B to the inputs of XOR gate and take its output as a sum. For carry, we have obtained (A AND B) so we will connect A and B to the inputs of AND gate and take its output as a carry.

    ![](img/9c7ac697b3c2955f31cd3c804840df21.png)

    现在在这个电路中，如果你在 A 端和 B 端提供输入。根据我们在上面创建的真值表，您将获得求和和进位输出。这里我们已经完成了创建组合电路的四个步骤。

    因此，我们创建了一个名为**半加法器**的组合电路。你可以用同样的步骤来创建任何其他的组合电路。