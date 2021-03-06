# 商业演绎数据库系统的应用

> 原文:[https://www . geesforgeks . org/applications-of-commercial-演绎-database-systems/](https://www.geeksforgeeks.org/applications-of-commercial-deductive-database-systems/)

一个**演绎数据库**是一种数据库类型，它可以使用存储在数据库中的一组定义良好的规则和事实来做出结论或者我们可以说推断。在我们处理大量数据的当今世界，这种演绎数据库提供了很多优势。它有助于将*关系数据库管理系统*与逻辑编程相结合。为了设计演绎数据库，使用了一种称为 Datalog 的纯声明性编程语言。

演绎数据库的实现可以在 LDL(逻辑数据语言)、NAIL(不是逻辑的另一种实现)、CORAL 和 VALIDITY 中看到。
LDL 和 validation 在各种商业/工业应用中的使用如下。

**1。低密度脂蛋白应用:**
该系统已应用于以下应用领域:

*   **企业建模:**
    与企业相关的数据可能会产生包含数百个实体和关系以及数千个属性的扩展 ER 模型。这个领域包括对企业内部的结构、流程和约束进行建模。
*   **假设检验或数据挖掘:**
    这个领域包括制定假设，翻译成低密度脂蛋白规则集和查询，然后对给定的数据执行查询以检验假设。这已被应用于微生物领域的基因组数据分析，其中数据挖掘包括从大肠杆菌实验的低水平数字化自动放射图中识别脱氧核糖核酸序列。
*   **软件重用:**
    应用程序的一小部分软件是基于规则的，并以 LDL 编码(批量是以标准过程代码开发的)。这些规则产生了一个知识库，其中包含*系统中使用的每个 C 模块的定义*和*一组定义模块导出/导入函数、约束等方式的规则。*“知识库”可用于做出与软件子集重用相关的决策。这正在银行软件中进行实验。

**2。有效性应用:**
有效性结合了演绎能力和操作复杂对象(oid、继承、方法等)的能力。它提供了一个称为 del(数据日志扩展语言)的 DOOD 数据模型和语言，一个沿着客户机-服务器模型工作的引擎，以及一组用于模式和规则编辑、验证和查询的工具。
以下是有效性系统的一些应用领域:

*   **电子商务:**
    在电子商务中，复杂的客户档案必须与目标描述相匹配。匹配过程也由规则描述，计算谓词处理数值计算。DEl 的声明性质使得匹配算法的制定变得容易。
*   **规则管理的流程:**
    在规则管理的流程中，定义良好的规则定义了要执行的操作。在这些过程中，一些类被建模为 DEL 类。有效性的主要优点是容易考虑新法规。
*   **知识发现:**
    知识发现的目标是通过分析已有数据发现新的数据关系。伊利诺伊大学开发的一个应用程序原型利用了已经存在的少数民族学生数据，这些数据通过 DEL 中的规则得到了增强。
*   **并行工程:**
    一个并行工程应用程序处理大量集中的数据，由几个参与者共享。在土木工程领域已经开发了一个应用原型。设计数据是使用 DEL 语言的面向对象能力建模的。DEL 能够处理规则到约束的转换，它也可以处理任何封闭的公式作为完整性约束。