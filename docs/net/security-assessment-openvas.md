# 安全评估:OpenVAS

> 原文:[https://www.geeksforgeeks.org/security-assessment-openvas/](https://www.geeksforgeeks.org/security-assessment-openvas/)

在本文中，我们将讨论开放式[漏洞评估](https://www.geeksforgeeks.org/vulnerabilities-in-information-security/)系统(开放式 VAS)的概述，还将介绍其工作原理和特点，最后以开放式 VAS 体系结构的类别结束。我们一个一个来讨论。

**概述:**
开放[漏洞评估](https://www.geeksforgeeks.org/vulnerabilities-in-information-security/)系统(OpenVAS)是提供漏洞评估各种服务和工具的免费软件。漏洞是指系统中的弱点或缺陷。如果系统易受攻击，它可能会面临用户身份和数据的威胁。评估系统的脆弱性总是明智的。漏洞评估是一个过程，可以识别、列举和排列系统或网络中存在的漏洞，以便修补它们。基本上，它关注的是系统资源的安全性。

**漏洞评估工具的工作原理:**
漏洞评估工具的工作原理如下。

1.  对系统资源进行分类。
2.  将可枚举值分配给分类资源。
3.  检测每个资源中可能存在的威胁(漏洞)。
4.  优先消除漏洞。

**特征:**

*   它允许攻击者造成不良操作或获得未经授权的访问。
*   开放增值服务是一个在通用公共许可证下许可的框架。
*   它基于客户机-服务器体系结构，该体系结构基于开放增值服务传输协议(OTP)、开放增值服务管理协议(OMP)和开放增值服务管理协议(OAP)工作。

**开放 VAS 架构的类别:**
开放 VAS 架构有以下几类。

*   **客户端–**
    开放 VAS CLI 和绿骨安全助手(GSA)是客户端可用的接口。|

*   **服务–**
    开放 VAS 扫描器和开放 VAS 管理器是实际执行扫描网络上主机进行网络漏洞测试(NVTs)任务的服务。

*   **数据–**
    NVTs 结果和配置是扫描主机过程中使用的数据。