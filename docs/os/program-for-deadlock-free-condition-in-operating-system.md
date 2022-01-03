# 操作系统中无死锁条件的程序

> 原文:[https://www . geesforgeks . org/program-for-free-deadlock-in-condition-in-operating-system/](https://www.geeksforgeeks.org/program-for-deadlock-free-condition-in-operating-system/)

给定:一个系统有 R 个相同的资源，P 个进程竞争它们，N 是每个进程的最大需求。任务是找到所需的最小资源数量，这样就不会出现死锁。

**公式:**

```
R >= P * (N - 1) + 1 
```

**示例:**

```
Input : P = 3, N = 4
Output : R >= 10

Input : P = 7, N = 2
Output : R >= 8 
```

**进场:**

> 考虑，3 个流程 A、B、c
> 让，每个流程的需求为 4
> 因此，最大资源需求为 3 * 4 = 12 **即**，给每个流程 4 个资源。
> 并且，所需的最低资源为 3 *(4–1)+1 = 10。
> 也就是说，给每个流程 3 个资源，我们只剩下 1 个资源。
> 该 1 个资源将被给予进程 A、B 或 c 中的任何一个。
> 因此，在任何一个进程使用该资源后，它会留下资源，并且该资源将被任何其他进程使用，因此**死锁永远不会发生。**

## C++

```
// C++ implementation of above program.
#include <bits/stdc++.h>
using namespace std;

// function that calculates
// the minimum no. of resources
int Resources(int process, int need)
{
    int minResources = 0;

    // Condition so that deadlock
    // will not occur
    minResources = process * (need - 1) + 1;

    return minResources;
}

// Driver code
int main()
{
    int process = 3, need = 4;

    cout << "R >= " << Resources(process, need);
    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java implementation of above program

class GFG
{

// function that calculates
// the minimum no. of resources
static int Resources(int process, int need)
{
    int minResources = 0;

    // Condition so that deadlock
    // will not occur
    minResources = process * (need - 1) + 1;

    return minResources;
}

// Driver Code
public static void main(String args[])
{
    int process = 3, need = 4;

    System.out.print("R >= ");
    System.out.print(Resources(process, need));
}
}
```

## 蟒蛇 3

```
# Python 3 implementation of
# above program

# function that calculates
# the minimum no. of resources
def Resources(process, need):

    minResources = 0

    # Condition so that deadlock
    # will not occur
    minResources = process * (need - 1) + 1

    return minResources

# Driver Code
if __name__ == "__main__" :

    process, need = 3, 4

    print("R >=", Resources(process, need))

# This Code is Contributed
# by Naman_Garg
```

## C#

```
// C# implementation of above program
using System;

class GFG
{

// function that calculates
// the minimum no. of resources
static int Resources(int process, int need)
{
    int minResources = 0;

    // Condition so that deadlock
    // will not occur
    minResources = process * (need - 1) + 1;

    return minResources;
}

// Driver Code
public static void Main()
{
    int process = 3, need = 4;

    Console.Write("R >= ");
    Console.Write(Resources(process, need));
}
}

// This code is contributed
// by Sanjit_Prasad
```

**输出:**

```
R >= 10
```