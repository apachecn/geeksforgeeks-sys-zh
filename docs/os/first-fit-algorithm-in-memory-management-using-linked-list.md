# 使用链表的内存管理中的首次拟合算法

> 原文:[https://www . geesforgeks . org/first-fit-算法-内存管理-使用链表/](https://www.geeksforgeeks.org/first-fit-algorithm-in-memory-management-using-linked-list/)

**内存管理的第一个适合算法:**分配第一个足以容纳进程的内存分区。
在这篇[文章](https://www.geeksforgeeks.org/program-first-fit-algorithm-memory-management/?ref=rp)中，我们已经讨论了使用[数组](https://www.geeksforgeeks.org/introduction-to-arrays/)的首次拟合算法。然而，这里我们将研究另一种使用链表的方法，其中删除已分配的节点也是可能的。
**示例:**

```
Input: blockSize[] = {100, 500, 200}
        processSize[] = {417, 112, 426, 95} 
Output:
Block of size 426 can't be allocated
Tag    Block ID    Size
0         1        417
1         2        112
2         0        95
After deleting block with tag id 0.
Tag    Block ID    Size
1         2        112
2         0        95
3         1        426
```

![](img/95bf5b2d33712a78e257b389241d0d67.png)

**方法:**想法是使用具有唯一标签 id 的存储块。每个不同大小的进程都有块 id，这表示它们属于哪个内存块，还有唯一的标签 id 来删除特定的进程以释放空间。创建给定内存块大小的空闲列表和进程的分配列表。
**创建已分配列表:**
通过找到第一个具有足够大小的内存块来分配内存，从而创建给定进程大小的已分配列表。如果找不到内存块，只需打印出来。否则，创建一个节点并将其添加到分配的链表中。
**删除流程:**
每个流程都有唯一的标签 id。从分配的链表中删除进程节点，为其他进程释放一些空间。删除后，使用已删除节点的块 id 增加空闲列表中的内存块大小。
以下是实施办法:

C/C++

```
// C++ implementation of the First
// sit memory management algorithm
// using linked list

#include <bits/stdc++.h>
using namespace std;

// Two global counters
int g = 0, k = 0;

// Structure for free list
struct free {
    int tag;
    int size;
    struct free* next;
}* free_head = NULL, *prev_free = NULL;

// Structure for allocated list
struct alloc {
    int block_id;
    int tag;
    int size;
    struct alloc* next;
}* alloc_head = NULL, *prev_alloc = NULL;

// Function to create free
// list with given sizes
void create_free(int c)
{
    struct free* p = (struct free*)
        malloc(sizeof(struct free));
    p->size = c;
    p->tag = g;
    p->next = NULL;
    if (free_head == NULL)
        free_head = p;
    else
        prev_free->next = p;
    prev_free = p;
    g++;
}

// Function to print free list which
// prints free blocks of given sizes
void print_free()
{
    struct free* p = free_head;
    cout << "Tag\tSize\n";
    while (p != NULL) {
        cout << p->tag << "\t"
            << p->size << "\n";
        p = p->next;
    }
}

// Function to print allocated list which
// prints allocated blocks and their block ids
void print_alloc()
{
    struct alloc* p = alloc_head;
    cout << "Tag\tBlock ID\tSize\n";
    while (p != NULL) {
        cout << p->tag << "\t "
            << p->block_id << "\t\t"
            << p->size << "\n";
        p = p->next;
    }
}

// Function to allocate memory to
// blocks as per First fit algorithm
void create_alloc(int c)
{
    // create node for process of given size
    struct alloc* q = (struct alloc*)
        malloc(sizeof(struct alloc));
    q->size = c;
    q->tag = k;
    q->next = NULL;
    struct free* p = free_head;

    // Iterate to find first memory
    // block with appropriate size
    while (p != NULL) {
        if (q->size <= p->size)
            break;
        p = p->next;
    }

    // Node found to allocate
    if (p != NULL) {
        // Adding node to allocated list
        q->block_id = p->tag;
        p->size -= q->size;
        if (alloc_head == NULL)
            alloc_head = q;
        else {
            prev_alloc = alloc_head;
            while (prev_alloc->next != NULL)
                prev_alloc = prev_alloc->next;
            prev_alloc->next = q;
        }
        k++;
    }
    else // Node found to allocate space from
        cout << "Block of size " << c
            << " can't be allocated\n";
}

// Function to delete node from
// allocated list to free some space
void delete_alloc(int t)
{
    // Standard delete function
    // of a linked list node
    struct alloc *p = alloc_head, *q = NULL;

    // First, find the node according
    // to given tag id
    while (p != NULL) {
        if (p->tag == t)
            break;
        q = p;
        p = p->next;
    }
    if (p == NULL)
        cout << "Tag ID doesn't exist\n";
    else if (p == alloc_head)
        alloc_head = alloc_head->next;
    else
        q->next = p->next;
    struct free* temp = free_head;
    while (temp != NULL) {
        if (temp->tag == p->block_id) {
            temp->size += p->size;
            break;
        }
        temp = temp->next;
    }
}

// Driver Code
int main()
{
    int blockSize[] = { 100, 500, 200 };
    int processSize[] = { 417, 112, 426, 95 };
    int m = sizeof(blockSize)
            / sizeof(blockSize[0]);
    int n = sizeof(processSize)
            / sizeof(processSize[0]);

    for (int i = 0; i < m; i++)
        create_free(blockSize[i]);

    for (int i = 0; i < n; i++)
        create_alloc(processSize[i]);

    print_alloc();

    // Block of tag id 0 deleted
    // to free space for block of size 426
    delete_alloc(0);

    create_alloc(426);
    cout << "After deleting block"
        << " with tag id 0.\n";
    print_alloc();
}

```

## 蟒蛇 3

```
# Python3 implementation of the First
# sit memory management algorithm
# using linked list

# Two global counters
g = 0; k = 0

# Structure for free list
class free:
    def __init__(self):
        self.tag=-1
        self.size=0
        self.next=None
free_head = None; prev_free = None

# Structure for allocated list
class alloc:
    def __init__(self):
        self.block_id=-1
        self.tag=-1
        self.size=0
        self.next=None

alloc_head = None;prev_alloc = None

# Function to create free
# list with given sizes
def create_free(c):
    global g,prev_free,free_head
    p = free()
    p.size = c
    p.tag = g
    p.next = None
    if free_head is None:
        free_head = p
    else:
        prev_free.next = p
    prev_free = p
    g+=1

# Function to print free list which
# prints free blocks of given sizes
def print_free():
    p = free_head
    print("Tag\tSize")
    while (p != None) :
        print("{}\t{}".format(p.tag,p.size))
        p = p.next

# Function to print allocated list which
# prints allocated blocks and their block ids
def print_alloc():
    p = alloc_head
    print("Tag\tBlock ID\tSize")
    while (p is not None) :
        print("{}\t{}\t{}\t".format(p.tag,p.block_id,p.size))
        p = p.next

# Function to allocate memory to
# blocks as per First fit algorithm
def create_alloc(c):
    global k,alloc_head
    # create node for process of given size
    q = alloc()
    q.size = c
    q.tag = k
    q.next = None
    p = free_head

    # Iterate to find first memory
    # block with appropriate size
    while (p != None) :
        if (q.size <= p.size):
            break
        p = p.next

    # Node found to allocate
    if (p != None) :
        # Adding node to allocated list
        q.block_id = p.tag
        p.size -= q.size
        if (alloc_head == None):
            alloc_head = q
        else :
            prev_alloc = alloc_head
            while (prev_alloc.next != None):
                prev_alloc = prev_alloc.next
            prev_alloc.next = q

        k+=1

    else: # Node found to allocate space from
        print("Block of size {} can't be allocated".format(c))

# Function to delete node from
# allocated list to free some space
def delete_alloc(t):
    global alloc_head
    # Standard delete function
    # of a linked list node
    p = alloc_head; q = None

    # First, find the node according
    # to given tag id
    while (p != None) :
        if (p.tag == t):
            break
        q = p
        p = p.next

    if (p == None):
        print("Tag ID doesn't exist")
    elif (p == alloc_head):
        alloc_head = alloc_head.next
    else:
        q.next = p.next
    temp = free_head
    while (temp != None) :
        if (temp.tag == p.block_id) :
            temp.size += p.size
            break

        temp = temp.next

# Driver Code
if __name__ == '__main__':
    blockSize = [100, 500, 200]
    processSize = [417, 112, 426, 95]
    m = len(blockSize)
    n = len(processSize)

    for i in range(m):
        create_free(blockSize[i])

    for i in range(n):
        create_alloc(processSize[i])

    print_alloc()

    # Block of tag id 0 deleted
    # to free space for block of size 426
    delete_alloc(0)

    create_alloc(426)
    print("After deleting block with tag id 0.")
    print_alloc()
```

**Output:** 

```
Block of size 426 can't be allocated
Tag    Block ID    Size
0      1        417
1      2        112
2      0        95
After deleting block with tag id 0.
Tag    Block ID    Size
1      2        112
2      0        95
3      1        426
```