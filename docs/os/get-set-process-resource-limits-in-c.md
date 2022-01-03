# 在 C

中获取/设置流程资源限制

> 原文:[https://www . geesforgeks . org/get-set-process-resource-limits-in-c/](https://www.geeksforgeeks.org/get-set-process-resource-limits-in-c/)

**getrlimit()** 和 **setrlimit()** 系统调用可以用来获取和设置文件、CPU、内存等资源限制。与流程相关联。

> 每个资源都有一个相关的**软限制和硬限制。**
> 
> *   ***软限制* :** 软限制是内核对相应资源实施的实际限制。
> *   ***硬限制* :** 硬限制是软限制的上限。
> 
> **软限制范围在 0 和硬限制之间。**

这两个限制由以下结构定义

```
struct rlimit {
    rlim_t rlim_cur;  /* Soft limit */
    rlim_t rlim_max;  /* Hard limit (ceiling for rlim_cur) */
};
```

系统调用的签名是

```
int getrlimit(int resource, struct rlimit *rlim);
int setrlimit(int resource, const struct rlimit *rlim);
```

**资源**是指您想要检索或修改的资源限制。
要设置两个限制，*用新值设置 rlimit 结构元素的值。*
到**得到**两个极限，*传递 rlim 的地址。成功调用 getrlimit()，将 rlimit 元素设置为极限。*
在**成功**时，两者都返回 **0** 。在**错误**上，返回 **-1** ，并适当设置 errno。

```
Here, is a program demonstrating the system calls by changing the value one greater than the maximum file descriptor number to 3.
```

```
// C program to demonstrate working of getrlimit() 
// and setlimit()
#include <stdio.h>
#include <sys/resource.h>
#include <string.h>
#include <errno.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>

int main() {

    struct rlimit old_lim, lim, new_lim;

    // Get old limits
    if( getrlimit(RLIMIT_NOFILE, &old_lim) == 0)
        printf("Old limits -> soft limit= %ld \t"
           " hard limit= %ld \n", old_lim.rlim_cur, 
                                 old_lim.rlim_max);
    else
        fprintf(stderr, "%s\n", strerror(errno));

    // Set new value
    lim.rlim_cur = 3;
    lim.rlim_max = 1024;

    // Set limits
    if(setrlimit(RLIMIT_NOFILE, &lim) == -1)
        fprintf(stderr, "%s\n", strerror(errno));

    // Get new limits
    if( getrlimit(RLIMIT_NOFILE, &new_lim) == 0)
        printf("New limits -> soft limit= %ld "
         "\t hard limit= %ld \n", new_lim.rlim_cur, 
                                  new_lim.rlim_max);
    else
        fprintf(stderr, "%s\n", strerror(errno));
    return 0;
}
```

输出:

```
Old limits -> soft limit= 1048576      hard limit= 1048576 
New limits -> soft limit= 3              hard limit= 1024

```

旧限值可能因系统而异。

```
Now, If you try to open a new file, it will show run time error, because maximum 3 files can be opened and that are already being opened by the system(STDIN, STDOUT, STDERR).
```

```
// C program to demonstrate error when a 
// process tries to access resources beyond
// limit.
#include <stdio.h>
#include <sys/resource.h>
#include <string.h>
#include <errno.h>
#include <unistd.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>

int main() {

    struct rlimit old_lim, lim, new_lim;

    // Get old limits
    if( getrlimit(RLIMIT_NOFILE, &old_lim) == 0)
        printf("Old limits -> soft limit= %ld \t"
          " hard limit= %ld \n", old_lim.rlim_cur,
                               old_lim.rlim_max);
    else
        fprintf(stderr, "%s\n", strerror(errno));

    // Set new value
    lim.rlim_cur = 3;
    lim.rlim_max = 1024;

    // Set limits
    if(setrlimit(RLIMIT_NOFILE, &lim) == -1)
        fprintf(stderr, "%s\n", strerror(errno));

    // Get new limits
    if( getrlimit(RLIMIT_NOFILE, &new_lim) == 0)
        printf("New limits -> soft limit= %ld \t"
          " hard limit= %ld \n", new_lim.rlim_cur, 
                                new_lim.rlim_max);
    else
        fprintf(stderr, "%s\n", strerror(errno));

    // Try to open a new file
    if(open("foo.txt", O_WRONLY | O_CREAT, 0) == -1)
        fprintf(stderr, "%s\n", strerror(errno));
    else
            printf("Opened successfully\n");

    return 0;
}
```

输出:

```
Old limits -> soft limit= 1048576      hard limit= 1048576

New limits -> soft limit= 3                      hard limit= 1024

Too many open files
```

There is another system call **prlimit()** that combines both the system calls.
For more details, check manual by typing

```
man 2 prlimit
```