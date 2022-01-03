# 带示例 C 程序的命名管道或先进先出

> 原文:[https://www . geesforgeks . org/named-pipe-FIFO-example-c-program/](https://www.geeksforgeeks.org/named-pipe-fifo-example-c-program/)

在计算中，命名管道(也称为**先进先出**)是进程间通信的方法之一。

*   它是 Unix 上传统管道概念的扩展。传统的管道是“未命名的”，并且只持续整个过程。
*   然而，命名管道可以持续到系统启动，超过流程的生命周期。如果不再使用，可以删除。
*   通常，命名管道显示为一个文件，通常进程附加到它上面，用于进程间通信。先进先出文件是本地存储器上的一种特殊文件，它允许两个或多个进程通过读/写这个文件来相互通信。
*   通过调用 c 语言中的 *mkfifo()* 将一个 fifo 特殊文件输入到文件系统中。一旦我们用这种方式创建了一个 FIFO 特殊文件，任何进程都可以打开它进行读取或写入，就像普通文件一样。但是，它必须在两端同时打开，然后才能继续对它进行任何输入或输出操作。

**创建 FIFO 文件:**为了创建 FIFO 文件，使用了一个函数调用，即 mkfifo。

## 卡片打印处理机（Card Print Processor 的缩写）

```
int mkfifo(const char *pathname, mode_t mode);
```

mkfifo()制作一个名为 ***路径名*** 的 fifo 特殊文件。这里 ***模式*** 指定了先进先出的权限。它以通常的方式被进程的 umask 修改:创建的文件的权限是(模式& ~umask)。
**使用 FIFO:** 由于命名管道(FIFO)是一种文件，我们可以使用与之关联的所有系统调用即*打开*、*读取*、*写入*、*关闭*。
**举例说明命名管道的程序:**有两个程序使用相同的先进先出。程序 1 先写，然后读。程序 2 先读，然后写。他们都一直这样做，直到终止。

<gfg-tab role="tab" slot="tab" id="gfg-tab-0">Program 1(Writes first)</gfg-tab><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="C"></gfg-panel>

```
 // C program to implement one side of FIFO
// This side writes first, then reads
#include <stdio.h>
#include <string.h>
#include <fcntl.h>
#include <sys/stat.h>
#include <sys/types.h>
#include <unistd.h>

int main()
{
    int fd;

    // FIFO file path
    char * myfifo = "/tmp/myfifo";

    // Creating the named file(FIFO)
    // mkfifo(<pathname>, <permission>)
    mkfifo(myfifo, 0666);

    char arr1[80], arr2[80];
    while (1)
    {
        // Open FIFO for write only
        fd = open(myfifo, O_WRONLY);

        // Take an input arr2ing from user.
        // 80 is maximum length
        fgets(arr2, 80, stdin);

        // Write the input arr2ing on FIFO
        // and close it
        write(fd, arr2, strlen(arr2)+1);
        close(fd);

        // Open FIFO for Read only
        fd = open(myfifo, O_RDONLY);

        // Read from FIFO
        read(fd, arr1, sizeof(arr1));

        // Print the read message
        printf("User2: %s\n", arr1);
        close(fd);
    }
    return 0;
} 
```

<gfg-tab role="tab" slot="tab" id="gfg-tab-1">程序 2(先读)</gfg-tab><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-1" data-code-lang="C"></gfg-panel>

```
 // C program to implement one side of FIFO
// This side reads first, then reads
#include <stdio.h>
#include <string.h>
#include <fcntl.h>
#include <sys/stat.h>
#include <sys/types.h>
#include <unistd.h>

int main()
{
    int fd1;

    // FIFO file path
    char * myfifo = "/tmp/myfifo";

    // Creating the named file(FIFO)
    // mkfifo(<pathname>,<permission>)
    mkfifo(myfifo, 0666);

    char str1[80], str2[80];
    while (1)
    {
        // First open in read only and read
        fd1 = open(myfifo,O_RDONLY);
        read(fd1, str1, 80);

        // Print the read string and close
        printf("User1: %s\n", str1);
        close(fd1);

        // Now open in write mode and write
        // string taken from user.
        fd1 = open(myfifo,O_WRONLY);
        fgets(str2, 80, stdin);
        write(fd1, str2, strlen(str2)+1);
        close(fd1);
    }
    return 0;
} 
```