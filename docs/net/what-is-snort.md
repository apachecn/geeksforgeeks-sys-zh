# 什么是 SNORT？

> 原文:[https://www.geeksforgeeks.org/what-is-snort/](https://www.geeksforgeeks.org/what-is-snort/)

**SNORT** 是用 C 编程语言编写的基于网络的入侵检测系统。它是由马丁·罗施在 1998 年开发的。现在是思科开发的。它是免费的开源软件。它还可以用作数据包嗅探器来实时监控系统。网络管理员可以使用它来监视所有传入的数据包，并找到对系统有危险的数据包。它基于库包捕获工具。这些规则很容易创建和实现，可以部署在任何类型的操作系统和任何类型的网络环境中。这种入侵检测系统比其他系统受欢迎的主要原因是，它是一个免费使用的软件，也是开源的，因为任何用户都可以按照他想要的方式使用它。

**特征:**

*   实时交通监控
*   数据包记录
*   协议分析
*   内容匹配
*   操作系统指纹识别
*   可以安装在任何网络环境中。
*   创建日志
*   开放源码
*   规则很容易实施

**安装步骤:**

在 Linux 中:

*   **步骤 1:** 获得 https://www.snort.org/downloads/snort/snort-2.9.15.tar.gz
*   **步骤 2:**tar xvzf snort-2 . 9 . 15 . tar . gz
*   **步骤 3:** cd snort-2.9.15
*   **第 4 步:**。/configure–enable-source fire&&make&&sudo make install

在窗口中:

*   **步骤-1:** 从 https://www . SNORT . org/downloads/SNORT/SNORT _ 2 _ 9 _ 15 _ installer . exe 下载 SNORT 安装程序
*   **步骤-1:** 执行 Snort_2_9_15_Installer.exe

**基本用法:**

1.  **嗅探器模式–**
    要打印 TCP/IP 报头，请使用命令**。/snort -v**
    要打印 IP 地址和报头，请使用命令**。/snort -vd**
2.  **数据包记录–**
    要将数据包存储在磁盘中，您需要给出存储日志的路径。对于这个命令是**。/snort -dev -l ./SnortLogs** 。
3.  **激活网络入侵检测模式–**
    要启动该模式，请使用此命令**。/snort-dev-l ./snort logs-h 192 . 127 . 1 . 0/24-c snort . conf**