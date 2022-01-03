# SDN 控制器(Ryu 和 ODL)

> 原文:[https://www.geeksforgeeks.org/sdn-controllers-ryu-and-odl/](https://www.geeksforgeeks.org/sdn-controllers-ryu-and-odl/)

在我们深入了解 [SDN 控制器](https://www.geeksforgeeks.org/software-defined-networking-sdn-controller/)之前，让我们了解一下什么是 SDN 和 SDN 控制器。

**[【软件定义网络(SDN)](https://www.geeksforgeeks.org/software-defined-networking/) :**
它是网络领域最大的持续平台之一，使网络灵活敏捷。SDN 克服了传统网络的所有缺点。SDN 的主要目的是在控制器的帮助下控制网络。SDN 是网络的未来。随着存储和服务器的兴起，SDN 引入了一个新概念，称为“**网络功能虚拟化(NFV)** ”。

SDN 体系结构形成三个主要层，即:

1.  基础设施层
2.  控制层
3.  应用层

我们一个一个来讨论。
**基础设施层:**
基础设施层由交换机、路由器等网络设备组成，也称为数据层。

**控制层:**
控制层由控制器组成，在控制器的帮助下控制数据包的流入和流出。让我们详细了解一下不同的控制器。

**应用层:**
应用层由监控、流量控制、网络分析和安全等网络应用组成。

**SDN 控制器:**
如前所述，控制器位于中间层。它们是许多 SDN 控制器，即:

1.  闵宽宏
2.  开放日
3.  Ryu 控制器

它是专为网络灵活性和管理更高流量速率而设计的 SDN 控制器之一。Ryu 包括定义良好的软件组件和应用编程接口。Ryu 让开发人员开发新的应用程序并管理各种其他网络设备。Ryu 控制器是用 Python 编写的。

快速启动龙控制器。在您的 Ubuntu 系统或预先安装了 SDN OVA 文件的 VMWare 工作站中运行以下所有命令。

```
// Python 
pip install ryu
```

要从 git 存储库中安装 Ryu，请执行以下命令。

```
git clone https://github.com / faucetsdn / ryu.git
cd ryu; pip install

```

**OpenDay Light (ODL)控制器:**
ODL 是最全能、最大的开源控制器之一。它有助于自动化更大的区域网络，并且是可扩展的。ODL 是用 Java 写的。与所有其他 SDN 控制器相比，该控制器是所有控制器中最好的，并且以其安全性而闻名。

以下是安装和运行控制器的命令。

```
// For Java
$wget https : // nexus.opendaylight.org/content/repositories/
opendaylight.release/org/opendaylight/integration/
opendaylight/0.12.1/
opendaylight-0.12.1.zip
              $unzip opendaylight
              - 0.12.1.zip $yum install java
              - 11 $export JAVA_HOME
    = / usr / lib / jvm / jre - 11 $cd / root / 
            opendaylight - 0.12.1 $./ bin / karaf

```