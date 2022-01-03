# 法新社全文

> 原文:[https://www.geeksforgeeks.org/afp-fullform/](https://www.geeksforgeeks.org/afp-fullform/)

法新社代表**苹果备案协议**。这是一种用于在服务器和客户端之间共享文件的苹果操作系统网络协议。它允许用户访问属于外部系统的文件。它是应用层和会话层协议。

**功能:**

*   Unicode file names are supported.
*   It provides a portable operating system interface (POSIX).
*   It also provides [access control list (ACL)](https://www.geeksforgeeks.org/access-lists-acl/) authority, specifying which system processes and users are allowed to access objects and perform necessary operations.
*   It provides storage facilities for structured data using resource bifurcation and unstructured data using data bifurcation.
*   Support both [TCP/IP](https://www.geeksforgeeks.org/tcp-ip-model/) and AppleTalk to communicate and provide various services.
*   In AFP protocol, commands such as creating directory, closing directory, copying files, deleting files and closing volumes can be executed.

**优势:**

*   It provides security functions for the system and restricts users from accessing dangerous files by using advanced file locking mechanism.
*   It also includes named extended attributes that users can use to map unexplained computer files with metadata.
*   Besides local file access, it also supports server file access by establishing a remote file server connection.
*   It provides 100% compatibility with Mac file system (HFS+) and is also a native file sharing protocol.
*   It provides built-in functions such as spotlight search, time machine, Mac alias and Bonjour service.

**缺点:**

*   Incompatible with storage devices formatted with Apple File System (APFS).
*   Its sequential read-write speed is lower than that of server message block (SMB) protocol.