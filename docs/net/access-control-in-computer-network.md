# 计算机网络中的访问控制

> 原文:[https://www . geesforgeks . org/计算机网络访问控制/](https://www.geeksforgeeks.org/access-control-in-computer-network/)

**访问控制**是一种限制对系统或物理或虚拟资源的访问的方法。这是一个用户可以访问系统、资源或信息并被授予某些特权的过程。访问控制是一种安全技术，可以控制谁可以查看不同的方面、可以查看什么以及谁可以使用计算环境中的资源。这是安全领域的一个基本概念，可以降低企业或组织的风险。

为了建立一个安全的系统，使用了电子访问控制系统，该系统依赖于用户证书、访问读卡器、审计和报告来跟踪员工对受限业务地点和区域的访问。这些系统包括访问控制面板，以禁止进入敏感区域，如警报和锁定区域，以防止未经授权的访问或操作。

访问控制系统通过评估所需的登录凭证来执行用户和实体的识别、认证和授权，登录凭证可能包括密码、pin、生物计量扫描或其他认证因素。存在需要两个或更多认证因素的多因素认证，这通常是保护访问控制系统的分层防御的重要部分。

**认证因素:**

*   密码或个人识别码
*   生物计量测量(指纹和视网膜扫描)
*   卡片还是钥匙

根据法规遵从性要求和要保护的信息技术的安全级别，使用不同的访问控制模型。基本上访问控制有两种类型:

1.  **物理访问控制:**
    物理访问控制限制进入校园、建筑物、房间和物理 IT 资产。

2.  **逻辑访问控制:**
    逻辑访问控制限制与计算机网络、系统文件和数据的连接。

**门禁模型:**

1.  **Attribute-based Access Control (ABAC):** 
    In this model, access is granted or declined by evaluating a set of rules, policies, and relationships using the attributes of users, systems and environmental conditions. 
2.  **Discretionary Access Control (DAC):** 
    In DAC, the owner of data determines who can access specific resources. 
3.  **History-Based Access Control (HBAC):** 
    Access is granted or declined by evaluating the history of activities of the inquiring party that includes behavior, the time between requests and content of requests. 
4.  **Identity-Based Access Control (IBAC):** 
    By using this model network administrators can more effectively manage activity and access based on individual requirements. 
5.  **Mandatory Access Control (MAC):** 
    A control model in which access rights are regulated by a central authority based on multiple levels of security. Security Enhanced Linux is implemented using MAC on the Linux operating system. 
6.  **Organization-Based Access control (OrBAC):** 
    This model allows the policy designer to define a security policy independently of the implementation. 
7.  **Role-Based Access Control (RBAC):** 
    RBAC allows access based on the job title. RBAC eliminates discretion on a large scale when providing access to objects. For example, there should not be permissions for human resources specialist to create network accounts. 
8.  **Rule-Based Access Control (RAC):** 
    RAC method is largely context based. Example of this would be only allowing students to use the labs during a certain time of day.