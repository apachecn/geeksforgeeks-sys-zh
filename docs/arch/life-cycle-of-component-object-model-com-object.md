# 组件对象模型(COM)对象的生命周期

> 原文:[https://www . geesforgeks . org/组件生命周期-对象-模型-com-object/](https://www.geeksforgeeks.org/life-cycle-of-component-object-model-com-object/)

[组件对象模型](https://www.geeksforgeeks.org/difference-between-com-and-dcom/)对象生命周期过程是利用组件对象模型进行有用资源维护和组件交互的技术。COM 是微软开发的典型软件结构，它提供了集成软件程序组件的框架。

这个框架允许开发人员在组装可重用组件的帮助下构建结构。通过定义应用编程接口(API)，COM 批准以定制的目的引入和集成因素，或者批准各种因素进行交互。只有当元素遵循微软的二进制结构时，相互作用才是可行的。如果遵循这种二进制结构，用独占的[编程语言](https://www.geeksforgeeks.org/introduction-to-programming-languages/)编写的组件可以互操作。

当客户请求创建和使用组件对象时，组件的生命周期技术开始脱离进化。组件对象生命周期涉及以下步骤:

1.  **客户端请求:**
    COM 客户端请求是对象创建的第一段。这里，组件客户端是每一个调用组件应用编程接口来实例化新组件对象的实用程序。然后，它将唯一的 CLSID 或类 ID 传递给 COM，并作为回报要求实例化对象。COM 客户端负责两个特定的任务，如果它们在应用程序启动时不再完成，则必须包含在这个部分的开始:

*   COM 客户端需要确认 COM 库模型是新的，足以支持通过应用程序预测的性能。一般来说，应用程序可以使用最新版本的库，但不再是旧版本。
*   COM client has to initialize COM Library.
    Client of COM object continually asks COM to instantiate objects in precisely identical manner and doesn’t depend on kind of server in use i.e., it may be in-process server, local server, or any other. Talking about methods so there are two types of methods, which client makes use of to make request. Easiest approach is to call COM function CoCreateInstance. In response to this, there is creation of one object of given Class id and it returns interface pointer of any requested type.

    同样有一个替代选项，即通过调用 CoGetClassObject，客户端可以实现并获取接口指针，该指针被称为类标识的类工厂对象。这个类工厂帮助被称为 IclassFactory 的接口，通过它消费者要求工厂制造它的类的对象。

*   **Server location :**
    Subsequent step concerned in COM object life-cycle is Server location.
    process. In this step, COM locates object implementation and initiates server system for object. A unique element referred to as Service Control Manager or SCM which is accountable for location and execution of COM server that implements COM object. SCM ensures that when client request is made, suitable server is linked and geared up to acquire request. SCM stores all class records in system registry, beneath unique textual content key named with object’s class ID.

    例如，服务控制管理器支持文件存储，并存储组件服务器的文件路径名，这有助于它们的本地化，并且可以很容易地找到其位置。COM 客户端通过 COM 库获取这些记录。

    通过配置管理采取的行动依赖于某种组件服务器:

    *   **进程内–**
        在这个过程中，包含对象服务器实现的 DLL 的文件路径由单片机提供。然后组件库负责加载动态链接库，并进一步向动态链接库请求其类工厂的接口指针。
    *   **Local–**
        在这个过程中，SCM 进一步找到并开始本地执行，注册类工厂的接口指针。
    *   **Remote –**
        At last, in this process, local SCM then contacts SCM running on appropriate remote pc, and forwards request to far off SCM. Then further remote SCM obtains interface pointer of class factory in one of two ways described above processes.

        它远程配置管理的功能是保持与类工厂的连接，并将 RPC 连接返回给本地配置管理。

        *   **对象创建:**
    在 COM 对象的生命周期中，第三个阶段被称为对象创建，通过给定类 ID 来创建对象。它包括三个内部步骤:
    *   获取 CLSID 的类工厂。
    *   要求类工厂实例化类的对象，并将接口指针返回给 COM 客户端。
    *   初始化 COM 对象。*   **Interaction :**
    When object is initialized, then fourth phase begins for this process, which is referred to as Interaction. During this phase, client can interact with newly instantiated COM object with help of interface pointers.

    创建阶段负责给客户端一个使用功能范围有限的接口指针。如果 COM 客户端需要在任何特定时间执行该范围之外的操作，那么要做到这一点，它需要调用接口函数 QueryInterface，以便在同一对象上请求另一个接口。

    *   **Disconnection :**
    The closing process phase is Disconnection that takes place when COM client no longer desires COM object. The groundwork of this step is Reference Counting mechanism. This mechanism offers COM object functionality to manipulate its very own lifetime. Hence, as alternative to releasing object directly, COM client needs to inform object to free itself.

    指定引用计数机制来提供这个控件。每个对象都保留 32 位引用，依赖于跟踪有多少客户端链接到它。32 位计数器的使用，可以处理多达 40 多亿个客户端，容量肯定没有过载计数的威胁。

    有 2 个接口函数，添加引用和释放，控制属于基本组件接口的计数。AddRef 函数用于增加计数，Release 函数用于减少计数。当引用递减为零时，这意味着所有正在使用 COM 对象的客户端和与之相关联的客户端现在都已断开连接，COM 对象可能会自我毁灭，即发生对象的自我销毁。