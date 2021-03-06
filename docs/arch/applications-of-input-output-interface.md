# 输入/输出接口的应用

> 原文:[https://www . geesforgeks . org/applications-of-input-output-interface/](https://www.geeksforgeeks.org/applications-of-input-output-interface/)

**I/O 接口:**
任何一个 CPU 想要和 I/O 设备进行通信，都有表面的需求。该接口用于解释中央处理器产生的地址。因此，表面用于与输入/输出设备通信，即在中央处理器和输入/输出设备之间共享信息，使用的接口称为 **[输入/输出接口](https://www.geeksforgeeks.org/structure-of-input-output-interface/?ref=rp)** 。

**I/O 接口的各种应用:**
I/O 的应用就是我们可以说接口有权限打开任何文件而没有任何一种关于文件的信息即即使文件的基本信息也是未知的。它还有一个特点，即使不会对操作系统造成任何中断，也可以用来给计算机系统增加新的设备。它还可以通过识别一般类型来抽象输入/输出设备的差异。对每种通用类型的访问都是通过一组标准化的功能进行的，称为**接口。**

每种类型的操作系统都有自己的设备驱动程序接口类别。给定的设备可能附带多个设备驱动程序，例如，用于 Windows、Linux、AIX 和 Mac OS 的驱动程序，设备可能因尺寸而异，如下表所示:

| 没有。 | 基础 | 改变 | 例子 |
| --- | --- | --- | --- |
| 1. | 数据传输模式 | 字符或块 | 终端磁盘 |
| 2. | 访问数据的方法 | 顺序或随机 | 调制解调器，光盘 |
| 3. | 转移计划 | 同步还是异步 | 键盘磁带 |
| 4. | 共享方法 | 专用或共享 | 键盘磁带 |
| 5. | 设备速度 | 延迟、寻道时间、传输速率、操作之间的延迟 |  |
| 6. | 输入输出接口 | 只读，只写，读写 | 光盘图形控制器磁盘 |

1.  **字符流或块:**
    字符流或块都以字节的形式传输数据。两者的区别在于字符流以线性方式传输字节，即一个接一个，而块以单个单元传输整个字节。
2.  **顺序或随机访问:**
    要按照设备确定的固定顺序传输数据，我们使用顺序设备，而用户要指示设备寻找任何数据存储位置，则使用随机访问设备。
3.  **同步或异步:**
    响应时间可预测的数据传输由同步设备与系统的其他方面协调执行。异步设备表现出与其他计算机事件不协调的不规则或不可预测的响应时间。
4.  **可共享或专用:**
    可共享设备可以同时使用多个进程或线程；而专用设备不能。
5.  **运行速度:**
    设备的速度范围设置为每秒几个字节到每秒几个千兆字节。
6.  **读写、只读、只写:**
    不同的设备执行不同的操作，有的同时支持输入和输出，但有的只支持一个数据传输方向输入或输出。