# 代码优化中的频率降低

> 原文:[https://www . geesforgeks . org/降频降码优化/](https://www.geeksforgeeks.org/frequency-reduction-in-code-optimization/)

**先决条件–**[编译器设计|代码优化](https://www.geeksforgeeks.org/compiler-design-code-optimization/)
**降频**是[循环优化](https://www.geeksforgeeks.org/compiler-design-loop-optimization/)过程中的一种类型，与机器无关。在频率降低代码内的循环是优化的，以改善程序的运行时间。频率降低用于减少循环中的代码量。可以移到循环体之外而不影响程序语义的语句或表达式被移到循环之外。频率降低也称为代码运动。

**降频目标:**
降频目标为:

*   降低表达式的求值频率。
*   将循环不变语句带出循环。

下面是频率降低的例子:

**程序 1:**

```
// This program does not uses frequency reduction.
#include <bits/stdc++.h>

using namespace std;

int main()
{
    int a = 2, b = 3, c, i = 0;

    while (i < 5) {
        // c is calculated 5 times
        c = pow(a, b) + pow(b, a); 

        // print the value of c 5 times
        cout << c << endl; 
        i++;
    }
    return 0;
}
```

**程序 2:**

```
// This program uses frequency reduction.
#include <bits/stdc++.h>

using namespace std;

int main()
{
    int a = 2, b = 3, c, i = 0;

    // c is calculated outside the loop
    c = pow(a, b) + pow(b, a); 

    while (i < 5) {

        // print the value of c 5 times
        cout << c << endl; 
        i++;
    }
    return 0;
}
```

**输出:**

```
17
17
17
17
17
```

**解释:**
程序 2 比程序 1 更有效，因为在程序 1 中，每次执行 while 循环时都会计算 c 的值。因此，c 的值只在循环外计算一次，这减少了循环中的代码量。