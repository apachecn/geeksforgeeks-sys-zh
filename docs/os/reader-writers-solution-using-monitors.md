# 使用监视器的读写器解决方案

> 原文:[https://www . geesforgeks . org/reader-writers-solution-use-monitors/](https://www.geeksforgeeks.org/reader-writers-solution-using-monitors/)

先决条件–[进程同步](https://www.geeksforgeeks.org/process-synchronization-set-1/)、[监视器](https://www.geeksforgeeks.org/monitors/)、[读者-作者问题](https://www.geeksforgeeks.org/readers-writers-problem-set-1-introduction-and-readers-preference-solution/)
考虑到共享数据库，我们的目标是:

*   只有当没有写入程序时，读者才能访问数据库。
*   只有当没有读取器或写入器时，写入器才能访问数据库。
*   一次只有一个线程可以操作状态变量。

**溶液的基本结构–**

```
Reader()
   Wait until no writers
   Access database
   Check out – wake up a waiting writer
Writer()
   Wait until no active readers or writers
   Access database
   Check out – wake up waiting readers or writer

```

–现在让我们假设一个作家很活跃，现在出现了读者和作家的混合体。
**下一个该谁上车？**
——或者假设一个作家在等待，源源不断的读者不断出现。
**他们活跃起来公平吗？**
那么我们来实现一种来回形式的公平:

***   Once a reader is waiting, the reader will enter next.*   If a writer is waiting, a writer will come in next.**

***使用监视器实施解决方案:-***

1.  这些方法应该以互斥的方式执行，即在每个时间点，最多一个线程可以执行它的任何方法。
2.  监视器还为线程提供了一种暂时放弃独占访问的机制，以便在重新获得独占访问并恢复其任务之前等待满足某些条件。
3.  监视器还有一种机制，用于向其他线程发出信号，告知这些条件已经满足。
4.  所以在这个实现中只有互斥是不够的。尝试操作的线程可能需要等待，直到某个断言 P 成立。
5.  当一个线程正在等待一个条件变量时，该线程不被认为占用了监视器，因此其他线程可能会进入监视器以改变监视器的状态。

**代码–**

```
// STATE VARIABLES
// Number of active readers; initially = 0
int NReaders = 0;

// Number of waiting readers; initially = 0
int WaitingReaders = 0;

// Number of active writers; initially = 0
int NWriters = 0;

// Number of waiting writers; initially = 0
int WaitingWriters = 0;

Condition canRead = NULL;
Condition canWrite = NULL;

Void BeginWrite()
{

    // A writer can enter if there are no other
    // active writers and no readers are waiting
    if (NWriters == 1 || NReaders > 0) {

        ++WaitingWriters;
        wait(CanWrite);
        --WaitingWriters;
    }

    NWriters = 1;
}

Void EndWrite()
{

    NWriters = 0;

    // Checks to see if any readers are waiting
    if (WaitingReaders)

        Signal(CanRead);

    else

        Signal(CanWrite);
}

Void BeginRead()
{

    // A reader can enter if there are no writers
    // active or waiting, so we can have
    // many readers active all at once
    if (NWriters == 1 || WaitingWriters > 0) {

        ++WaitingReaders;

        // Otherwise, a reader waits (maybe many do)
        Wait(CanRead);

        --WaitingReaders;
    }

    ++NReaders;
    Signal(CanRead);
}

Void EndRead()
{

    // When a reader finishes, if it was the last reader,
    // it lets a writer in (if any is there).
    if (--NReaders == 0)

        Signal(CanWrite);
}
```

***<u>解惑:-</u>***

*   **It wants to be fair.

    1.  如果一个作者在等待，读者就会排队。
    2.  如果一个读者(或另一个作者)正在活动或等待，作者会排队。
    3.  这基本上是公平的，尽管一旦它让一个读者进来，它就让所有等待的读者同时进来，即使有些读者“在”其他等待的作者之后出现。** *   ******The code is “simplified” because we know there can only be one writer at a time.*******   ******It also takes advantage of the fact that signal is a no-op if nobody is waiting.

    1.  在“结束写入”代码中(它发出可以写入的信号，而不检查等待的写入程序)
    2.  在 EndRead 代码中(同样的事情)
    3.  在开始读取(信号可以在最后读取)

    > 有了信号量，我们从来没有过这种“公平”的解决方案。事实上，这是可以做到的，但代码相当棘手。这里，简单的解决方案以期望的方式工作！显示器不容易出错，也更容易理解。******