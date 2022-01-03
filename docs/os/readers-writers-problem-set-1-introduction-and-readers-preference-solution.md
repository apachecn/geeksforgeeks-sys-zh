# 读者-作者问题|第 1 集(介绍和读者偏好解决方案)

> 原文:[https://www . geesforgeks . org/readers-writers-problem-set-1-introduction-and-readers-preference-solution/](https://www.geeksforgeeks.org/readers-writers-problem-set-1-introduction-and-readers-preference-solution/)

考虑一种情况，我们有一个文件在许多人之间共享。

*   If one of them tries to edit the file, no one else should read or write at the same time, or he/she will not see the changes.
*   However, if someone is reading the file, others may read it at the same time.

准确地说，在操作系统中，我们称这种情况为**读者-作者问题**

问题参数:

*   A set of data is shared by multiple processes.
*   Once the writer is ready, it will write. Only one writer can write at a time.
*   If one process is writing, no other process can read.
*   If at least one reader is reading, no other process can write.
*   Readers can't write, only read.

**当读者优先于作者时的解决方案**

这里的优先级是指，如果共享当前已打开进行读取，则不应有任何读取器等待。

使用三个变量:**互斥，wrt，readcnt** 实现解

1.  **semaphore** is mutually exclusive, wrt；; //semaphore **mutex** is used to ensure mutex when **readcnt** is updated, that is, when any reader enters or exits the critical area, semaphore **wrt** is used by both reader and writer.
2.  **int** read CNT； // **Readcnt** indicates the number of processes performing reading in the critical area, which is initially 0.

【sempahore 的功能:

–wait():递减信号量值。

–signal():递增信号量值。

**作家流程:**

1.  The writer requests to enter the critical area.
2.  If allowed, that is, wait () gives a true value, then enter and write. If not, it will continue to wait.
3.  Exit the critical section.

```
do {
    // writer requests for critical section
    wait(wrt);  

    // performs the write

    // leaves the critical section
    signal(wrt);

} while(true);
```

**读者流程:**

1.  Readers request to enter the comment area.
2.  If allowed:
    *   It will increase the number of readers in the critical area. If the reader is the first reader to enter, it will lock the **wrt** semaphore to restrict the entry of the writer (if there is any reader in it).
    *   Then, when other readers are already reading, it sends out a mutually exclusive signal when any other reader is allowed to enter.
    *   After reading, exit the critical section. When exiting, it checks whether there are no more readers in it, and it signals the semaphore "wrt", just like now, the writer can enter the critical section.
3.  If not, continue to wait.

```
do {

   // Reader wants to enter the critical section
   wait(mutex);

   // The number of readers has now increased by 1
   readcnt++;                          

   // there is atleast one reader in the critical section
   // this ensure no writer can enter if there is even one reader
   // thus we give preference to readers here
   if (readcnt==1)     
      wait(wrt);                    

   // other readers can enter while this current reader is inside 
   // the critical section
   signal(mutex);                   

   // current reader performs reading here
   wait(mutex);   // a reader wants to leave

   readcnt--;

   // that is, no reader is left in the critical section,
   if (readcnt == 0) 
       signal(wrt);         // writers can enter

   signal(mutex); // reader leaves

} while(true);
```

因此，信号量“ **wrt** ”在读取器和写入器上排队，使得如果写入器也在读取器和写入器上，则优先考虑读取器。因此，没有读者仅仅因为作者请求进入关键部分而等待。

[Ekta Goel](https://www.linkedin.com/pub/ekta-goel/75/12a/3a6) 投稿文章。如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论