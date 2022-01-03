# WMI 完整版

> 原文:[https://www.geeksforgeeks.org/wmi-full-form/](https://www.geeksforgeeks.org/wmi-full-form/)

WMI 代表**视窗管理工具。**

**定义:** WMI 是微软提供的一套规范，用于从 Windows 计算系统整合网络中设备和应用程序的管理。WMI 是微软基于网络的企业管理的实现。

**WMI 的目的:**

WMI 的目的是定义一组独立于环境的规范，允许在相同的管理应用程序之间共享管理信息。

**优势:**

*   WMI can easily obtain the information of remote machines like the current machines.
*   Use WMI REAL restart time as an indicator of uptime.
*   Account settings automatically used by SAM.
*   WMI wraps the native API, so with the change of API call, unless WMI also changes, you will (probably) get benefits.

**缺点:**

*   Speed–Query data is slow, and if you try to use it during startup, it will delay your startup, because WMI service takes a long time to start.
*   Compared with SNMP, WMI is less efficient.
*   In the case of WMI, more firewall ports are needed.