# 信息安全风险管理| Set-2

> 原文:[https://www . geesforgeks . org/risk-management-for-information-security-set-2/](https://www.geeksforgeeks.org/risk-management-for-information-security-set-2/)

先决条件–[风险管理|集合-1](https://www.geeksforgeeks.org/risk-management-set-1/)
**2。风险评估–**
风险管理是一项经常性活动，另一方面，风险评估在离散点执行，直到下一次评估完成。风险评估是评估已知和假设的威胁和漏洞以确定预期损失的过程。它还包括确定系统运行的可接受程度。

风险评估从上下文建立阶段接收输入和输出，输出是评估的风险列表，其中风险根据风险评估标准被赋予优先级。

1.  **Risk Identification –**
    In this step we identify the following:
    *   资产
    *   威胁
    *   现有和计划的安全措施
    *   脆弱点
    *   结果
    *   相关业务流程

    因此，输出包括以下内容:

    *   资产和相关业务流程列表，以及相关威胁、现有和计划的安全措施列表
    *   与任何已识别威胁无关的漏洞列表
    *   事故场景及其后果列表
2.  **Risk Estimation –**
    There are 2 methods for Risk Assessment:

    **1。定量风险评估–**除了金融机构和保险公司之外，该方法主要不被组织使用。定量风险在数学上表示为年化预期损失。ALE 是由于一年期内实现的风险而导致的资产预期货币损失。

    ```
    ALE= SLE * ARO
    ```

    单次损失预期是资产单次损失的价值。这可能是也可能不是全部资产。这就是亏损的影响。年化发生率(ARO)是损失发生的频率。这是可能的。

    理论上，定量风险评估看似简单，但在给参数赋值时存在问题。虽然系统成本很容易定义，但间接成本，如信息价值、损失的生产活动和回收成本，很难准确定义。另一个因素的可能性并不准确。

    因此，定量风险评估存在很大的误差幅度。由于缺乏准确完整的信息，对信息技术系统进行定量风险评估不符合成本效益。

    **2。定性风险评估–**定性风险评估以主观的方式定义可能性、影响值和风险，记住可能性和影响值是高度不确定的。定性风险评估通常给出“高”、“中”和“低”的风险结果。以下是定性风险评估的步骤:

    1.  **Identifying Threats:** Threats and Threat-Sources must be identified. Threats should include threat-source to ensure accurate estimation. It is important to compile a list of all possible threats that are present across the organization and use this list as the basis for all risk management activities. Some of the examples of threat and threat-source are:
        *   自然威胁——洪水、地震等。
        *   人类威胁——病毒、蠕虫等。
        *   环境威胁-停电、污染等。
    2.  **Identifying Vulnerabilities:** Vulnerabilities are identified by numerous means. Some of the tools are:
        1.  漏洞扫描程序–这是一种软件，它将操作系统或代码的缺陷与缺陷签名数据库进行比较。
        2.  渗透测试–人类安全分析师将针对系统实施威胁，包括操作漏洞，如社会工程。
        3.  运营和管理控制审计–通过将当前文档与最佳实践(例如 ISO 17799)进行比较，以及将实际实践与当前文档化流程进行比较，来审查运营和管理控制。
    3.  **将威胁与漏洞联系起来:**这是风险评估中最困难和强制性的活动。T-V 配对列表是通过审查漏洞列表并将漏洞与每个适用的威胁配对，然后审查威胁列表并确保该威胁-操作/威胁可以针对的所有漏洞都已被识别来建立的。
    4.  **Defining Likelihood:** Likelihood is the probability that a threat caused by a threat-source will occur against a vulnerability. Sample Likelihood definitions can be like:

        一年内成功实施威胁的概率低-0-30%
        一年内成功实施威胁的概率中等-31-70%
        一年内成功实施威胁的概率高-71-100%

        这只是一个示例定义。组织可以使用自己的定义，如非常低、低、中、高、非常高。

    5.  **Defining Impact:** Impact is best defined in terms of impact upon confidentiality, integrity and availability. Sample definitions for impact are as follows:

        |  | 机密 | 完整 | 有效性 |
        | --- | --- | --- | --- |
        | 低的 | 失去保密性导致**对组织的影响有限** | 诚信缺失导致**对组织的影响有限** | 可用性丧失导致**对组织的影响有限** |
        | 中等 | 失密导致**对组织的严重影响** | 诚信缺失导致**对组织的严重影响** | 可用性丧失导致**对组织的严重影响** |
        | 高的 | 失密导致**对组织的严重影响** | 诚信缺失导致**对组织的严重影响** | 可用性丧失导致**对组织的严重影响** |

        组织效应的例子如下:

        | 效果类型 | 对任务能力的影响 | 财务损失 | 对人类生活的影响 |
        | --- | --- | --- | --- |
        | 有限效应 | 暂时丧失一项或多项次要任务能力 | 50 000 卢比以下 | 轻微伤害 |
        | 严重影响 | 一项或多项次要能力的长期损失或一项或多项主要任务能力的暂时损失。 | 50，000 卢比-1，00，000 卢比 | 重大危害 |
        | 严重影响 | 一个或多个主要任务能力的长期损失 | 超过 100，000 卢比 | 被处死 |

    6.  **评估风险:**评估风险是确定针对漏洞实施威胁的可能性以及成功妥协所产生的影响的过程。样本风险判定矩阵如下:
        T22】高的 T42】温和的

        |  | 影响 |
        | 高的 | 温和的 | 低的 |
        | 可能性 | 高的 | 高的 | 温和的 |
        | 温和的 | 高的 | 温和的 | 低的 |
        | 低的 | 低的 | 低的 |

**3。风险评估–**风险评估流程接收风险分析流程的输出作为输入。它首先将每个风险级别与风险接受标准进行比较，然后根据风险治疗指征对风险列表进行优先级排序。

**3。风险缓解/管理–**
风险缓解包括对风险评估流程中建议的适当的风险降低控制措施进行优先排序、评估和实施。由于消除组织中的所有风险几乎是不可能的，因此高级管理层、职能和业务经理有责任使用成本最低的方法并实施最适当的控制措施，将风险降低到可接受的水平。

根据 NIST 标准普尔 800 30 框架，风险缓解有 6 个步骤。

1.  **风险假设:**这意味着接受风险并继续运行系统，但同时尝试实施控制以
2.  **风险规避:**这意味着消除风险原因或后果，以避免风险，例如，如果识别出风险，则关闭系统。
3.  **风险限制:**通过实施控制措施，将威胁利用漏洞的不利影响降至最低，从而限制风险(例如，使用支持、预防、检测控制措施)
4.  **风险规划:**通过制定风险缓解计划来管理风险，该计划优先考虑、实施并保持控制
5.  **研究和确认:**这一步包括确认漏洞或缺陷，并研究纠正漏洞的控制措施。
6.  **风险转移:**这意味着转移风险以补偿损失，例如，在所有情况下购买保险担保不是 100%，而是从损失中获得一些补偿。

**4。风险沟通–**
这一步的主要目的是向组织的所有利益相关者进行沟通，让他们了解风险的各个方面。建立共识很重要，因为它会影响要做出的决定。

**5。风险监控和审查–**
定期审查安全措施，以确保它们按计划工作，并且环境的变化不会使它们无效。随着工作环境的重大变化，安全措施也应该更新。业务需求、漏洞和威胁会随着时间的推移而变化。应安排定期审计，并应由独立的一方进行。

**6。信息技术评估和评估–**
应验证安全控制。技术控制是需要测试和验证的系统。漏洞评估和渗透测试用于验证安全控制的状态。根据安全监控策略、事件响应计划以及安全验证和度量来监控系统事件是确保获得最佳安全级别的基本活动。对新漏洞进行检查并应用程序和技术控制(例如定期更新软件)非常重要。