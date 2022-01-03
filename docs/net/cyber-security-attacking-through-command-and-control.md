# 网络安全——通过指挥和控制进行攻击

> 原文:[https://www . geesforgeks . org/网络安全-通过命令和控制进行攻击/](https://www.geeksforgeeks.org/cyber-security-attacking-through-command-and-control/)

C&C 指挥控制服务器基本上是一台由黑客或任何网络罪犯控制的计算机。其被恶意地用于命令已经被恶意软件利用或危害的各种系统，并且这些服务器还被黑客用于从目标网络上被危害的机器秘密地接收期望的数据。现在，随着 C&C 服务器能够轻松地在目标网络中进行转换和融合，许多组织已经开始使用各种类型的基于云的服务。

### **C&C 是如何工作的？**

在本节中，我们将讨论使用的各种命令和控制技术。

**1。**在最近十年里，报复性组织的黑客数量呈上升趋势。最具危害性的利用之一，经常通过域名系统执行，是通过命令和控制培养出来的，另外称为 C2 或 T2

**2。**黑客首先通过利用目标组织内部的机器开始攻击，该机器可能在防火墙后面。这应该可以通过多种方式实现:

*   通过网络钓鱼。
*   通过浏览器插件中的漏洞。
*   通过在受害机器上执行各种恶意程序或应用程序。

**3。**此后，当目标网络上的一台计算机受到攻击并建立连接时，被利用的机器通过向攻击者机器发送进一步命令的信号来确认攻击者机器。

**4。**该受害机器将执行黑客的 C & C 服务器传入的进一步命令，并可能强制下载其他支持软件进行进一步攻击。

**5。**现在，黑客已经完成了完全控制受害者机器的任务，因此可以在其上运行任何种类的恶意代码。同样，恶意代码会进一步轻松地在网络中枢转；完全由一个组织的整个 IT 基础设施组成，这将最终导致创建一个已经受损的机器网络，也称为僵尸网络。

**6。**通过这种方式，黑客可以通过目标的网络获得完全未经授权的访问。

**7。** C & C 作为攻击中使用的恶意软件的大本营，递归地报告嗅探或窃取的数据，并且各种支持攻击的命令也存储在服务器上。为了在网络中绕过，这种攻击的一个重要步骤是建立 C & C 连接。

**8。** C2 服务器也是僵尸网络中已经被利用的机器的总部。它很可能被用来分散那些可以获取信息、传播恶意软件、扰乱网络管理的命令，从此以后，天空就是极限。

**9。除了允许攻击者获取信息之外，机器上 C & C 程序的存在同样可能会干扰真正的应用程序并导致未来资产的滥用。**

### C&C 服务器中的僵尸网络架构

**1。集中式模型:**一种网络模型，其中所有客户端都与一个焦点系统接口，该焦点系统是所有通信的代理操作员。

*   该系统/服务器将存储通信和客户账户数据。
*   大多数开放的短信阶段利用一个统一的组织。
*   另外，称为集中主机结构。

**2。对等模型:**对等计算或系统管理是一种循环的应用程序设计，它在对等方之间分配差事或未完成的负担。

*   The connected peers or nodes are also favored equal members in the application.
*   It is said that they have built a shared hub organization.
*   Nodes provide some of their own assets, such as preparation power, circle reserve or organization data transmission, directly to other organization members, without the coordination of staff or stable hosts.
*   It is the two providers and buyers of assets of peers, rather than the traditional customer worker model, in which the utilization and elegance of assets are separated.
*   The development of cooperative P2P framework is going through a period when friends share assets and make comparisons at the same time, and they are looking for different partners who can acquire extraordinary assets and capabilities, so that virtual networks can participate in more noteworthy undertakings than a single friend can cultivate, and at the same time it is helpful to all partners.

**3。随机模型:**任意地理僵尸网络不依赖任何 C & C 主机；相反，所有僵尸网络订单都是合法发送的，从一个僵尸开始，然后发送到下一个，极有可能它们被一些不常见的方法“标记”,表明它们是从僵尸网络所有者或另一个经批准的客户开始的。

*   This kind of botnet has extremely high dormancy, and will frequently take into account a large number of bots in the botnet, so that analysts can identify it with only one captured botnet.
*   Abnormal types of scrambling robots and robot communication that are common in open organizations are used in more complex C&C host geography (for example, in TDL-4 botnet) to provide such a botnet that is particularly difficult to destroy.

### 利用 C&C 的战功

*   **窃取信息:**敏感信息，例如预算记录，可以被复制或转移到黑客的服务器。
*   **关闭:**攻击者可以关闭一台或几台机器，或者在任何情况下，关闭整个组织的网络。
*   **重启:**被利用的电脑可能会突然、持续地关闭并重启，这可能会干扰典型的正在进行的任务。
*   **分布式拒绝服务:** DDoS 攻击用无数的请求淹没了服务器，或者我们可以用巨大的互联网流量。一旦僵尸网络建立，攻击者可以指示每个机器人向目标 IP 地址发送请求，从而造成对目标地址或目标服务器的请求流量阻塞。因此，合法流量被拒绝访问。这种类型的攻击可以用来摧毁一个网站。

### C&C 探测

**1。不间断地观察所有入站和出站流量:**控制明确建议观察大量信息交换或未经批准的流量，这可能发生在漏洞利用的过滤期。

**2。区分网络流中的异常:**控制建议搜索组织流量中的不一致，这可能是恶意软件行为的表现(例如，C2 通信)或已经被利用的机器。

**3。记录域名系统查询并应用恶名检查:**控制部门建议检查域名系统要求，以确定已知的恶意区域或进行 C2 通信的努力。

**4。利用抵制:**利用抵制来拒绝内部机器对已知恶意主机的通信。

**5。整理组织流量:**整理日志检查框架中的组织流量和注意事项，用于额外的调查和评估，捕获和分解网络流量信息，以区分奇怪的移动。

**6。区分网络流量中未经批准的加密利用:**这里的推理是，恶意软件可能利用加密绕过依赖于流量内容检查的工具包(例如，DLP)来泄露敏感信息。

**7。阻碍进入:**阻碍进入已实现的记录移动和邮件过滤区域。寻找高峰时间交通堵塞设计中的不规则之处。

**8。按照信任区的指示分割组织:**如果可以设想将组织的高风险部分与高自尊部分明确隔离开来，那么这一行动尤其有益。

**9。保证客户询问内部域名系统服务器:**保证客户询问内部域名系统服务器，这些服务器可以被观察到，其答案可以被控制，例如，阻止进入已知的恶意或未经批准的区域。

### C&C 控制

**1。筛选所有入站和出站流量:**更确切地说，查看入站流量中可能导致污染的黑客攻击迹象、过量下载、免下车攻击或网络钓鱼攻击至关重要。应该对出站流量进行分解，搜索 C2 通道已经建立的标志(信息过滤、命令和控制注册等)。

**2。识别并审查组织流量中的特性:**理由是集中攻击依赖于一个基础，该基础不太倾向于被记住有害端点的大部分可访问安排，或者利用广泛恶意软件额外使用的 C2 方法(例如，约定)。在这一点上，专注于区分异常流量将使保护者有能力获得这些新的危险。这个提议有两个基本假设:定向攻击带来奇怪的流量，异常流量意味着讨价还价。这两个假设可能会时不时地被重新审视:我们已经看到，攻击者正在炮制新的技术来“混入”典型的流量；随着新的管理和小工具的出现，一个组织的流量质量可能会发生变化。

**3。收集组织流量的显式子集:**收集组织流量的显式子集，特别是 DNS 问题和网络流量信息。这个建议的灵感来自于收集这样的信息可能更简单，而不是建立一个完整的组织检查框架。正如我们从我们的写作调查中看到的，已经设计了一些方法来区分依赖于这些信息来源的 C2 交通。

**4。组织工程化:**组织工程化有助于改善交通检查和对袭击的反应。例如，通过在所有流量通过的地方有一个单独的阻塞点，一个被剖析的关联可以重新安排流量的全部分类和它的调查。

**5。屏蔽网络行为:**这将有助于区分对已知可怕端点的关联努力，即入侵防御系统和已知用于攻击的区域。理由是可以预先阻止对这些端点的准入，期望设置适当的组件(例如防火墙)。这里的关键观点显然是制作和保持有害端点的特殊排列。