# 什么是匿名 FTP(文件传输协议)？

> 原文:[https://www . geesforgeks . org/什么是匿名-FTP-文件传输-协议/](https://www.geeksforgeeks.org/what-is-anonymous-ftp-file-transfer-protocol/)

AFTP(匿名文件传输协议)是一种使用基于 TCP 的网络传输文件的网络协议。匿名文件传输协议允许用户匿名地将文件从一台计算机移动到另一台计算机。

匿名 FTP 在第 7 层运行；匿名 FTP 允许没有任何指定密码或用户 ID 的匿名外部计算机用户访问 FTP 服务器，即当用户访问文件时，他们不需要识别自己。因此，允许匿名 FTP 的网站中包含的所有数据都应被视为可公开访问。

一般来说，无论何时用户访问匿名文件传输协议网站，都不会被要求提供用户名或密码。虽然有时它可能会要求提供用户名和密码，在这种情况下，用户可以为他们的用户名提供 ftp 或匿名这个词，他们可以为密码提供他们想要的任何东西。要获取任何文件，用户必须知道该文件的路径名及其所属的主机。

### **AFTP 时段:**

AFTP 是一个用户登录远程服务器的 FTP 会话。要启动会话，用户需要使用“ftp”命令和主机名/IP。存档站点的所有 FTP 程序响应前面都有一个称为回复代码的数字。

一般来说，几乎每个文件传输协议程序都必须遵循下面给出的命令。

*   Users need to log in to the local host and call the FTP program.
*   Then open the connection with the host.
*   After establishing a connection with the remote host, the user needs to log in anonymously with the user name.
*   After providing the user name, the user needs to provide the password.
*   After providing the password, provide any FTP commands required by the user.
*   Finally, after completion, exit the FTP program, and the connection will be closed.

```
Wtr.ca% ftp pbshr.com
Connected to pbshr.com
220 pbshr.com FTP server (Sat Nov 6 13:10:12 IST 2021) ready.
Name (pbshr.com: allen): anonymous
331 Guest login ok, enter your email address as the password.
Password:
230 Guest login ok, access restrictions apply.
ftp> cd files/atl/ar5
250 Please read the file readfile.txt
250 it was last modified on Wed Oct 13 12:48:50 2021 – 23 days ago  
250 CWD command successful.
ftp> binary
200 Type set to I.
ftp> get ar5-bc-3.4.h.txt
200 PORT command successful.
150 opening ASCII mode data connection for ar5-bc-3.4.h.txt (159873 bytes).
226 Transfer complete.
local: ar5-bc-3.4.h.txt remote: ar5-bc-3.4.h.txt
167925 bytes received in 0.6 seconds (2.7e+02 Kbytes/s)
ftp> quit
221 Goodbye
Wtr.ca%
```

**匿名 FTP 的优势:**

*   No authentication is required.
*   It allows quick access to public archives without any web server process.
*   AFTP can transfer not only multiple files, but also multiple directories at the same time.

**匿名 FTP 的缺点:**

*   Not completely anonymous.
*   Because the FTP server is completely open, there is less control over who accesses your server.
*   If used improperly, it will endanger the whole system. That is, extra security steps are needed to prevent any exploitation.