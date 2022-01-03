# 彼得森互斥算法|集合 1(基本 C 实现)

> 原文:[https://www . geeksforgeeks . org/petersons-算法换互斥-set-1/](https://www.geeksforgeeks.org/petersons-algorithm-for-mutual-exclusion-set-1/)

**问题:**给定 2 个进程 I 和 j，你需要编写一个程序，在没有任何额外硬件支持的情况下，保证两者互斥。

**解决方案:**可以有多种方法来解决这个问题，但大多数都需要额外的硬件支持。最简单和最流行的方法是使用彼得森互斥算法。它是由彼得森在 1981 年开发的，尽管这个方向的最初工作是由西奥多鲁斯·约瑟夫·德克尔完成的，他在 1960 年提出了**德克尔的算法**，后来被彼得森完善，并被称为**彼得森算法**。

基本上，彼得森的算法通过仅使用共享内存来提供有保证的互斥。它在算法中使用了两种思想:

1.  愿意获得锁。
2.  转到获取锁定。

前提条件:[C 中多线程](https://www.geeksforgeeks.org/multithreading-c-2/)

#### 解释:

其思想是，首先一个线程表达其获取锁的愿望，并设置**标志【self】= 1**，然后给另一个线程一个获取锁的机会。如果线程想要获得锁，那么它就获得锁，并将机会传递给第一个线程。如果它不想得到锁，那么 while 循环中断，第一个线程得到机会。

**C 语言实现**

## C

```
// Filename: peterson_spinlock.c
// Use below command to compile:
// gcc -pthread peterson_spinlock.c -o peterson_spinlock

#include <stdio.h>
#include <pthread.h>
#include"mythreads.h"

int flag[2];
int turn;
const int MAX = 1e9;
int ans = 0;

void lock_init()
{
    // Initialize lock by reseting the desire of
    // both the threads to acquire the locks.
    // And, giving turn to one of them.
    flag[0] = flag[1] = 0;
    turn = 0;
}

// Executed before entering critical section
void lock(int self)
{
    // Set flag[self] = 1 saying you want to acquire lock
    flag[self] = 1;

    // But, first give the other thread the chance to
    // acquire lock
    turn = 1-self;

    // Wait until the other thread looses the desire
    // to acquire lock or it is your turn to get the lock.
    while (flag[1-self]==1 && turn==1-self) ;
}

// Executed after leaving critical section
void unlock(int self)
{
    // You do not desire to acquire lock in future.
    // This will allow the other thread to acquire
    // the lock.
    flag[self] = 0;
}

// A Sample function run by two threads created
// in main()
void* func(void *s)
{
    int i = 0;
    int self = (int *)s;
    printf("Thread Entered: %d\n", self);

    lock(self);

    // Critical section (Only one thread
    // can enter here at a time)
    for (i=0; i<MAX; i++)
        ans++;

    unlock(self);
}

// Driver code
int main()
{
    // Initialized the lock then fork 2 threads
    pthread_t p1, p2;
    lock_init();

    // Create two threads (both run func)
    pthread_create(&p1, NULL, func, (void*)0);
    pthread_create(&p2, NULL, func, (void*)1);

    // Wait for the threads to end.
    pthread_join(p1, NULL);
    pthread_join(p2, NULL);

    printf("Actual Count: %d | Expected Count: %d\n",
                                        ans, MAX*2);

    return 0;
}
```

## C

```
// mythread.h (A wrapper header file with assert
// statements)
#ifndef __MYTHREADS_h__
#define __MYTHREADS_h__

#include <pthread.h>
#include <assert.h>
#include <sched.h>

void Pthread_mutex_lock(pthread_mutex_t *m)
{
    int rc = pthread_mutex_lock(m);
    assert(rc == 0);
}

void Pthread_mutex_unlock(pthread_mutex_t *m)
{
    int rc = pthread_mutex_unlock(m);
    assert(rc == 0);
}

void Pthread_create(pthread_t *thread, const pthread_attr_t *attr,    
           void *(*start_routine)(void*), void *arg)
{
    int rc = pthread_create(thread, attr, start_routine, arg);
    assert(rc == 0);
}

void Pthread_join(pthread_t thread, void **value_ptr)
{
    int rc = pthread_join(thread, value_ptr);
    assert(rc == 0);
}

#endif // __MYTHREADS_h__
```

**输出:**

```
Thread Entered: 1
Thread Entered: 0
Actual Count: 2000000000 | Expected Count: 2000000000

```

产生的输出是 2*10 <sup>9</sup> ，其中 10 <sup>9</sup> 由两个线程递增。

本文由**平克什·巴杰蒂亚**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。