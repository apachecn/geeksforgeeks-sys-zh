# 使用循环调度计算服务器负载

> 原文:[https://www . geesforgeks . org/compute-server-loads-使用循环调度/](https://www.geeksforgeeks.org/calculate-server-loads-using-round-robin-scheduling/)

给定处理具有无限计算能力的多个请求的 **M 个服务器**和大小为 **N** 的数组 **arrivalTime[]** 和 **processTime[]** ，表示 **N 个请求的到达时间和加载时间**，方式如下:

*   每台服务器从 **0** 到**(M–1)**编号，请求严格按照时间递增顺序给出。
*   每个请求 **i** 以下列方式分配给其中一个服务器:
    *   选择第 **(i % m)** <sup>台</sup>服务器。如果所选服务器空闲，请将请求分配给该服务器。
    *   否则，选择下一个可用的服务器。如果没有可用的服务器，则请求被丢弃。

考虑到每台服务器一次只能处理一个请求，任务是在处理完所有传入请求后，找出每台服务器上的负载，假设每台服务器上的负载是它处理的请求数。

**示例:**

> **输入** : N = 4，M = 3，arrivalTime[] = {1，3，6，8}，processTime[] = {1，2，2，1}
> **输出**:
> 1<sup>ST</sup>Server->2
> 2<sup>nd</sup>Server->1
> 3<sup>rd</sup>Server->1
> **说明:**
> 第二个请求分配给第二个服务器，第三个请求分配给第三个服务器。
> 下面是过渡表:
> 
> <figure class="table">
> 
> | 请求编号 | 到达时间 | 装入时间 | 结束时间 | 可用服务器 | 要求的服务器 | 分配的服务器 |
> | Zero | one | one | Two | 0, 1, 2 | Zero | Zero |
> | one | three | Two | five | 0, 1, 2 | one | one |
> | Two | six | Two | eight | 0, 1, 2 | Two | Two |
> | three | eight | one | nine | 0, 1, 2 | one | one |
> 
> **输入** : N = 4，M = 2，arrivalTime = {1，2，4，6}，processTime = {7，1，4，4}
> **输出** :
> 第一台服务器- > 1
> 第二台服务器- > 2
> **说明:**
> 第一个请求分配给第一台服务器，第二个请求分配给第二台服务器。
> 第三个请求被分配给第二个服务器。第三个请求的被请求服务器是第一个服务器，但是由于在请求到达时它正忙，
> 因此，第二个服务器被分配给它。
> 第四个请求被丢弃，因为到达时两台服务器都很忙。
> 下面是过渡表:
> 
> <figure class="table">
> 
> | 请求编号 | 到达时间 | 装入时间 | 结束时间 | 可用服务器 | 要求的服务器 | 分配的服务器 |
> | Zero | one | seven | eight | 0, 1 | Zero | Zero |
> | one | Two | one | three | one | one | one |
> | Two | four | four | eight | one | Zero | one |
> | three | six | four | Ten | – | one | – |
> 
> </figure>
> 
> </figure>

**方式:**思路是使用[最小优先级队列](https://www.geeksforgeeks.org/implement-min-heap-using-stl/)和[集合](https://www.geeksforgeeks.org/set-in-cpp-stl/)。[优先级队列](https://www.geeksforgeeks.org/priority-queue-set-1-introduction/)记录繁忙的服务器，并在它们空闲时帮助释放它们。 [Set](https://www.geeksforgeeks.org/set-in-java/) 用于维护可用服务器的数据，将其分配给传入的请求。以下是步骤:

*   初始化一个辅助数组 **loadOnServer[]** ，它将存储每个服务器上的负载。
*   通过在每个请求处添加**到达时间**和**处理时间**，迭代传入的请求并找到每个请求的结束时间。
*   从结束时间超过当前结束时间的**优先级队列**中弹出忙碌的服务器。
*   如果可用服务器集为空，则放弃当前请求。
*   现在，使用[下界函数](https://www.geeksforgeeks.org/set-lower_bound-function-in-c-stl/)在集合中搜索 **(i % m) <sup>第</sup>个**服务器，如果下界迭代器指向集合的末尾，则选择集合中的第一个服务器。
*   在上述步骤之后，增加所选服务器上的负载计数器。
*   完成上述步骤后，在 **loadOnServer[]** 中打印所有负载的存储。

下面是上述方法的实现:

## C++

```
// C++ Program for the above approach
#include <bits/stdc++.h>
using namespace std;

// Function to print load on each server
void printLoadOnEachServer(
    int m, int loadOnServer[])
{
    // Traverse the loadOnServer and
    // print each loads
    for (int i = 0; i < m; i++) {

        cout << i + 1 << "st Server -> "
             << loadOnServer[i] << ".\n";
    }
}

// Function for finding the load
// on each server
void loadBalancing(int n, int m,
                   int arrivalTime[],
                   int processTime[])
{
    // Stores the load on each Server
    int loadOnServer[m];

    for (int i = 0; i < m; i++) {

        // Initialize load on each
        // server as zero
        loadOnServer[i] = 0;
    }

    // Minimum priority queue for
    // storing busy servers according
    // to their release time
    priority_queue<pair<int, int>,
                   vector<pair<int, int> >,
                   greater<pair<int, int> > >
        busyServers;

    // Set to store available Servers
    set<int> availableServers;

    for (int i = 0; i < m; i++) {

        // Initially, all servers are free
        availableServers.insert(i);
    }

    // Iterating through the requests.
    for (int i = 0; i < n; i++) {

        // End time of current request
        // is the sum of arrival time
        // and process time
        int endTime = arrivalTime[i]
                      + processTime[i];

        // Releasing all the servers which
        // have become free by this time
        while (!busyServers.empty()
               && busyServers.top().first
                      <= arrivalTime[i]) {

            // Pop the server
            pair<int, int> releasedServer
                = busyServers.top();
            busyServers.pop();

            // Insert available server
            availableServers.insert(
                releasedServer.second);
        }

        // If there is no free server,
        // the request is dropped
        if ((int)availableServers.empty()) {
            continue;
        }

        int demandedServer = i % m;

        // Searching for demanded server
        auto itr
            = availableServers.lower_bound(
                demandedServer);

        if (itr == availableServers.end()) {

            // If demanded Server is not free
            // and no server is free after it,
            // then choose first free server
            itr = availableServers.begin();
        }

        int assignedServer = *itr;

        // Increasing load on assigned Server
        loadOnServer[assignedServer]++;

        // Removing assigned server from list
        // of assigned servers
        availableServers.erase(assignedServer);

        // Add assigned server in the list of
        // busy servers with its release time
        busyServers.push({ endTime,
                           assignedServer });
    }

    // Function to print load on each server
    printLoadOnEachServer(m, loadOnServer);
}

// Driver Code
int main()
{
    // Given arrivalTime and processTime
    int arrivalTime[] = { 1, 2, 4, 6 };
    int processTime[] = { 7, 1, 4, 4 };

    int N = sizeof(arrivalTime)
            / sizeof(int);

    int M = 2;

    // Function Call
    loadBalancing(N, M, arrivalTime,
                  processTime);

    return 0;
}
```

**Output:** 

```
1st Server -> 1.
2st Server -> 2.
```

***时间复杂度:** O(N*log M)*
***辅助空间:** O(M)*