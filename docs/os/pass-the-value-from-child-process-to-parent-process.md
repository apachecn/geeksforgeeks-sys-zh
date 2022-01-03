# 将值从子进程传递到父进程

> 原文:[https://www . geesforgeks . org/将子进程的值传递给父进程/](https://www.geeksforgeeks.org/pass-the-value-from-child-process-to-parent-process/)

**先决条件** : [Pipe()和 Fork() Basic](https://www.geeksforgeeks.org/c-program-demonstrate-fork-and-pipe/)
编写一个 C 程序，子进程取一个输入数组，用 Pipe()和 Fork()发送给父进程，然后在父进程中打印出来。

**示例:**假设子进程中有一个数组 a[]={1，2，3，4，5}，那么输出应该是 1 2 3 4 5。

```
Input:  1 2 3 4 5
Output: 1 2 3 4 5

```

```
// C program for passing value from
// child process to parent process
#include <pthread.h>
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h> 
#include <stdlib.h> 
#include <sys/wait.h>
#define MAX 10

int main()
{

  int fd[2], i = 0;
  pipe(fd);
  pid_t pid = fork();

   if(pid > 0) {
      wait(NULL);

      // closing the standard input 
      close(0);

      // no need to use the write end of pipe here so close it
      close(fd[1]); 

       // duplicating fd[0] with standard input 0
      dup(fd[0]); 
      int arr[MAX];

      // n stores the total bytes read successfully
      int n = read(fd[0], arr, sizeof(arr));
      for ( i = 0;i < n/4; i++)

         // printing the array received from child process
          printf("%d ", arr[i]); 
  } 
  else if( pid == 0 ) {
      int arr[] = {1, 2, 3, 4, 5};

      // no need to use the read end of pipe here so close it
      close(fd[0]); 

       // closing the standard output
      close(1);    

      // duplicating fd[0] with standard output 1
      dup(fd[1]);  
      write(1, arr, sizeof(arr));
  } 

  else {
      perror("error\n"); //fork()
  }
} 
```

**执行上述代码的步骤:**

*   要编译，编写 **gcc 程序 _name.c**
*   要跑，写**。/a.out**