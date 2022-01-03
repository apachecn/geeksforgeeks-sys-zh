# 千里眼最短工作优先(SJF)

> 原文:[https://www . geesforgeks . org/千里眼-最短-工作-第一-sjf/](https://www.geeksforgeeks.org/clairvoyant-shortest-job-first-sjf/)

在这篇文章中，我们讨论了先知 SJF。这是一个理论概念，其中算法着眼于未来，等待最短的进程到达，这导致最小的平均等待时间。

**千里眼 SJF 与[最短作业优先](https://www.geeksforgeeks.org/program-for-shortest-job-first-or-sjf-cpu-scheduling-set-1-non-preemptive/) :**
两种算法的工作原理相同，都是将 CPU 时间分配给较短的进程。不同之处在于，千里眼可以展望未来，等待最短的进程，并相应地分配资源，而 SJF 必须将资源分配给已经到达的进程(即等待就绪队列)。
**示例:**

**输入:**流程为:

```
Process id    Arrival time    Burst time    
    p1            0             5        
    p2            1             2        
    p3            3             1        
    p4            4             3    
```

**输出:**根据千里眼 SJF 的进程调度是，

```
Process id    Arrival time    Burst time    
    p3           3              1        
    p2           1              2        
    p4           4              3        
    p1           0              5    
```

平均等待时间为:2.5
**输出:**按最短作业优先的流程调度为:

```
Process id    Arrival time    Burst time    
    p1           0              5        
    p3           3              1        
    p2           1              2        
    p4           4              3    
```

平均等待时间为:2.75

**注:**
千里眼 SJF 和 SJF 如果所有进程同时到达会给出同样的结果。

**输入:**流程为:

```
Process id      Arrival time    Burst time      
    p1               0               4
    p2               0               9
    p3               0               5
    p4               0               3    
```

**输出:**根据千里眼 SJF 的进程调度是，

```
Process id    Arrival time    Burst time    
    p4              0               3
    p1              0               4
    p3              0               5
    p2              0               9    
```

平均等待时间为:5.5
**输出:**按最短作业优先的流程调度为:

```
Process id    Arrival time    Burst time    
    p4              0               3
    p1              0               4
    p3              0               5
    p2              0               9    
```

**平均等待时间:5.5**

**代码:**

```
#include <bits/stdc++.h>
#define SIZE 4
using namespace std;

// Structure to store the information about the process
typedef struct proinfo {
    string pname; // Process name
    int atime; // Arrival time
    int btime; // Burst time
} proinfo;

// This function schedules the process 
// according to the Clairvoyant SJF scheduling algorithm.
void clairvoyantSjf(proinfo* arr)
{
    // To sort the processes according to the burst time
    int index = 0;
    for (int i = 0; i < SIZE - 1; i++) {
        index = i;
        for (int j = i + 1; j < SIZE; j++) {
            if (arr[j].btime < arr[index].btime) {

                index = j;
            }
        }
        swap(arr[i], arr[index]);
    }
}

void display(proinfo* arr)
{
    cout << endl;
    cout << "Process id"
         << "\t";
    cout << "Arrival time"
         << "\t";
    cout << "Burst time"
         << "\t";
    cout << endl;
    for (int i = 0; i < SIZE; i++) {
        cout << arr[i].pname << "\t\t";
        cout << arr[i].atime << "\t\t";
        cout << arr[i].btime << "\t\t";
        cout << endl;
    }
}

// To calculate the average waiting time
void avgWait(proinfo* arr)
{
    int ctime = 0;
    int twait = 0;
    for (int i = 0; i < SIZE; i++) {
        twait += abs(arr[i].atime - ctime);
        ctime += arr[i].btime;
    }
    cout << "The average waiting time is: " << (float)twait / SIZE << endl;
}

int main()
{
    // Array of process info structures.
    proinfo arr[SIZE];
    arr[0] = { "p1", 0, 5 };
    arr[1] = { "p2", 1, 2 };
    arr[2] = { "p3", 3, 1 };
    arr[3] = { "p4", 4, 3 };

    cout << "Process scheduling according to Clairvoyant SJF is: " << endl;

    clairvoyantSjf(arr);
    // To display the schedule
    display(arr);
    // to calculate the Average waiting time
    avgWait(arr);
}
```

**Output:**

```
Process scheduling according to Clairvoyant SJF is: 

Process id    Arrival time    Burst time    
p3        3        1        
p2        1        2        
p4        4        3        
p1        0        5        
The average waiting time is: 2.5

```