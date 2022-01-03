# LFU 页面错误|实施

> 原文:[https://www . geesforgeks . org/page-faults-in-lfu-implementation/](https://www.geeksforgeeks.org/page-faults-in-lfu-implementation/)

**概述:**

在这种情况下，它使用分页的概念进行内存管理，需要一个页面替换算法来决定当新页面进来时需要替换哪个页面。每当引用一个新页面并且该页面不在内存中时，就会发生页面错误，并且操作系统会用一个新需要的页面替换一个现有页面。LFU 就是这样一个页面替换政策，最不常用的页面被替换。如果页面的频率相同，那么先到达的页面会先被替换。

**示例:**

给定长度为 N、内存容量为 C 的页面数组[]中的页面序列，使用最少使用(LFU)算法找出页面错误的数量。

**示例-1 :**

```
Input : N = 7, C = 3
pages = { 1, 2, 3, 4, 2, 1, 5 }
Output :
Page Faults = 6
Page Hits = 1
```

**说明:**

> 容量为 3，因此，我们一次最多可以存储 3 页。
> 
> 第 1 页是必需的，因为它不存在，
> 
> 这是页面错误:页面错误= 1
> 
> 第 2 页是必需的，因为它不存在，
> 
> 这是一个页面错误:页面错误= 1 + 1 = 2
> 
> 第 3 页是必需的，因为它不存在，
> 
> 这是一个页面错误:页面错误= 2 + 1 = 3
> 
> 第 4 页是必需的，因为它不存在，
> 
> 它取代了 LFU 第 1 页:页面错误= 3 + 1 = 4
> 
> 第 2 页是必需的，因为它存在，
> 
> 这不是页面错误:页面错误= 4 + 0 = 4
> 
> 第 1 页是必需的，因为它不存在，
> 
> 它取代了 LFU 第 3 页:页面错误= 4 + 1 = 5
> 
> 第 5 页是必需的，因为它不存在，
> 
> 它取代了 LFU 第 4 页:页面错误= 5 + 1 = 6

**示例-2 :**

```
Input : N = 9, C = 4
pages = { 5, 0, 1, 3, 2, 4, 1, 0, 5 }
Output :
Page Faults = 8
Page Hits = 1
```

**说明:**

> 容量为 4，因此，我们一次最多可以存储 4 页。
> 
> 第 5 页是必需的，因为它不存在，
> 
> 这是页面错误:页面错误= 1
> 
> 第 0 页是必需的，因为它不存在，
> 
> 这是一个页面错误:页面错误= 1 + 1 = 2
> 
> 第 1 页是必需的，因为它不存在，
> 
> 这是一个页面错误:页面错误= 2 + 1 = 3
> 
> 第 3 页是必需的，因为它不存在，
> 
> 这是一个页面错误:页面错误= 3 + 1 = 4
> 
> 第 2 页是必需的，因为它不存在，
> 
> 它取代了 LFU 第 5 页:页面错误= 4 + 1 = 5
> 
> 第 4 页是必需的，因为它不存在，
> 
> 它取代了 LFU 页面 0:页面错误= 5 + 1 = 6
> 
> 第 1 页是必需的，因为它存在，
> 
> 这不是页面错误:页面错误= 6 + 0 = 6
> 
> 第 0 页是必需的，因为它不存在，
> 
> 它取代了 LRU 第 3 页:页面错误= 6 + 1 = 7
> 
> 第 5 页是必需的，因为它不存在，
> 
> 它取代了 LFU 第 2 页:页面错误= 7 + 1 = 8

**算法:**

```
Step-1 : Initialize count as 0.
Step-2 : Create a vector / array of size equal to memory capacity.
            Create a map to store frequency of pages 
Step-3 : Traverse elements of pages[]
Step-4 : In each traversal:
       if(element is present in memory):
            remove the element and push the element at the end  
            increase its frequency
       else:
            if(memory is full) 
                 remove the first element and decrease frequency of 1st element
            Increment count  
            push the element at the end and increase its frequency
      Compare frequency with other pages starting from the 2nd last page                  
      Sort the pages based on their frequency and time at which they arrive
      if frequency is same, then, the page arriving first must be placed first       
```

下面是上述算法的实现。

## C++

```
// C++ program to illustrate
// page faults in LFU

#include <bits/stdc++.h>
using namespace std;

/* Counts no. of page faults */
int pageFaults(int n, int c, int pages[])
{
    // Initialise count to 0
    int count = 0;

    // To store elements in memory of size c
    vector<int> v;
    // To store frequency of pages
    unordered_map<int, int> mp;

    int i;
    for (i = 0; i <= n - 1; i++) {

        // Find if element is present in memory or not
        auto it = find(v.begin(), v.end(), pages[i]);

        // If element is not present
        if (it == v.end()) {

            // If memory is full
            if (v.size() == c) {

                // Decrease the frequency
                mp[v[0]]--;

                // Remove the first element as
                // It is least frequently used
                v.erase(v.begin());
            }

            // Add the element at the end of memory
            v.push_back(pages[i]);
            // Increase its frequency
            mp[pages[i]]++;

            // Increment the count
            count++;
        }
        else {

            // If element is present
            // Remove the element
            // And add it at the end
            // Increase its frequency
            mp[pages[i]]++;
            v.erase(it);
            v.push_back(pages[i]);
        }

        // Compare frequency with other pages
        // starting from the 2nd last page                 
        int k = v.size() - 2;

        // Sort the pages based on their frequency 
        // And time at which they arrive
        // if frequency is same
        // then, the page arriving first must be placed first
        while (mp[v[k]] > mp[v[k + 1]] && k > -1) {
            swap(v[k + 1], v[k]);
            k--;
        }
    }

    // Return total page faults
    return count;
}

/* Driver program to test pageFaults function*/
int main()
{

    int pages[] = { 1, 2, 3, 4, 2, 1, 5 };
    int n = 7, c = 3;

    cout << "Page Faults = " << pageFaults(n, c, pages)
         << endl;
    cout << "Page Hits = " << n - pageFaults(n, c, pages);
    return 0;
}

// This code is contributed by rajsanghavi9.
```

**Output**

```
Page Faults = 6
Page Hits = 1
```