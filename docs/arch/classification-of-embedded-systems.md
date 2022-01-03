# 嵌入式系统分类

> 原文:[https://www . geesforgeks . org/嵌入式系统分类/](https://www.geeksforgeeks.org/classification-of-embedded-systems/)

**嵌入式系统**根据两个因素进行分类，即

1.  性能和功能要求
2.  微控制器的性能

**根据性能和功能需求，分为以下 4 种类型:**

1.  **Real-Time Embedded Systems :**
    A Real-Time Embedded System is strictly time specific which means these embedded systems provides output in a particular/defined time interval. These type of embedded systems provide quick response in critical situations which gives most priority to time based task performance and generation of output. That’s why real time embedded systems are used in defense sector, medical and health care sector, and some other industrial applications where output in the right time is given more importance.

    此外，该实时嵌入式系统分为两种类型，即

    *   **软实时嵌入式系统–**
        在这些类型的嵌入式系统中，时间/截止日期并没有得到严格遵守。如果任务的截止日期已过(意味着系统没有在规定的时间内给出结果)，仍然接受结果或输出。
    *   **硬实时嵌入式系统–**
        在这些类型的嵌入式系统中，严格遵守任务的时间/截止日期。任务必须在两个时间框架(定义的时间间隔)之间完成，否则结果/输出可能不被接受。

    **示例:**

    *   交通管理系统
    *   国防部门的军事用途
    *   卫生部门的医疗用途
2.  **Stand Alone Embedded Systems :**
    Stand Alone Embedded Systems are independent systems which can work by themselves they don’t depend on a host system. It takes input in digital or analog form and provides the output.

    **示例:**

    *   MP3 播放器
    *   微波炉
    *   计算器
3.  **Networked Embedded Systems :**
    Networked Embedded Systems are connected to a network which may be wired or wireless to provide output to the attached device. They communicate with embedded web server through network.

    **示例:**

    *   家庭安全系统
    *   自动取款机
    *   刷卡机

4.  **Mobile Embedded Systems :**
    Mobile embedded systems are small and easy to use and requires less resources. They are the most preferred embedded systems. In portability point of view mobile embedded systems are also best.

    **示例:**

    *   MP3 播放器
    *   移动电话
    *   数码相机

**根据性能和微控制器分为以下 3 种:**

1.  **Small Scale Embedded Systems :**
    Small Scale Embedded Systems are designed using an 8-bit or 16-bit micro-controller. They can be powered by a battery. The processor uses very less/limited resources of memory and processing speed. Mainly these systems does not act as an independent system they act as any component of computer system but they did not compute and dedicated for a specific task.
2.  **Medium Scale Embedded Systems :**
    Medium Scale Embedded Systems are designed using an 16-bit or 32-bit micro-controller. These medium Scale Embedded Systems are faster than that of small Scale Embedded Systems. Integration of hardware and software is complex in these systems. [Java](https://www.geeksforgeeks.org/java/), [C](https://www.geeksforgeeks.org/c-programming-language/), [C++](https://www.geeksforgeeks.org/c-plus-plus/) are the programming languages are used to develop medium scale embedded systems. Different type of software tools like compiler, debugger, simulator etc are used to develop these type of systems.
3.  **复杂或复杂的嵌入式系统:**
    复杂或复杂的嵌入式系统使用多个 32 位或 64 位微控制器进行设计。这些系统是为执行大规模复杂功能而开发的。这些系统具有很高的硬件和软件复杂性。我们使用硬件和软件组件来设计最终系统或硬件产品。