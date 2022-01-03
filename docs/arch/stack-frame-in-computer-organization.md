# 计算机组织中的堆栈框架

> 原文:[https://www . geesforgeks . org/stack-frame-in-computer-organization/](https://www.geeksforgeeks.org/stack-frame-in-computer-organization/)

[**堆栈**](https://www.geeksforgeeks.org/stack-data-structure/) **框架:**
堆栈是应用程序内存的一部分，用于存储函数的局部变量、函数调用。每当在我们的程序中有一个函数调用时，对局部变量和其他函数调用或子程序的内存就存储在堆栈框架中。每个函数都在应用程序内存的堆栈段中获得自己的堆栈帧。

**特征:**

*   堆栈中为函数调用分配的内存只存在于函数执行时，一旦函数完成，我们就不能访问该函数的变量。
*   一旦调用函数完成了它的执行，它的堆栈帧就被移除，被调用函数的执行线程从它被留下的位置重新开始。
*   堆栈用于存储函数调用，因此当我们在程序中使用大量递归调用时，堆栈内存会被函数调用或子程序耗尽，这可能会导致堆栈溢出，因为堆栈内存有限。
*   每个堆栈帧维护堆栈指针和帧指针。堆栈指针和帧指针总是指向堆栈的顶部。它还维护一个指向要执行的下一条指令的程序计数器。
*   每当进行函数调用时，都会在堆栈段中创建一个堆栈帧，调用函数给出的参数会在被调用函数的堆栈帧中获得一些内存，并被推入被调用函数的堆栈帧中。当它们的执行完成时，它们会从堆栈框架中弹出。执行线程在被调用的函数中继续。

**栈帧结构:**
栈指针始终指向顶部，帧指针存储子程序整个栈帧的地址。子例程或函数的每个堆栈帧包含如下内容。

<figure class="table">

| 堆栈框架 |
| --- |
| 其他函数调用 |
| 其他保存的寄存器 |
| 局部变量 |
| 被调用函数的已保存[帧指针]
 |
| 已保存被调用函数的[链接寄存器]
 |
| 传递的参数 |
| 帧指针 |

子程序的典型堆栈帧。

**c++中的实现:**
让我们考虑一个示例程序，以便更好地理解堆栈框架。

## C++

```
#include <iostream>
using namespace std;

//product method
int findProduct(int a, int b)
{
    int product = a * b;
    return product;
}

//findSum method
int findSum(int a, int b)
{
    int sum = a + b;
    return sum;
}

//main function
int main()
{
    int a = 6;
    int b = 6;

    //findProduct method called
    int product = findProduct(a, b);

    //findSum method called
    int sum = findSum(a, b);
    cout << "Product is :" << product << endl;
    cout << "Sum is :" << sum << endl;

    return 0;
}
```

**输出:**

```
Product is :36
Sum is :12
```

**使用堆栈的解释:**

**步骤-1 :**
当 main()调用 findProduct 函数时，会创建一个新的堆栈帧，如下所示。

<figure class="table">

| findProduct()a = 6
b=6产品= a* b |
|   |
|   |
| main()
a = 6
b = 6
product =调用 findProduct()
sum =调用 findSum() |

**堆叠**

**步骤 2 :**
函数 findProduct 完成指令并返回 main()后，findProduct 的堆栈帧从堆栈中弹出。之后 main()调用 findSum()函数。

<figure class="table">

| findSum()
a = 6
b = 6
sum = a+b |
|   |
|   |
| main()a = 6
b=6
积= 36
和=调用 findSum() |

**堆叠**

**步骤 3 :**
函数 findSum 完成指令并返回 main()后，findSum()从堆栈中弹出，如下所示。

<figure class="table">

| main()
a = 6
b=6
积= 36
和= 12 |

**堆叠**

**步骤-4 :**
现在 main()函数执行剩余的语句并从堆栈中弹出，堆栈变空..

</figure>

</figure>

</figure>

</figure>