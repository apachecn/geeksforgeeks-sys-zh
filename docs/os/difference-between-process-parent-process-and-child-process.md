# 流程、父流程和子流程的区别

> 原文:[https://www . geeksforgeeks . org/进程-父进程-子进程的区别/](https://www.geeksforgeeks.org/difference-between-process-parent-process-and-child-process/)

运行程序是一个 [<u>的过程</u>](https://www.geeksforgeeks.org/states-of-a-process-in-operating-systems/) 。从这个过程中，可以创建另一个过程。这两个过程之间存在父子关系。这可以通过使用名为 fork()的库函数来实现。fork()函数将正在运行的进程分成两个进程，现有的进程称为父进程，新的进程称为子进程。这里有一个程序演示了这一点:

## C

```
// C program to demonstrate
// the above concept
#include <sys/types.h>
#include<stdio.h>
#include <unistd.h> 

// Driver code
int main()
{
  printf ("Before Forking\n");
  fork();
  printf ("After Forking\n");
}
```

**Output**

```
Before Forking
After Forking
Before Forking
After Forking
```

**说明:**所有**叉()**后的语句执行两次:

1.  一旦通过**父进程。**
2.  第二次语句由**子进程**执行。

让我们更详细地讨论以下概念:

1.  流程。
2.  父进程。
3.  子流程。

**<u>进程</u> :** 进程是正在执行的程序，即活动程序。一个流程不止是程序代码，它包括以下内容:

1.  程序计数器。
2.  进程堆栈。
3.  寄存器。
4.  程序代码等。

相反，程序代码只是一个文本部分。

进程在执行时会改变其状态。新状态部分取决于进程的当前活动。流程在执行过程中的不同状态是:

1.  新的
2.  准备好的
3.  运转
4.  堵塞的
5.  终止。

一个[过程控制块和过程表](https://www.geeksforgeeks.org/process-table-and-process-control-block-pcb/)与每个过程相关联。它包含有关该过程的以下重要信息:

1.  进程状态。
2.  流程编号。
3.  程序计数器。
4.  文件和寄存器列表。
5.  CPU 信息。
6.  记忆信息等。

**<u>父进程</u> :** 除了启动进程，所有进程都是在进程执行 fork()系统调用时创建的。执行 [<u>fork()系统调用</u>](https://www.geeksforgeeks.org/fork-system-call/) 的流程是父流程。父进程是使用 fork()系统调用创建子进程的进程。一个父进程可能有多个子进程，但一个子进程只有一个父进程。

fork()系统调用成功时:

*   子进程的进程标识返回给父进程。
*   0 被返回给子进程。

fork()系统调用失败时，

*   -1 返回到父进程。
*   不会创建子进程。

**<u>子进程</u> :** 子进程由操作系统中的父进程使用 fork()系统调用创建。子流程也可以称为子流程或子任务。

*   子进程被创建为其父进程的副本。
*   子进程继承了它的大部分属性。
*   如果子进程没有父进程，那么子进程是由内核直接创建的。
*   如果子进程退出或被中断，则向父进程发送 SIGCHLD 信号，通知子进程的终止或退出。

**<u>为什么我们需要创建一个子流程</u>？**
有时一个程序需要同时执行多个功能。由于这些作业可能相互关联，因此无法创建两个不同的程序来执行它们。例如:假设有两个作业:将源文件的内容复制到目标文件，并显示一个动画进度条，指示文件复制正在进行中。GIF 进度条文件应该继续播放，直到文件复制开始。一旦复制过程完成，就应该停止播放 GIF 进度条文件。因为这两项工作是相互关联的，所以不能在两个不同的程序中执行。此外，它们不能一个接一个地执行。这两项工作应该同时进行。

此时 **fork()** 用于创建子进程，然后以这样的方式编写程序:文件复制由父进程完成，动画 GIF 文件的显示由**子进程**完成。

**程序 1:** 这里的任务是展示如何同时执行两个不同但相互关联的作业。因此，文件复制和播放动画 GIF 文件的实际代码已被跳过，只显示了同时执行两个作业的方法。

## C

```
// C program for the above approach
#include <sys/types.h>

// Driver Code
int main( )
{
  int pid;
  pid = fork();
  if (pid == 0)
  {
    printf ("In child process\n");

    /* code to play animated GIF file */
  }
  else
  {
    printf ("In parent process\n");

    /* code to copy file */
  }
}
```

**说明:** **fork()** 创建**子进程**，并在子进程中复制**父进程**的代码。此后，fork()函数的执行在两个进程中继续。因此，fork()中的重复代码只执行一次，而其中的剩余代码在父进程和子进程中都执行。因此，控制将从 fork()返回两次，即使它实际上只被调用了一次。当控件从父进程的 fork()返回时，它返回子进程的 PID，而当控件从子进程的 fork()返回时，它总是返回 0。程序可以利用这一点将我们希望在父进程中执行的代码与我们希望在子进程中执行的代码分开。这个逻辑在上面的程序中使用 if 语句实现。在子进程的情况下执行“if 块”，在父进程的情况下执行“else 块”。

**程序 2:**
这个程序将使用 **fork()** 调用来创建一个子进程。在子进程中，我们会打印子进程及其父进程的 **PID** ，而在父进程中，我们会打印父进程及其子进程的 **PID** 。

## C

```
// C program to implement
// the above approach
# include <sys/types.h>

// Driver code
int main()
{
  int pid;
  pid = fork();

  if (pid == 0)
  {
    printf ("Child : I am the child process\n");
    printf ("Child : Child’s PID: %d\n", getpid());
    printf ("Child : Parent’s PID: %d\n", getppid());
  }
  else
  {
    printf ("Parent : I am the parent process\n");
    printf ("Parent : Parent’s PID: %d\n", getpid());
    printf ("Parent : Child’s PID: %d\n", pid);
  }
}
```

**输出:**

```
Child : I am the child process
Child : Child's PID: 4706
Child : Parent's PID: 4705
Parent : I am the Parent process
Parent : Parent's PID: 4705
Parent : Child's PID: 4706
```