# 威胁建模

> 原文:[https://www.geeksforgeeks.org/threat-modelling/](https://www.geeksforgeeks.org/threat-modelling/)

随着技术的进步，黑客获取敏感数据、禁用应用程序等变得越来越容易。因此，应用程序安全性已经成为一个主要问题。用于在设计过程中实现应用程序安全性的一种方法是通过威胁建模。

威胁可以是任何能够利用漏洞破坏安全并负面改变、删除、伤害对象或感兴趣对象的东西。威胁建模可以在开发的任何阶段进行，但是如果在开始时进行，它将有助于早期确定可以正确处理的威胁。

威胁建模的**目的**是尽早向组织的利益相关者识别、传达和理解威胁和缓解措施。这个过程的文档为系统分析师和维护者提供了对可能的攻击者配置文件、最可能的攻击媒介以及攻击者最想要的资产的完整分析。

威胁建模有助于实现以下目标:

1.  定义应用程序的安全性
2.  识别和调查潜在威胁和漏洞
3.  导致更早发现架构缺陷

开发团队将能够通过在设计阶段使用威胁建模来识别威胁、风险和缓解措施，从而将应用安全作为设计和开发过程的一部分来实施。有各种可用的威胁建模方法。我们将讨论 8 种方法:

1.  **STRIDE–**
    STRIDE 是微软为威胁建模开发的一种方法论。它为六类安全威胁提供了一个助记符:
    *   **欺骗:**假扮成另一个用户、组件或在被建模系统中具有身份的另一个系统的对手。
    *   **篡改:**对系统内数据的修改，以达到恶意目的。
    *   **否认:**在缺乏充分证据的情况下，对手否认实施某些恶意活动的能力。
    *   **信息披露:**将受保护数据暴露给用户，否则不允许用户访问该数据。
    *   **拒绝服务:**当对手使用不正当手段取得比他当前拥有的不同特权更高的信任级别时发生。
    *   **特权提升:**当攻击者成功破坏系统的管理控制并篡改其配置的权限和特权时，就会出现此威胁。通过这种方式，攻击者可以从网络中的低级系统到达包含机密信息的更高权限的系统。

2.  **发怵–**
    发怵是为了威胁建模而提出的，但由于评级不一致，它在 2008 年被微软放弃。它目前被 OpenStack 和许多其他公司使用。它使用五个类别为风险评级安全威胁提供了一个助记符。这些类别是:
    1.  **潜在损害:**对漏洞被利用时可能发生的损害程度进行排序。
    2.  **再现性:**排列重现攻击的难易程度
    3.  **可利用性:**为发动攻击所需的努力分配一个数字。
    4.  **受影响用户:**一个值，表示如果漏洞被广泛利用，会有多少人受到影响。
    5.  **可发现性:**衡量发现威胁的难易程度。

3.  **p . a . s . t . a .–**
    攻击模拟和威胁分析流程(PASTA)是一种以风险为中心的七步方法。目的是提供一个动态的威胁识别、枚举和评分过程。完成威胁模型后，安全主题专家会对已识别的威胁进行详细分析。最后，可以列举适当的安全控制。这有助于开发人员通过分析以攻击者为中心的应用程序视图来开发以资产为中心的缓解策略。

4.  **Trike–**
    重点是将威胁模型用作风险管理工具。威胁模型基于**需求模型**。需求模型建立了利益相关者定义的分配给每个资产类别的“可接受”风险水平。对需求模型的分析产生了一个威胁模型，从该模型中识别威胁并分配风险值。完整的威胁模型用于根据资产、角色、操作和计算出的风险敞口构建风险模型。

5.  **VAST–**
    VAST 是视觉、敏捷和简单威胁建模的缩写。该方法为各种利益相关者(如应用程序架构师和开发人员、网络安全人员等)的独特需求提供了可操作的输出。它提供了独特的应用程序和基础架构可视化方案，因此威胁模型的创建和使用不需要特定的安全主题专业知识。

6.  **Attack Tree –** 
    Attack trees are the conceptual diagram showing how an asset, or target, might be attacked. These are multi-level diagrams consisting of one root node, leaves, and children nodes. Bottom to Top, child nodes are conditions that must be satisfied to make the direct parent node true. An attack is considered complete when the root is satisfied. Each node may be satisfied only by its direct child nodes. 

    假设根节点下有 1 个孙子。在这种情况下，必须采取多个步骤来执行攻击，因为首先必须满足孙子的条件以使直接父节点为真，然后必须满足直接父节点的条件以使根节点为真。它还有“与”和“或”选项，代表实现该目标的备选方案和不同步骤。

7.  **Common Vulnerability Scoring System (CVSS) –** 
    It provides a way to capture the principal characteristics of a vulnerability and produce a numerical score (ranging from 0-10, with 10 being the most severe) depicting its severity. 

    然后可以将分数转化为定性表示(如低、中、高和关键)，以帮助组织正确评估其漏洞管理流程并确定其优先级。

8.  **T-MAP–**
    T-MAP 是商业现货(COTS)系统中用于计算攻击路径权重的方法。这个模型是通过使用 UML 类图、访问类图、漏洞类图、目标资产类图和受影响值类图来开发的。

目前，有八种工具可用于威胁建模:

1.  **微软的威胁建模工具–**
    该工具基于 STRIDE 威胁模型分类识别威胁，并基于数据流图(DFD)，可用于发现与组织中整体 IT 资产相关的威胁。

2.  **my appsecurity–**
    它提供了第一个商用威胁建模工具——威胁模型器。它使用 VAST 威胁分类方案，并基于流程图(PFD)，该流程图提供了风险和易受攻击漏洞的详细视图。

3.  **IriuRisk–**
    提供了该工具的社区版和商业版。该工具主要用于在整个软件开发生命周期中创建和维护实时威胁模型。它连接了几个不同的工具，如 OWASP ZAP、BDD-Security 等。以促进自动化，并涉及完全可定制的调查问卷和风险模式库。

4.  **securicade–**
    这是斯堪的纳维亚公司 foreseeti 开发的威胁建模和风险管理工具。通过对当前和未来的信息技术架构进行自动攻击模拟，并根据结果提供决策支持，来识别和量化风险。securiCAD 提供商业版和社区版。

5.  **安全罗盘的 SD 元素–**
    它是一个软件安全需求管理平台，包括自动威胁建模功能。针对应用程序的技术细节和法规遵从性驱动因素进行了简短的问卷调查，以生成一组威胁。对策以可操作任务的形式提供给开发人员。

6.  **攻击树建模–**
    像 SecurITree、AttackTree+这样的商业工具和像 ADTool、Ent、SeaMonster 这样的开源工具被用来建模攻击树。

7.  **CVSS 3.0–**
    CVSS 目前处于 3.0 版本。它用于 CVSS 模型。除此之外，可以在线分析为不同硬件和软件确定的漏洞的 CVV 分数，因为它有助于识别可能危害系统的潜在威胁。

8.  **提拉米苏–**
    该工具用于 T-MAP 方法。它用于计算所有攻击路径的列表，并根据攻击路径的总权重产生总体威胁。

**如何创建威胁模型:**
所有威胁建模过程都从创建正在分析的应用程序或系统的可视化表示开始。有两种方法可以创建视觉表示:

1.  **Visual Representation using Data Flow Diagram –** 
    The Microsoft Methodology, PASTA, and Trike each develop a visual representation of the application infrastructure utilizing data flow diagrams (DFD). DFDs were developed in the 1970s as tools for system engineers to provide a high-level visualization of how an application works within a system to move, store, and manipulate data. The concept of trust boundaries was added in the early 2000s by Security professionals in an attempt to make them applicable for threat modelling. 

    DFD 用于识别广泛的类别，通常使用 STRIDE 威胁分类方案。通过这种方法确定的威胁清单是有限的，因此是建模的一个不良起点。基于 DFD 的方法使用三个主要步骤:

    1.  将系统视为对手
    2.  表征系统
    3.  确定威胁
    4.  DFD 没有准确地描述应用程序的设计和流程。
    5.  他们分析的是数据如何流动，而不是用户如何与系统交互。
    6.  基于 DFD 的威胁建模没有标准方法，因为不同的人会针对相同的场景或问题创建具有不同输出的威胁模型。

2.  **Visual Representation using Process Flow Diagram –** 
    To deal with the limitations of DFD based threat modelling Process Flow Diagrams were introduced in 2011 as a tool to allow Agile software development teams to create threat models based on the application design process. These were specifically designed to illustrate how the attacker thinks. 

    攻击者不分析数据流。相反，他们试图弄清楚如何通过基于 DFD 的威胁建模不支持的应用程序。
    他们的分析侧重于如何滥用普通用例来访问资产或其他目标。
    VAST 方法使用 PFD 对应用程序进行可视化表示。

    基于 PFD 的威胁模型从用户交互的角度来看待应用。以下是基于 PFD 的威胁建模步骤:

    1.  设计应用程序的用例
    2.  定义了个人在用例之间移动的通信协议
    3.  包括各种技术控制，如表单、cookies 等
    4.  基于 PFD 的威胁模型很容易理解，不需要任何安全专业知识。
    5.  创建流程图-展示个人如何通过应用程序。因此，从攻击者的角度理解应用程序很容易。