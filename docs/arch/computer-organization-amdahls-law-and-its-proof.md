# 计算机组织|阿姆达尔定律及其证明

> 原文:[https://www . geesforgeks . org/computer-organization-amdahl s-law-and-it-proof/](https://www.geeksforgeeks.org/computer-organization-amdahls-law-and-its-proof/)

它以计算机科学家吉恩·阿姆达尔(来自 IBM 和阿姆达尔公司的计算机架构师)的名字命名，并于 1967 年在 AFIPS 春季联合计算机会议上发表。也被称为 ***安达尔的论点*** 。这是一个公式，给出了在资源得到改善的系统在固定工作负载下执行任务的理论延迟加速。换句话说，它是一个公式，用于通过仅仅改进系统的特定部分来寻找最大可能的改进。在*并行计算*中经常使用它来预测使用多处理器时的理论加速比。

**加速-**
加速被定义为使用增强的整个任务的性能与不使用增强的整个任务的性能之比，或者加速可以被定义为不使用增强的整个任务的执行时间与使用增强的整个任务的执行时间之比。
如果 **Pe** 是在可能的情况下使用增强的整个任务的性能， **Pw** 是不使用增强的整个任务的性能， **Ew** 是不使用增强的整个任务的执行时间， **Ee** 是在可能的情况下使用增强的整个任务的执行时间，

**加速= Pe/Pw**
或
**加速= Ew/Ee**

阿姆达尔定律使用两个因素来发现某些增强带来的加速——

*   **分数增强**–原始计算机中计算时间的分数，可以转换为利用增强。例如，如果一个总共花费 40 秒的程序的 10 秒执行时间可以使用一个增强，那么这个分数就是 10/40。该获得值为*分数增强*。
    *强化分数始终小于 1* 。*   **Speedup enhanced** – The improvement gained by the enhanced execution mode; that is, how much faster the task would run if the enhanced mode were used for the entire program. For example – If the enhanced mode takes, say 3 seconds for a portion of the program, while it is 6 seconds in the original mode, the improvement is 6/3\. This value is Speedup enhanced.
    *Speedup Enhanced is always greater than 1*.

    整体加速是执行时间的比率:-

    ![](img/e15f3eb7359373d151f6c84961cc5950.png)

    **证明:-**
    让加速为 S，旧的执行时间为 T，新的执行时间为 T’，A 部分(将被增强)占用的执行时间为 T，A 部分(增强后)占用的执行时间为 T’，不被增强的部分占用的执行时间为 t <sub>n</sub> ，分数增强为 f’，加速增强为 S’。

    从上面的等式中，

    ![     S=\frac{T}{T'}  ](img/674e177aed34b49eca730fcdc7136bb1.png "Rendered by QuickLaTeX.com")

    ![   T=t_{n}+ t  ](img/0541056738f03f81040f39fb80e774ee.png "Rendered by QuickLaTeX.com")

    ![    T'=t_{n}+ t'](img/531c74eac5f6cdf218167f566e74bab1.png "Rendered by QuickLaTeX.com")

    ![     f' = \frac{t}{T}  ](img/17b1fa8b7e1ca962a087f5580c178a5a.png "Rendered by QuickLaTeX.com")

    ![      = \frac{t}{t+t_{n}}  ](img/26fcb66bab444e9c8cf7c3d2b4f1ae3a.png "Rendered by QuickLaTeX.com")

    ![       1-f'= 1- \frac{t}{t+t_{n}}  ](img/e2c46af157969ef93987dbf011cc5d46.png "Rendered by QuickLaTeX.com")

    ![    = \frac{t_{n}}{t+t_{n}}    ](img/bfe8c3b8f431d2e530293db02cdf95c1.png "Rendered by QuickLaTeX.com")

    ![       S'=\frac{t}{t'}       ](img/ddc0820900ac12587488c96b28ba7de5.png "Rendered by QuickLaTeX.com")

    ![      t'=\frac{t}{s'}     ](img/8b85637700ff0c8796ac3ae9b3e8dbe0.png "Rendered by QuickLaTeX.com")

    ![     =\frac{T*f'}{S'}     ](img/1c6073f9398508e0d94f45fd493491fe.png "Rendered by QuickLaTeX.com")

    ![     =\frac{(t_{n}+t)*f'}{S'}   ](img/3c7a643e8f43df0c227a60e2fff09258.png "Rendered by QuickLaTeX.com")

    ![    =\frac{t'}{t_{n}+t}=\frac{f'}{S'}  ](img/b61f48ef95281cfa11fd9713cd9038e2.png "Rendered by QuickLaTeX.com")

    ![  S=\frac{T}{T'}  ](img/ca5b5f8b8a8e5d1cc3f240922310034e.png "Rendered by QuickLaTeX.com")

    ![    = \frac{t_{n}+t}{t_{n}+t'}  ](img/4595214ee0fed192074a7d9cef31dd6c.png "Rendered by QuickLaTeX.com")

    ![        S = \frac{1}{1-f' + \frac{f'}{S'}}           ](img/c166203d7003267e2bd88fdefe5548c9.png "Rendered by QuickLaTeX.com")

    ![  Overall Speedup = \frac{1}{1 - Fraction Enhanced + ( Fraction Enhanced/Speedup Enhanced )}  ](img/857b459b69edb4045adf3017a0103102.png "Rendered by QuickLaTeX.com")
    遂证。