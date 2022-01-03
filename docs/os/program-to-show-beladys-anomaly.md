# 显示贝拉蒂异常的程序

> 原文:[https://www . geesforgeks . org/program-to-show-Bela dys-exception/](https://www.geeksforgeeks.org/program-to-show-beladys-anomaly/)

先决条件–[贝拉蒂的异常](https://www.geeksforgeeks.org/beladys-anomaly-in-page-replacement-algorithms/)
贝拉蒂的异常是当页面错误的数量增加时，即使增加了帧数。
在本文中，我们使用 FIFO 页面替换算法演示了 Belady 的异常。
**例:**

```
Reference array is: 1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5 
Output :
When number of frames is 3, page fault : 9
When number of frames is 4, page fault : 10

Reference array is: 0, 1, 5, 3, 0, 1, 4, 0, 1, 5, 3, 4
Output :
When number of frames is 3, page fault : 9
When number of frames is 4, page fault : 10 
```

**实现:**
使用 FIFO 页面替换算法展示了 Belady 的异常。首先，使用一个大小等于帧数的数组，这个数组模拟页面帧，这个数组上的操作以循环数组的方式执行。计数变量用于计算页面错误，每当在页面框架数组中插入/重写元素时，该变量就会递增。
**在本代码中:**
分别测试了两种帧大小 3 和 4，随着帧数的增加，页面错误应该会减少，但是出现了异常，因为 3 帧导致 9 个页面错误，而 4 帧导致 10 个页面错误。这是贝拉蒂的异常，是在参考阵列和帧大小的特殊情况下观察到的。

## C++

```
#include <bits/stdc++.h>

using namespace std;

void pageFault(int frame_size, int* ref, int len)
{
    // To dynamically allocate an array,
    // it represents the page frames.
    int* arr = new int[frame_size];

    // To initialize the array
    for (int i = 0; i < frame_size; i++) {
        arr[i] = -1;
    }

    // To count page faults
    int cnt = 0;
    int start = 0;
    int flag;
    int elm;

    for (int i = 0; i < len; i++) {
        elm = ref[i];
        // Linear search to find if the page exists
        flag = 0;
        for (int j = 0; j < frame_size; j++) {
            if (elm == arr[j]) {
                flag = 1;
                break;
            }
        }
        // If the page doesn't exist it is inserted,
        // count is incremented
        if (flag == 0) {
            if (start < frame_size) {
                arr[start] = elm;
                start++;
            }
            else if (start == frame_size) {
                arr[0] = elm;
                start = 1;
            }
            cnt++;
        }
    }
    cout << "When the number of frames are: " << frame_size << ", ";
    cout << "the number of page faults is : " << cnt << endl;
}

int main()
{
    // Reference array
    int ref[] = { 1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5 };
    int len = sizeof(ref) / sizeof(ref[0]);
    // The frame size
    int frame_size = 3;

    pageFault(frame_size, ref, len);

    // Increase value of frame size
    frame_size = 4;

    // The page fault increases
    // even after increasing the
    // the number of frames.
    // This is Belady's Anomaly
    pageFault(frame_size, ref, len);
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Implementation of the above approach
class GFG
{
static void pageFault(int frame_size,
                      int []ref, int len)
{
    // To dynamically allocate an array,
    // it represents the page frames.
    int []arr = new int[frame_size];

    // To initialize the array
    for (int i = 0; i < frame_size; i++)
    {
        arr[i] = -1;
    }

    // To count page faults
    int cnt = 0;
    int start = 0;
    int flag;
    int elm;

    for (int i = 0; i < len; i++)
    {
        elm = ref[i];

        // Linear search to find
        // if the page exists
        flag = 0;
        for (int j = 0; j < frame_size; j++)
        {
            if (elm == arr[j])
            {
                flag = 1;
                break;
            }
        }

        // If the page doesn't exist it is inserted,
        // count is incremented
        if (flag == 0)
        {
            if (start < frame_size)
            {
                arr[start] = elm;
                start++;
            }
            else if (start == frame_size)
            {
                arr[0] = elm;
                start = 1;
            }
            cnt++;
        }
    }
    System.out.print("When the number of frames are: " +
                                     frame_size + ", ");
    System.out.println("the number of page faults is : " + cnt);
}

// Driver Code
public static void main (String[] args)
{
    // Reference array
    int ref[] = { 1, 2, 3, 4, 1, 2,
                  5, 1, 2, 3, 4, 5 };

    int len = ref.length;

    // The frame size
    int frame_size = 3;

    pageFault(frame_size, ref, len);

    // Increase value of frame size
    frame_size = 4;

    // The page fault increases
    // even after increasing the
    // the number of frames.
    // This is Belady's Anomaly
    pageFault(frame_size, ref, len);
}
}

// This code is contributed by AnkitRai01
```

## 蟒蛇 3

```
# Python3 Implementation of the above approach
def pageFault(frame_size, ref, len):

    # To dynamically allocate an array,
    # it represents the page frames.
    arr = [0] * frame_size;

    # To initialize the array
    for i in range(frame_size):
        arr[i] = -1;

    # To count page faults
    cnt = 0;
    start = 0;

    for i in range(len):
        elm = ref[i];

        # Linear search to find if the page exists
        flag = 0;
        for j in range(frame_size):
            if (elm == arr[j]):
                flag = 1;
                break;

        # If the page doesn't exist it is inserted,
        # count is incremented
        if (flag == 0):
            if (start < frame_size):
                arr[start] = elm;
                start += 1;
            elif (start == frame_size):
                arr[0] = elm;
                start = 1;
            cnt += 1;

    print("When the number of frames are: ",
                    frame_size, end = ", ");
    print("the number of page faults is : ", cnt);

# Driver Code

# Reference array
ref = [1, 2, 3, 4, 1, 2,
       5, 1, 2, 3, 4, 5 ];
len = len(ref);

# The frame size
frame_size = 3;

pageFault(frame_size, ref, len);

# Increase value of frame size
frame_size = 4;

# The page fault increases
# even after increasing the
# the number of frames.
# This is Belady's Anomaly
pageFault(frame_size, ref, len);

# This code is contributed by 29AjayKumar
```

## C#

```
// C# Implementation of the above approach
using System;

class GFG
{
static void pageFault(int frame_size,
                      int []refer, int len)
{
    // To dynamically allocate an array,
    // it represents the page frames.
    int []arr = new int[frame_size];

    // To initialize the array
    for (int i = 0; i < frame_size; i++)
    {
        arr[i] = -1;
    }

    // To count page faults
    int cnt = 0;
    int start = 0;
    int flag;
    int elm;

    for (int i = 0; i < len; i++)
    {
        elm = refer[i];

        // Linear search to find
        // if the page exists
        flag = 0;
        for (int j = 0; j < frame_size; j++)
        {
            if (elm == arr[j])
            {
                flag = 1;
                break;
            }
        }

        // If the page doesn't exist it is inserted,
        // count is incremented
        if (flag == 0)
        {
            if (start < frame_size)
            {
                arr[start] = elm;
                start++;
            }
            else if (start == frame_size)
            {
                arr[0] = elm;
                start = 1;
            }
            cnt++;
        }
    }
    Console.Write("When the number of frames are: " +
                                  frame_size + ", ");
    Console.WriteLine("the number of page " +
                       "faults is : " + cnt);
}

// Driver Code
public static void Main()
{
    // Reference array
    int []refer = { 1, 2, 3, 4, 1, 2,
                    5, 1, 2, 3, 4, 5 };

    int len = refer.Length;

    // The frame size
    int frame_size = 3;

    pageFault(frame_size, refer, len);

    // Increase value of frame size
    frame_size = 4;

    // The page fault increases
    // even after increasing the
    // the number of frames.
    // This is Belady's Anomaly
    pageFault(frame_size, refer, len);
}
}

// This code is contributed by kanugargng
```

## java 描述语言

```
<script>

    // JavaScript Implementation of the above approach

    function pageFault(frame_size, refer, len)
    {
        // To dynamically allocate an array,
        // it represents the page frames.
        let arr = new Array(frame_size);

        // To initialize the array
        for (let i = 0; i < frame_size; i++)
        {
            arr[i] = -1;
        }

        // To count page faults
        let cnt = 0;
        let start = 0;
        let flag;
        let elm;

        for (let i = 0; i < len; i++)
        {
            elm = refer[i];

            // Linear search to find
            // if the page exists
            flag = 0;
            for (let j = 0; j < frame_size; j++)
            {
                if (elm == arr[j])
                {
                    flag = 1;
                    break;
                }
            }

            // If the page doesn't exist it is inserted,
            // count is incremented
            if (flag == 0)
            {
                if (start < frame_size)
                {
                    arr[start] = elm;
                    start++;
                }
                else if (start == frame_size)
                {
                    arr[0] = elm;
                    start = 1;
                }
                cnt++;
            }
        }
        document.write("When the number of frames are: " +
                                      frame_size + ", ");
        document.write("the number of page " +
                           "faults is : " + cnt + "</br>");
    }

    // Reference array
    let refer = [ 1, 2, 3, 4, 1, 2, 5, 1, 2, 3, 4, 5 ];

    let len = refer.length;

    // The frame size
    let frame_size = 3;

    pageFault(frame_size, refer, len);

    // Increase value of frame size
    frame_size = 4;

    // The page fault increases
    // even after increasing the
    // the number of frames.
    // This is Belady's Anomaly
    pageFault(frame_size, refer, len);

</script>
```

**Output:** 

```
When the number of frames are: 3, the number of page faults is : 9
When the number of frames are: 4, the number of page faults is : 10
```