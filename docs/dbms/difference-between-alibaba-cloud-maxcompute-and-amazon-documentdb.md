# 阿里巴巴云 MaxCompute 和亚马逊 DocumentDB 的区别

> 原文:[https://www . geesforgeks . org/difference-Alibaba-cloud-maxcompute-and-Amazon-document db/](https://www.geeksforgeeks.org/difference-between-alibaba-cloud-maxcompute-and-amazon-documentdb/)

**1。【阿里巴巴云 MaxCompute:**
MaxCompute 原名 ODPS，是一个面向大规模数据仓储的通用、全托管、多租户数据处理平台。它用于存储和计算成批的结构化数据。它包含非常广泛的数据仓库解决方案。它还提供非常大的数据分析和建模服务。

**2。Amazon document db:**
Amazon document db 是一个商业许可的数据库，它具有以下特性，因为它是一个支持 MongoDB 工作负载的快速、可扩展、高可用性和完全托管的文档数据库服务。它目前在 AWS 的加利福尼亚、俄勒冈、北弗吉尼亚和爱尔兰地区提供。它通过模拟响应来实现 Apache 2.0 开源 MongoDB 3.6 应用编程接口。

**阿里巴巴云 MaxCompute 与亚马逊 DocumentDB 的区别:**

<center>

| 没有 | 阿里巴巴云 MaxCompute | Amazon DocumentDB |
| --- | --- | --- |
| 1. | 由阿里巴巴于 2016 年开发。 | 由亚马逊于 2019 年开发。 |
| 2. | 它是一个通用的、完全管理的、多租户的数据处理平台，用于大规模数据仓库。 | 它是一个快速、可扩展、高可用性和完全管理的 MongoDB 兼容的数据库服务 |
| 3. | 阿里巴巴云 MaxCompute 的许可证是商用的。 | 亚马逊文档数据库的许可证是商业的。 |
| 4. | 在阿里巴巴云 MaxCompute 中，托管服务器操作系统。 | 在亚马逊文档数据库中，托管服务器操作系统 |
| 5. | 它的主要数据库模型是关系数据库管理系统。 | 它的主要数据库模型是文档存储。 |
| 6. | 它支持基于服务器端脚本的用户定义函数。 | 它不支持服务器端脚本。 |
| 7. | 只有一种分区方法——分片。 | 它不支持分区方法。 |
| 8. | 它支持类似 SQL 的查询语言。 | 它不支持 SQL 查询语言。 |
| 9. | 它支持复制方法。 | 它支持高可用性多可用性区域 |
| 10. | 它没有提供参照完整性的概念。因此，没有外键。 | 它没有提供参照完整性的概念。因此，没有外键。但是可以通过亚马逊弹性地图缩减来实现。 |
| 11. | 它为用户定义的映射/缩减方法提供了一个应用编程接口 | 它没有为用户定义的映射/缩减方法提供应用编程接口 |
| 12. | 它确实支持 ACID 属性。 | 它支持原子单文档操作。 |
| 13.  | 支持的编程语言是 Java | 支持的编程语言有 Go、Java、JavaScript、PHP 和 Python。 |

</center>