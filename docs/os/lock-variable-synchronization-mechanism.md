# 锁定变量同步机构

> 原文:[https://www . geesforgeks . org/lock-variable-synchronization-mechanism/](https://www.geeksforgeeks.org/lock-variable-synchronization-mechanism/)

**先决条件–**[进程同步](https://www.geeksforgeeks.org/process-synchronization-set-1/)
锁变量为进程提供了最简单的同步机制。关于锁定变量，值得注意的几点是-

1.  它是一个在用户模式下实现的**软件机制**，即不需要操作系统的支持。
2.  这是一个繁忙的等待解决方案(即使在技术上处于等待状态时，也能保持 CPU 繁忙)。
3.  它可以用于两个以上的过程。

当锁定= 0 时表示临界区是空的(初始值)，锁定= 1 时表示临界区被占用。
伪代码看起来像这样–

```
Entry section - while(lock != 0);
                Lock = 1;
//critical section
Exit section - Lock = 0;
```

在下面的代码片段中可以看到用于进程同步的锁定变量方法的更正式的方法:

## C

```
char buffer[SIZE];
int count = 0,
    start = 0,
    end = 0;
struct lock l;

// initialize lock variable
lock_init(&l);

void put(char c)
{

    // entry section
    lock_acquire(&l);

    // critical section begins
    while (count == SIZE) {

        lock_release(&l);
        lock_acquire(&l);
    }

    count++;
    buffer[start] = c;
    start++;

    if (start == SIZE) {

        start = 0;
    }

    // critical section ends
    // exit section
    lock_release(&l);
}

char get()
{

    char c;

    // entry section
    lock_acquire(&l);

    // critical section begins
    while (count == 0) {

        lock_release(&l);
        lock_acquire(&l);
    }

    count--;
    c = buffer[end];
    end++;

    if (end == SIZE) {

        end = 0;
    }

    // critical section ends
    // exit section
    lock_release(&l);

    return c;
}
```