# LRU 页面错误|实施

> 原文:[https://www . geesforgeks . org/page-faults-in-LRU-implementation/](https://www.geeksforgeeks.org/page-faults-in-lru-implementation/)

LRU 将分页的概念用于内存管理，当新页面进入时，需要一个页面替换算法来决定需要替换哪个页面。每当引用一个新页面并且该页面不在内存中时，就会发生页面错误，并且操作系统会用一个新需要的页面替换一个现有页面。LRU 就是这样一种页面替换策略，其中替换最近最少使用的页面。

**例如:**
给定长度为 N、内存容量为 C 的页面数组[]中的页面序列，使用[最近最少使用(LRU)算法](https://www.geeksforgeeks.org/program-for-least-recently-used-lru-page-replacement-algorithm/)找出页面错误的数量。

**示例-1 :**

```
Input : N = 7, C = 3
pages = {1, 2, 1, 4, 2, 3, 5}
Output : 5
```

**说明:**

```
Capacity is 3, thus, we can store maximum 3 pages at a time.
Page 1 is required, since it is not present, 
it is a page fault: page fault = 1

Page 2 is required, since it is not present, 
it is a page fault: page fault = 1 + 1 = 2

Page 1 is required, since it is present, 
it is not a page fault: page fault = 2 + 0 = 2

Page 4 is required, since it is not present, 
it is a page fault: page fault = 2 + 1 = 3

Page 2 is required, since it is present, 
it is not a page fault: page fault = 3 + 0 = 3

Page 3 is required, since it is not present, 
it replaces LRU page 2: page fault = 3 + 1 = 4

Page 5 is required, since it is not present, 
it replaces LRU page 1: page fault = 4 + 1 = 5
```

**示例-2 :**

```
Input : N = 9, C = 4
Pages = {5, 0, 1, 3, 2, 4, 1, 0, 5}
Output : 8
```

**说明:**

```
Capacity is 4, thus, we can store maximum 4 pages at a time.
Page 5 is required, since it is not present, 
it is a page fault: page fault = 1

Page 0 is required, since it is not present, 
it is a page fault: page fault = 1 + 1 = 2

Page 1 is required, since it is not present, 
it is a page fault: page fault = 2 + 1 = 3

Page 3 is required, since it is not present, 
it is a page fault: page fault = 3 + 1 = 4

Page 2 is required, since it is not present, 
it replaces LRU page 5: page fault = 4 + 1 = 5

Page 4 is required, since it is not present, 
it replaces LRU page 0: page fault = 5 + 1 = 6

Page 1 is required, since it is present, 
it is not a page fault: page fault = 6 + 0 = 6

Page 0 is required, since it is not present, 
it replaces LRU page 3: page fault = 6 + 1 = 7

Page 5 is required, since it is not present, 
it replaces LRU page 2: page fault = 7 + 1 = 8
```

### **算法:**

```
step-1 : Initialize count as 0.
step-2 : Create a vector / array of size equal to memory capacity.
step-3 : Traverse elements of pages[]
step-4 : In each traversal:
        if(element is present in memory):
            remove the element and push the element at the end  
        else:
            if(memory is full) remove the first element
            Increment count 
            push the element at the end       
```

#### **算法实现:**

下面是算法在 C++中的实现，如下所示。

## C++

```
// C++ program to illustrate
// page faults in LRU

#include <bits/stdc++.h>
using namespace std;

/* Counts no. of page faults */
int pageFaults(int n, int c, int pages[])
{
    // Initialise count to 0
    int count = 0;

    // To store elements in memory of size c
    vector<int> v;
    int i;
    for (i = 0; i <= n - 1; i++) {

        // Find if element is present in memory or not
        auto it = find(v.begin(), v.end(), pages[i]);

        // If element is not present
        if (it == v.end()) {

            // If memory is full
            if (v.size() == c) {

                // Remove the first element
                // As it is least recently used
                v.erase(v.begin());
            }

            // Add the recent element into memory
            v.push_back(pages[i]);

            // Increment the count
            count++;
        }
        else {

            // If element is present
            // Remove the element
            // And add it at the end as it is
            // the most recent element
            v.erase(it);
            v.push_back(pages[i]);
        }
    }

    // Return total page faults
    return count;
}

/* Driver program to test pageFaults function*/
int main()
{

    int pages[] = { 1, 2, 1, 4, 2, 3, 5 };
    int n = 7, c = 3;

    cout << "Page Faults = " << pageFaults(n, c, pages);
    return 0;
}

// This code is contributed by rajsanghavi9.
```

**输出:**

```
Page Faults = 5
```

**时间复杂度:** O(N*C)

**辅助空间:** O(C)