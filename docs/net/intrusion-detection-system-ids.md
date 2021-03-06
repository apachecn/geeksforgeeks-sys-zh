# 入侵检测系统(IDS)

> 原文:[https://www . geesforgeks . org/入侵检测-系统-ids/](https://www.geeksforgeeks.org/intrusion-detection-system-ids/)

入侵检测系统(IDS) 是一个监控**网络流量**的可疑活动并在发现此类活动时发出警报的系统。它是一种软件应用程序，用于扫描网络或系统中的有害活动或违反策略的行为。任何恶意冒险或违规行为通常都会向管理员报告，或者使用安全信息和事件管理(SIEM)系统集中收集。SIEM 系统集成了来自多个来源的输出，并使用警报过滤技术来区分恶意活动和虚假警报。

尽管入侵检测系统监控网络中潜在的恶意活动，但它们也容易发出假警报。因此，组织需要在首次安装入侵检测系统产品时对其进行微调。这意味着正确设置入侵检测系统，以识别网络上的正常流量与恶意活动相比是什么样子。

入侵防御系统还监控进入系统的网络数据包，以检查其中涉及的恶意活动，并立即发送警告通知。

**入侵检测系统分类:**
入侵检测系统分为 5 种类型:

1.  **网络入侵检测系统(NIDS):**
    网络入侵检测系统(NIDS)设置在网络内的计划点，用于检查来自网络上所有设备的流量。它会观察整个子网中通过的流量，并将子网中通过的流量与已知攻击的集合进行匹配。一旦发现攻击或观察到异常行为，就可以向管理员发送警报。NIDS 的一个例子是将它安装在防火墙所在的子网中，以便查看是否有人试图破解防火墙。
2.  **主机入侵检测系统(HIDS):**
    主机入侵检测系统(HIDS)在网络上独立的主机或设备上运行。HIDS 只监控来自设备的传入和传出数据包，如果检测到可疑或恶意活动，将向管理员发出警报。它会拍摄现有系统文件的快照，并将其与以前的快照进行比较。如果分析系统文件被编辑或删除，将向管理员发送警报进行调查。在任务关键型机器上可以看到使用 HIDS 的例子，这些机器预计不会改变布局。
3.  **基于协议的入侵检测系统(PIDS):**
    基于协议的入侵检测系统(PIDS)由一个系统或代理组成，该系统或代理始终驻留在服务器的前端，控制和解释用户/设备和服务器之间的协议。它试图通过定期监控 HTTPS 协议流并接受相关的 HTTP 协议来保护 web 服务器。由于 HTTPS 是未加密的，在立即进入其网络表示层之前，该系统需要驻留在这个接口中，以便使用 HTTPS。
4.  **基于应用协议的入侵检测系统(APIDS):**
    基于应用协议的入侵检测系统(APIDS)是通常驻留在一组服务器内的系统或代理。它通过监控和解释应用程序特定协议上的通信来识别入侵。例如，当中间件与 web 服务器中的数据库进行交易时，这将监视对中间件显式的 SQL 协议。
5.  **混合入侵检测系统:**
    混合入侵检测系统是由入侵检测系统的两种或多种方法组合而成。在混合入侵检测系统中，主机代理或系统数据与网络信息相结合，形成网络系统的完整视图。与其他入侵检测系统相比，混合入侵检测系统更有效。Prelude 是混合入侵检测系统的一个例子。

**入侵检测系统的检测方法:**

1.  **Signature-based Method:**
    Signature-based IDS detects the attacks on the basis of the specific patterns such as number of bytes or number of 1’s or number of 0’s in the network traffic. It also detects on the basis of the already known malicious instruction sequence that is used by the malware. The detected patterns in the IDS are known as signatures.

    基于签名的入侵检测系统可以很容易地检测到系统中已经存在模式(签名)的攻击，但是由于模式(签名)未知，很难检测到新的恶意攻击。

2.  **基于异常的方法:**
    随着新恶意软件的快速发展，引入了基于异常的 IDS 来检测未知的恶意软件攻击。在基于异常的入侵检测系统中，使用机器学习来创建一个可信的活动模型，任何出现的东西都会与该模型进行比较，如果在模型中没有发现，就会被宣布为可疑。与基于签名的入侵检测系统相比，基于机器学习的方法具有更好的通用性，因为这些模型可以根据应用和硬件配置进行训练。

**入侵检测系统与防火墙的比较:**
入侵检测系统和防火墙都与网络安全有关，但入侵检测系统不同于防火墙，因为防火墙会向外寻找入侵，以阻止入侵的发生。防火墙限制网络之间的访问，以防止入侵，如果攻击来自网络内部，它不会发出信号。入侵检测系统描述了一个可疑的入侵一旦发生，然后发出警报。