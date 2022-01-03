# 内存管理中所有分区分配方法的实现

> 原文:[https://www . geesforgeks . org/内存管理中所有分区分配方法的实现/](https://www.geeksforgeeks.org/implementation-of-all-partition-allocation-methods-in-memory-management/)

**先决条件:** [内存管理中的分区分配方法](https://www.geeksforgeeks.org/partition-allocation-methods-in-memory-management/)
在[分区分配](https://www.geeksforgeeks.org/partition-allocation-methods-in-memory-management/)中，当有多个分区可自由容纳进程请求时，必须选择一个分区。要选择特定的分区，需要分区分配方法。如果分区分配方法避免了内部碎片，则认为它更好。

**考虑以下工艺数据:**

| 过程 | 进程大小 |
| one | Eighty-eight |
| Two | One hundred and ninety-two |
| three | Two hundred and seventy-seven |
| four | Three hundred and sixty-five |
| five | Four hundred and eighty-nine |

**Consider the following data for memory slots:**

内存块号内存块大小onefour hundredTwoFive hundredthreeThree hundredfourTwo hundredfive100

下面是各种分区分配方案及其相对于上面给定数据的实现。

<u>**1。第一批**</u>

该方法保持按内存位置组织的任务忙/闲列表，从低序到高阶内存。在这种方法中，第一个作业要求第一个可用内存的空间大于或等于其大小。操作系统不会搜索合适的分区，而只是将作业分配到最近的、有足够大小的内存分区。

以下是[首次拟合算法](https://www.geeksforgeeks.org/first-fit-allocation-in-operating-systems/)的实现:

```
// C++ program for the implementation
// of the First Fit algorithm
#include <iostream>
#include <queue>
#include <vector>
using namespace std;

// Process Class
class process {
public:
    // Size & number of process
    size_t size;
    pid_t no;
};

// Memory Class
class memory {
public:
    size_t size;

    // Number of memory & queue of space
    // occupied by process
    pid_t no;
    queue<process> space_occupied;

    // Function to push process in a block
    void push(const process p)
    {
        if (p.size <= size) {
            space_occupied.push(p);
            size -= p.size;
        }
    }

    // Function to pop and return the
    // process from the block
    process pop()
    {
        process p;

        // If space occupied is empty
        if (!space_occupied.empty()) {
            p = space_occupied.front();
            space_occupied.pop();
            size += p.size;
            return p;
        }
    }

    // Function to check if block is
    // completely empty
    bool empty()
    {
        return space_occupied.empty();
    }
};

// Function to get data of processess
// allocated using first fit
vector<memory> first_fit(vector<memory> memory_blocks,
                         queue<process> processess)
{
    int i = 0;
    bool done, done1;
    memory na;
    na.no = -10;
    while (!processess.empty()) {
        done = 0;
        for (i = 0; i < memory_blocks.size(); i++) {
            done1 = 0;
            if (memory_blocks.at(i).size
                >= processess.front().size) {
                memory_blocks.at(i).push(processess.front());
                done = 1;
                done1 = 1;
                break;
            }
        }

        // If process is done
        if (done == 0 && done1 == 0) {
            na.size += processess.front().size;
            na.push(processess.front());
        }

        // pop the process
        processess.pop();
    }
    if (!na.space_occupied.empty())
        memory_blocks.push_back(na);
    return memory_blocks;
}

// Function to display the allocation
// of all processess
void display(vector<memory> memory_blocks)
{
    int i = 0, temp = 0;
    process p;
    cout << "+-------------+--------------+--------------+"
         << endl;
    cout << "| Process no. | Process size | Memory block |"
         << endl;
    cout << "+-------------+--------------+--------------+"
         << endl;

    // Traverse memory blocks size
    for (i = 0; i < memory_blocks.size(); i++) {

        // While memory block size is not empty
        while (!memory_blocks.at(i).empty()) {
            p = memory_blocks.at(i).pop();
            temp = to_string(p.no).length();
            cout << "|" << string(7 - temp / 2 - temp % 2, ' ')
                 << p.no << string(6 - temp / 2, ' ')
                 << "|";

            temp = to_string(p.size).length();
            cout << string(7 - temp / 2 - temp % 2, ' ')
                 << p.size
                 << string(7 - temp / 2, ' ') << "|";

            temp = to_string(memory_blocks.at(i).no).length();
            cout << string(7 - temp / 2 - temp % 2, ' ');

            // If memory blocks is assigned
            if (memory_blocks.at(i).no != -10) {
                cout << memory_blocks.at(i).no;
            }

            // Else memory blocks is assigned
            else {
                cout << "N/A";
            }
            cout << string(7 - temp / 2, ' ')
                 << "|" << endl;
        }
    }
    cout << "+-------------+--------------+--------------+"
         << endl;
}

// Driver Code
int main()
{
    // Declare memory blocks
    vector<memory> memory_blocks(5);

    // Declare first fit blocks
    vector<memory> first_fit_blocks;

    // Declare queue of all processess
    queue<process> processess;
    process temp;

    // Set sample data
    memory_blocks[0].no = 1;
    memory_blocks[0].size = 400;

    memory_blocks[1].no = 2;
    memory_blocks[1].size = 500;

    memory_blocks[2].no = 3;
    memory_blocks[2].size = 300;

    memory_blocks[3].no = 4;
    memory_blocks[3].size = 200;

    memory_blocks[4].no = 5;
    memory_blocks[4].size = 100;

    temp.no = 1;
    temp.size = 88;

    // Push the process
    processess.push(temp);

    temp.no = 2;
    temp.size = 192;

    // Push the process
    processess.push(temp);

    temp.no = 3;
    temp.size = 277;

    // Push the process
    processess.push(temp);

    temp.no = 4;
    temp.size = 365;

    // Push the process
    processess.push(temp);

    temp.no = 5;
    temp.size = 489;

    // Push the process
    processess.push(temp);

    // Get the data
    first_fit_blocks = first_fit(memory_blocks, processess);

    // Display the data
    display(first_fit_blocks);
    memory_blocks.clear();
    memory_blocks.shrink_to_fit();
    first_fit_blocks.clear();
    first_fit_blocks.shrink_to_fit();
    return 0;
}
```

**Output:**

```
+-------------+--------------+--------------+
| Process no. | Process size | Memory block |
+-------------+--------------+--------------+
|      1      |      88      |      1       |
|      2      |     192      |      1       |
|      3      |     277      |      2       |
|      4      |     365      |     N/A      |
|      5      |     489      |     N/A      |
+-------------+--------------+--------------+

```

<u>**2。下一个飞度**</u>

下一个版本是“第一个版本”的修改版本。它从第一个适合找到空闲分区开始，但下次调用时，它会从停止的地方开始搜索，而不是从开始。这个策略使用了一个流动指针。指针沿着内存链移动，以搜索下一个匹配。这有助于避免总是从自由区块链的头部(开始)使用内存。

下面是[下一个拟合算法](https://www.geeksforgeeks.org/program-for-next-fit-algorithm-in-memory-management/)的实现:

```
// C++ program for the implementation
// of the Next Fit algorithm
#include <iostream>
#include <queue>
#include <vector>
using namespace std;

// Process Class
class process {
public:
    // Size & number of process
    size_t size;
    pid_t no;
};

// Memory Class
class memory {
public:
    size_t size;

    // Number of memory & queue of space
    // occupied by process
    pid_t no;
    queue<process> space_occupied;

    // Function to push process in a block
    void push(const process p)
    {
        if (p.size <= size) {
            space_occupied.push(p);
            size -= p.size;
        }
    }

    // Function to pop and return the
    // process from the block
    process pop()
    {
        process p;

        // If space occupied is empty
        if (!space_occupied.empty()) {
            p = space_occupied.front();
            space_occupied.pop();
            size += p.size;
            return p;
        }
    }

    // Function to check if block is
    // completely empty
    bool empty()
    {
        return space_occupied.empty();
    }
};

// Function to get data of processess
// allocated using Next Fit
vector<memory> next_fit(vector<memory> memory_blocks,
                        queue<process> processess)
{
    int i = 0;
    bool done, done1;
    memory na;
    na.no = -10;

    // Loop till process is empty
    while (!processess.empty()) {
        done1 = 0;

        // Traverse memory_blocks
        for (i = 0; i < memory_blocks.size(); i++) {
            done = 0;

            // If process is not empty
            if (!processess.empty() && memory_blocks.at(i).size >= processess.front().size) {
                memory_blocks.at(i).push(processess.front());
                done = 1;
                done1 = 1;
                processess.pop();
            }
        }
        if (!processess.empty() && done == 0 && done1 == 0) {
            na.size += processess.front().size;
            na.push(processess.front());
            processess.pop();
        }
    }

    // If space is not occupied push
    // the memory_blocks na
    if (!na.space_occupied.empty()) {
        memory_blocks.push_back(na);
    }

    return memory_blocks;
}

// Function to display the allocation
// of all processess
void display(vector<memory> memory_blocks)
{
    int i = 0, temp = 0;
    process p;
    cout << "+-------------+--------------+--------------+"
         << endl;
    cout << "| Process no. | Process size | Memory block |"
         << endl;
    cout << "+-------------+--------------+--------------+"
         << endl;

    // Traverse memory blocks size
    for (i = 0; i < memory_blocks.size(); i++) {

        // While memory block size is not empty
        while (!memory_blocks.at(i).empty()) {
            p = memory_blocks.at(i).pop();
            temp = to_string(p.no).length();
            cout << "|" << string(7 - temp / 2 - temp % 2, ' ')
                 << p.no << string(6 - temp / 2, ' ')
                 << "|";

            temp = to_string(p.size).length();
            cout << string(7 - temp / 2 - temp % 2, ' ')
                 << p.size
                 << string(7 - temp / 2, ' ') << "|";

            temp = to_string(memory_blocks.at(i).no).length();
            cout << string(7 - temp / 2 - temp % 2, ' ');

            // If memory blocks is assigned
            if (memory_blocks.at(i).no != -10) {
                cout << memory_blocks.at(i).no;
            }

            // Else memory blocks is assigned
            else {
                cout << "N/A";
            }
            cout << string(7 - temp / 2, ' ')
                 << "|" << endl;
        }
    }
    cout << "+-------------+--------------+--------------+"
         << endl;
}

// Driver Code
int main()
{
    // Declare memory blocks
    vector<memory> memory_blocks(5);

    // Declare next fit blocks
    vector<memory> next_fit_blocks;

    // Declare queue of all processess
    queue<process> processess;
    process temp;

    // Set sample data
    memory_blocks[0].no = 1;
    memory_blocks[0].size = 400;

    memory_blocks[1].no = 2;
    memory_blocks[1].size = 500;

    memory_blocks[2].no = 3;
    memory_blocks[2].size = 300;

    memory_blocks[3].no = 4;
    memory_blocks[3].size = 200;

    memory_blocks[4].no = 5;
    memory_blocks[4].size = 100;

    temp.no = 1;
    temp.size = 88;

    // Push the process
    processess.push(temp);
    temp.no = 2;
    temp.size = 192;

    // Push the process
    processess.push(temp);
    temp.no = 3;
    temp.size = 277;

    // Push the process
    processess.push(temp);
    temp.no = 4;
    temp.size = 365;

    // Push the process
    processess.push(temp);
    temp.no = 5;
    temp.size = 489;

    // Push the process
    processess.push(temp);

    // Get the data
    next_fit_blocks = next_fit(memory_blocks,
                               processess);

    // Display the data
    display(next_fit_blocks);
    memory_blocks.clear();
    memory_blocks.shrink_to_fit();
    next_fit_blocks.clear();
    next_fit_blocks.shrink_to_fit();
    return 0;
}
```

**Output:**

```
+-------------+--------------+--------------+
| Process no. | Process size | Memory block |
+-------------+--------------+--------------+
|      1      |      88      |      1       |
|      2      |     192      |      2       |
|      3      |     277      |      3       |
|      4      |     365      |     N/A      |
|      5      |     489      |     N/A      |
+-------------+--------------+--------------+

```