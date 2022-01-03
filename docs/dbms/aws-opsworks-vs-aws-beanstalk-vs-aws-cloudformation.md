# AWS OpsWorks vs AWS 豆茎 vs AWS 云形成

> 原文:[https://www . geesforgeks . org/AWS-opsworks-vs-AWS-beanstalk-vs-AWS-cloud formation/](https://www.geeksforgeeks.org/aws-opsworks-vs-aws-beanstalk-vs-aws-cloudformation/)

**概述:**
AWS 列出了支持 [DevOps](https://www.geeksforgeeks.org/azure-devops-an-introduction/) 的广泛服务。无论是在集成、交付、战略、基础架构即代码方面。OpsWorks 属于配置管理服务，CloudFormation 有助于将基础设施作为代码进行维护，AWS Beanstalk 提供了简单的网络部署。让我们了解他们每个人。

[**AWS**T3**OpsWorks:**](https://www.geeksforgeeks.org/launching-an-ec2-instance-using-aws-cli/)

*   这项服务是 SSM 自动气象站的替代服务。
*   它提供 AWS 管理的厨师和木偶套件。
*   帮助管理应用程序配置和操作合规性管理等功能。
*   chef–自动完成多台服务器的配置、部署和管理任务。
*   puppet–它是跨各种服务器进行自动化和应用程序管理的又一个强大工具。
*   OpsWorks 还提供三种托管服务，分别是厨师自动化 OpsWorks、木偶企业 OpsWorks 和 Stacks OpsWorks。

**AWS 豆茎:**

*   这是一个平台即服务，旨在为开发人员提供网络部署解决方案。
*   它更像是以开发人员为中心的服务。
*   开发人员可以专注于应用程序，AWS Beanstalk 负责更高级别的资源，如 EC2 服务器、自动扩展组、RDS 数据库、带有 AWS ECS 的 Docker。
*   它只需要最少的配置，是扩展动态网站最简单的方法之一。

**AWS**T2**云**T5**阵型:**

*   AWS 云信息是企业实现卓越运营的一项伟大服务，是 AWS Well 架构框架的五大支柱之一。
*   它是一个低级服务，有助于不同 AWS 资源的建模和版本控制
*   这是一种基于模板的服务，因此侧重于将基础设施作为代码来维护
*   配置的模板支持资源建模，相同的资源可以轻松地跨服务器重复部署。
*   AWS CLOUDFORMATION 还支持 AWS BEANSTALK 资源和 AWS OPSWORKS 堆栈。

**参数对比:**

<figure class="table">

| 

参数

 | AWS op works | **AWS 豆茎** | **AWS** 云的形成 |
| --- | --- | --- | --- |
| 主要功能 | 托管厨师和木偶，提供简单的配置管理和自动化 | 支持简单的网络应用程序部署，自动扩展，兼容 Go、Java、。NET、Node.js、PHP、Python 和 Ruby | 将代码维护为模板，这些模板用于实现和配置服务/ AWS 资源 |
| 有效性 | 区域资源，目前存在于 9 个区域 | 区域资源 | 地区的 |
| 定价 | 厨师自动化的 AWS 操作说明–价格是根据服务器连接的节点数量、这些运行节点的持续时间以及创建的资源来计算的。木偶企业的 AWS 操作说明–连接到木偶主机和底层 EC2 实例的多个节点的成本AWS 操作工作栈–AWS 对创建的底层资源收费(EC2、自动扩展组、RDS 等) | 没有最低费用，您为创建的底层资源付费。这些资源将用于存储数据、服务器、自动扩展组和运行状况监控。 | 如果 AWS 是第三方资源提供者(不是 AWS::*、Alexa::*、或 Custom::*)，AWS 将按处理者(动作列表)收费。除此之外，您还需要为 EC2、ELB 等创建的底层资源付费。 |
| 它是混合服务吗？ | 是的，让您可以管理内部部署和云应用程序 | 不是混合动力 | 不适合内部数据中心编排。 |

</figure>