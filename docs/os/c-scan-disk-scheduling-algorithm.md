# C-SCAN 磁盘调度算法

> 原文:[https://www . geesforgeks . org/c-scan-disk-scheduling-algorithm/](https://www.geeksforgeeks.org/c-scan-disk-scheduling-algorithm/)

**先决条件:** [磁盘调度算法](https://www.geeksforgeeks.org/disk-scheduling-algorithms/)和[扫描磁盘调度算法](https://www.geeksforgeeks.org/scan-elevator-disk-scheduling-algorithms/)

给定一组磁盘磁道号和初始磁头位置，如果使用 C-SCAN 磁盘调度算法，我们的任务是找到访问所有请求磁道的寻道操作总数。

### **C-SCAN(圆形电梯)磁盘调度算法**

循环扫描(C-SCAN)调度算法是扫描磁盘调度算法的改进版本，通过更一致地服务请求来解决扫描算法的低效问题。像扫描(电梯算法)一样，C-SCAN 将头从服务所有请求的一端移动到另一端。但是，一旦磁头到达另一端，它会立即返回磁盘的开头，而不会在返回行程中处理任何请求(见下图)，并在到达开头时再次开始处理。这也被称为“圆形升降舵算法”，因为它本质上将圆柱体视为从最终圆柱体到第一个圆柱体环绕的圆形列表。

#### **C-SCAN(圆形电梯)磁盘调度算法优势:**

*   适用于中等至重负载。
*   它提供了更好的响应时间和统一的等待时间。

#### **C-SCAN(圆形电梯)磁盘调度算法的缺点:**

*   对极端情况下的曲目服务请求可能不公平。
*   与扫描算法相比，它有更多的寻道运动。

### **算法:**

1.  Let Request 数组表示一个数组，该数组存储按到达时间升序请求的磁道索引。“head”是磁盘磁头的位置。
2.  磁头仅在从 0 到磁盘大小的正确方向上工作。
3.  向左移动时，不要维修任何履带。
4.  当我们到达起点(左端)时，反转方向。
5.  当它朝着正确的方向前进时，它会逐个服务所有轨道。
6.  当向正确的方向移动时，计算轨道到头部的绝对距离。
7.  用此距离增加总寻道计数。
8.  当前维修的履带位置现在成为新的头部位置。
9.  转到步骤 6，直到我们到达磁盘的右端。
10.  如果我们到达磁盘的右端，则反转方向并转到步骤 3，直到请求阵列中的所有磁道都没有得到服务。

**示例:**

```
Input:  
Request sequence = {176, 79, 34, 60, 92, 11, 41, 114}
Initial head position = 50
Direction = right(We are moving from left to right)

Output:
Initial position of head: 50
Total number of seek operations = 389
Seek Sequence is
60
79
92
114
176
199
0
11
34
41
```

下图显示了使用扫描为请求的磁道提供服务的顺序。

![](img/76a6a6f3d1f929fbff905f9d2d587994.png)

因此，总寻道计数计算如下:

```
= (60-50)+(79-60)+(92-79)
        +(114-92)+(176-114)+(199-176)+(199-0)
        +(11-0)+(34-11)+(41-34)
= 389
```

### **实施:**

C-SCAN 算法的实现如下。

**注:**
距离变量用于存储磁头与当前磁道位置之间的绝对距离。disk_size 是磁盘的大小。向量左和右分别在初始头部位置的左侧和右侧存储所有请求轨迹。

## C++

```
// C++ program to demonstrate
// C-SCAN Disk Scheduling algorithm
#include <bits/stdc++.h>
using namespace std;

// Code by Vikram Chaurasia

int size = 8;
int disk_size = 200;

void CSCAN(int arr[], int head)
{
    int seek_count = 0;
    int distance, cur_track;
    vector<int> left, right;
    vector<int> seek_sequence;

    // appending end values
    // which has to be visited
    // before reversing the direction
    left.push_back(0);
    right.push_back(disk_size - 1);

    // tracks on the left of the
    // head will be serviced when
    // once the head comes back
    // to the beginning (left end).
    for (int i = 0; i < size; i++) {
        if (arr[i] < head)
            left.push_back(arr[i]);
        if (arr[i] > head)
            right.push_back(arr[i]);
    }

    // sorting left and right vectors
    std::sort(left.begin(), left.end());
    std::sort(right.begin(), right.end());

    // first service the requests
    // on the right side of the
    // head.
    for (int i = 0; i < right.size(); i++) {
        cur_track = right[i];
        // appending current track to seek sequence
        seek_sequence.push_back(cur_track);

        // calculate absolute distance
        distance = abs(cur_track - head);

        // increase the total count
        seek_count += distance;

        // accessed track is now new head
        head = cur_track;
    }

    // once reached the right end
    // jump to the beginning.
    head = 0;

    // adding seek count for head returning from 199 to 0
    seek_count += (disk_size - 1);

    // Now service the requests again
    // which are left.
    for (int i = 0; i < left.size(); i++) {
        cur_track = left[i];

        // appending current track to seek sequence
        seek_sequence.push_back(cur_track);

        // calculate absolute distance
        distance = abs(cur_track - head);

        // increase the total count
        seek_count += distance;

        // accessed track is now the new head
        head = cur_track;
    }

    cout << "Total number of seek operations = "
         << seek_count << endl;

    cout << "Seek Sequence is" << endl;

    for (int i = 0; i < seek_sequence.size(); i++) {
        cout << seek_sequence[i] << endl;
    }
}

// Driver code
int main()
{

    // request array
    int arr[size] = { 176, 79, 34, 60, 92, 11, 41, 114 };
    int head = 50;

    cout << "Initial position of head: " << head << endl;
    CSCAN(arr, head);

    return 0;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// C-SCAN Disk Scheduling algorithm
import java.util.*;

class GFG {

    static int size = 8;
    static int disk_size = 200;

    public static void CSCAN(int arr[], int head)
    {
        int seek_count = 0;
        int distance, cur_track;

        Vector<Integer> left = new Vector<Integer>();
        Vector<Integer> right = new Vector<Integer>();
        Vector<Integer> seek_sequence
            = new Vector<Integer>();

        // Appending end values which has
        // to be visited before reversing
        // the direction
        left.add(0);
        right.add(disk_size - 1);

        // Tracks on the left of the
        // head will be serviced when
        // once the head comes back
        // to the beggining (left end).
        for (int i = 0; i < size; i++) {
            if (arr[i] < head)
                left.add(arr[i]);
            if (arr[i] > head)
                right.add(arr[i]);
        }

        // Sorting left and right vectors
        Collections.sort(left);
        Collections.sort(right);

        // First service the requests
        // on the right side of the
        // head.
        for (int i = 0; i < right.size(); i++) {
            cur_track = right.get(i);

            // Appending current track to seek sequence
            seek_sequence.add(cur_track);

            // Calculate absolute distance
            distance = Math.abs(cur_track - head);

            // Increase the total count
            seek_count += distance;

            // Accessed track is now new head
            head = cur_track;
        }

        // Once reached the right end
        // jump to the beggining.
        head = 0;

        // adding seek count for head returning from 199 to
        // 0
        seek_count += (disk_size - 1);

        // Now service the requests again
        // which are left.
        for (int i = 0; i < left.size(); i++) {
            cur_track = left.get(i);

            // Appending current track to
            // seek sequence
            seek_sequence.add(cur_track);

            // Calculate absolute distance
            distance = Math.abs(cur_track - head);

            // Increase the total count
            seek_count += distance;

            // Accessed track is now the new head
            head = cur_track;
        }

        System.out.println("Total number of seek "
                           + "operations = " + seek_count);

        System.out.println("Seek Sequence is");

        for (int i = 0; i < seek_sequence.size(); i++) {
            System.out.println(seek_sequence.get(i));
        }
    }

    // Driver code
    public static void main(String[] args) throws Exception
    {

        // Request array
        int arr[] = { 176, 79, 34, 60, 92, 11, 41, 114 };
        int head = 50;

        System.out.println("Initial position of head: "
                           + head);

        CSCAN(arr, head);
    }
}

// This code is contributed by divyesh072019
```

## 蟒蛇 3

```
# Python3 program to demonstrate
# C-SCAN Disk Scheduling algorithm
size = 8
disk_size = 200

def CSCAN(arr, head):

    seek_count = 0
    distance = 0
    cur_track = 0
    left = []
    right = []
    seek_sequence = []

    # Appending end values
    # which has to be visited
    # before reversing the direction
    left.append(0)
    right.append(disk_size - 1)

    # Tracks on the left of the
    # head will be serviced when
    # once the head comes back
    # to the beggining (left end).
    for i in range(size):
        if (arr[i] < head):
            left.append(arr[i])
        if (arr[i] > head):
            right.append(arr[i])

    # Sorting left and right vectors
    left.sort()
    right.sort()

    # First service the requests
    # on the right side of the
    # head.
    for i in range(len(right)):
        cur_track = right[i]

        # Appending current track
        # to seek sequence
        seek_sequence.append(cur_track)

        # Calculate absolute distance
        distance = abs(cur_track - head)

        # Increase the total count
        seek_count += distance

        # Accessed track is now new head
        head = cur_track

    # Once reached the right end
    # jump to the beggining.
    head = 0

    # adding seek count for head returning from 199 to 0
    seek_count += (disk_size - 1)

    # Now service the requests again
    # which are left.
    for i in range(len(left)):
        cur_track = left[i]

        # Appending current track
        # to seek sequence
        seek_sequence.append(cur_track)

        # Calculate absolute distance
        distance = abs(cur_track - head)

        # Increase the total count
        seek_count += distance

        # Accessed track is now the new head
        head = cur_track

    print("Total number of seek operations =",
          seek_count)
    print("Seek Sequence is")
    print(*seek_sequence, sep="\n")

# Driver code

# request array
arr = [176, 79, 34, 60,
       92, 11, 41, 114]
head = 50

print("Initial position of head:", head)

CSCAN(arr, head)

# This code is contributed by rag2127
```

## C#

```
// C# program to demonstrate
// C-SCAN Disk Scheduling algorithm
using System;
using System.Collections.Generic;

class GFG {

    static int size = 8;
    static int disk_size = 200;

    static void CSCAN(int[] arr, int head)
    {
        int seek_count = 0;
        int distance, cur_track;

        List<int> left = new List<int>();
        List<int> right = new List<int>();
        List<int> seek_sequence = new List<int>();

        // Appending end values which has
        // to be visited before reversing
        // the direction
        left.Add(0);
        right.Add(disk_size - 1);

        // Tracks on the left of the
        // head will be serviced when
        // once the head comes back
        // to the beggining (left end).
        for (int i = 0; i < size; i++) {
            if (arr[i] < head)
                left.Add(arr[i]);
            if (arr[i] > head)
                right.Add(arr[i]);
        }

        // Sorting left and right vectors
        left.Sort();
        right.Sort();

        // First service the requests
        // on the right side of the
        // head.
        for (int i = 0; i < right.Count; i++) {
            cur_track = right[i];

            // Appending current track to seek sequence
            seek_sequence.Add(cur_track);

            // Calculate absolute distance
            distance = Math.Abs(cur_track - head);

            // Increase the total count
            seek_count += distance;

            // Accessed track is now new head
            head = cur_track;
        }

        // Once reached the right end
        // jump to the beggining.
        head = 0;

        // adding seek count for head returning from 199 to
        // 0
        seek_count += (disk_size - 1);

        // Now service the requests again
        // which are left.
        for (int i = 0; i < left.Count; i++) {
            cur_track = left[i];

            // Appending current track to
            // seek sequence
            seek_sequence.Add(cur_track);

            // Calculate absolute distance
            distance = Math.Abs(cur_track - head);

            // Increase the total count
            seek_count += distance;

            // Accessed track is now the new head
            head = cur_track;
        }

        Console.WriteLine("Total number of seek "
                          + "operations = " + seek_count);

        Console.WriteLine("Seek Sequence is");

        for (int i = 0; i < seek_sequence.Count; i++) {
            Console.WriteLine(seek_sequence[i]);
        }
    }

    // Driver code
    static void Main()
    {

        // Request array
        int[] arr = { 176, 79, 34, 60, 92, 11, 41, 114 };
        int head = 50;

        Console.WriteLine("Initial position of head: "
                          + head);

        CSCAN(arr, head);
    }
}

// This code is contributed by divyeshrabadiya07
```

## java 描述语言

```
<script>
    // Javascript program to demonstrate
    // C-SCAN Disk Scheduling algorithm
    let size = 8;
    let disk_size = 200;

    function CSCAN(arr, head)
    {
        let seek_count = 0;
        let distance, cur_track;
        let left = [], right = [];
        let seek_sequence = [];

        // appending end values
        // which has to be visited
        // before reversing the direction
        left.push(0);
        right.push(disk_size - 1);

        // tracks on the left of the
        // head will be serviced when
        // once the head comes back
        // to the beggining (left end).
        for (let i = 0; i < size; i++) {
            if (arr[i] < head)
                left.push(arr[i]);
            if (arr[i] > head)
                right.push(arr[i]);
        }

        // sorting left and right vectors
        left.sort(function(a, b){return a - b});
        right.sort(function(a, b){return a - b});

        // first service the requests
        // on the right side of the
        // head.
        for (let i = 0; i < right.length; i++)
        {
            cur_track = right[i];

            // appending current track to seek sequence
            seek_sequence.push(cur_track);

            // calculate absolute distance
            distance = Math.abs(cur_track - head);

            // increase the total count
            seek_count += distance;

            // accessed track is now new head
            head = cur_track;
        }

        // once reached the right end
        // jump to the beggining.
        head = 0;

        // adding seek count for head returning from 199 to 0
        seek_count += (disk_size - 1);

        // Now service the requests again
        // which are left.
        for (let i = 0; i < left.length; i++) {
            cur_track = left[i];

            // appending current track to seek sequence
            seek_sequence.push(cur_track);

            // calculate absolute distance
            distance = Math.abs(cur_track - head);

            // increase the total count
            seek_count += distance;

            // accessed track is now the new head
            head = cur_track;
        }

        document.write("Total number of seek operations = " + seek_count + "</br>");
        document.write("Seek Sequence is" + "</br>");
        for (let i = 0; i < seek_sequence.length; i++)
        {
            document.write(seek_sequence[i] + "</br>");
        }
    }

    // request array
    let arr = [ 176, 79, 34, 60, 92, 11, 41, 114 ];
    let head = 50;

    document.write("Initial position of head: " + head + "</br>");
    CSCAN(arr, head);

    // This code is contributed by mukesh07.
</script>
```

**Output**

```
Initial position of head: 50
Total number of seek operations = 389
Seek Sequence is
60
79
92
114
176
199
0
11
34
41
```