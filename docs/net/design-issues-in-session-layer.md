# 会话层的设计问题

> 原文:[https://www . geesforgeks . org/design-issues-in-session-layer/](https://www.geeksforgeeks.org/design-issues-in-session-layer/)

**会话层**是 [OSI 模型](https://www.geeksforgeeks.org/c-plus-plus/)的七层之一。[物理层](https://practice.geeksforgeeks.org/problems/explain-working-of-physical-layer)、[数据链路层](https://www.geeksforgeeks.org/data-link-layer-in-osi-model/)和[网络层](https://www.geeksforgeeks.org/design-issues-in-network-layer/)缺少一些服务，例如在通信系统之间建立会话。这是由会话层管理的，会话层特别充当通信系统之间的对话控制器，从而促进它们之间的交互。

在研究设计问题之前，下面是会话层的一些功能:

1.  **对话控制–**
    会话层允许两个系统进入全双工或半双工的对话交换机制。
2.  **管理令牌–**
    网络中的通信系统尝试执行一些关键操作，而会话层
    可以防止在执行这些操作时可能发生的冲突，否则这些冲突会导致丢失。
3.  **Synchronization –**
    Checkpoints are the midway marks that are added after a particular interval during stream of data
    transfer. These points are also referred to as synchronization points. The Session layer permits process to add these checkpoints.

    例如，假设一个 400 页的文件正在通过网络发送，那么在每 50 页之后设置一个检查点是非常有益的，这样只有在前一页被接收和确认时才发送下一个 50 页。

**会话层的设计问题:**

1.  **建立机器间会话–**
    机器间会话的建立是会话层提供的重要服务。此会话负责在连接的计算机之间创建对话。会话层提供了在终端用户应用程序进程之间打开、关闭和管理会话的机制，即半永久对话。此会话由应用程序之间发生的请求和响应组成。
2.  **增强服务–**
    某些服务(如检查点和令牌管理)是会话层的关键功能，因此有必要在会话层设计期间不断增强这些功能。
3.  **帮助令牌管理和同步–**
    会话层在防止多个关键操作冲突以及通过在特定时间间隔建立同步点来确保更好的网络数据传输方面发挥着重要作用。因此，确保正确执行这些服务变得非常重要。