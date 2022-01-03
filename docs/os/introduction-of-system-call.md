# 系统调用介绍

> 原文:[https://www.geeksforgeeks.org/introduction-of-system-call/](https://www.geeksforgeeks.org/introduction-of-system-call/)

在计算中，**系统调用**是一种编程方式，在这种方式下，计算机程序从运行它的操作系统内核请求服务。系统调用是程序**与操作系统**交互的一种方式。计算机程序在向操作系统内核发出请求时会进行系统调用。系统调用**通过应用程序接口(API)向用户程序提供**操作系统服务。它提供了进程和操作系统之间的接口，允许用户级进程请求操作系统的服务。系统调用是进入内核系统的唯一入口点。所有需要资源的程序都必须使用系统调用。

**系统调用提供的服务:**

1.  流程创建和管理
2.  主存管理
3.  文件访问、目录和文件系统管理
4.  设备处理
5.  保护
6.  Networking, etc.

    **系统调用的类型:**系统调用有 5 种不同的类别–

    1.  **进程控制:**结束、中止、创建、终止、分配和释放内存。
    2.  **文件管理:**创建、打开、关闭、删除、读取文件等。
    3.  设备管理
    4.  信息维护
    5.  沟通

    **Windows 和 Unix 系统调用示例–**

    <center>

    |  | Windows 操作系统 | Unix 操作系统 |
    | 过程控制 | CreateProcess()
    ExitProcess()
    WaitForSingleObject() | fork()
    exit()
    wait() |
    | 文件操作 | create file()
    read file()
    write file()
    close handler() | open()
    read()
    write()
    close() |
    | 设备操纵 | set onslemode()
    read console()
    write console() | ioctl()
    read()
    write() |
    | 信息维护 | GetCurrentProcessID（）
    SetTimer（）
    Sleep（） | getpid()
    报警()
    睡眠() |
    | 沟通 | createpipe()
    create file mapping()
    mapviewoffile() | 管道()
    shmget()
    mmap() |
    | 保护 | setfile security()
    InitlializeSecurityDescriptor()
    SetSecurityDescriptorGroup() | chmod()
    umask()
    chown() |

    </center>

    **Reference –**[http://www.cs.columbia.edu/~jae/4118/L02-intro2-osc-ch2.pdf](http://www.cs.columbia.edu/~jae/4118/L02-intro2-osc-ch2.pdf)