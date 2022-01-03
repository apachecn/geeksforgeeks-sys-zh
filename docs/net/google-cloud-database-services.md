# 谷歌云数据库服务

> 原文:[https://www . geesforgeks . org/Google-cloud-database-services/](https://www.geeksforgeeks.org/google-cloud-database-services/)

在设计应用程序时，存储是我们选择的首要因素。每个应用程序都需要一个可靠的存储结构来保证软件的正常运行。数据的多样性可以是流式传输或存储账户相关数据。有一点龙猫有 2600 多 CP，他们需要管理。

根据应用程序将要处理的内容，数据存储的类型可能会有所不同。谷歌提供了各种选项来存储、分析和处理这些数据。我们知道谷歌云以前有持久磁盘来存储大量数据，但为了满足客户的新需求，他们在云基础设施中加入了一些核心存储选项。

让我带您了解他们提供的选项，您可以从下面选择满足您应用需求的选项–

1.  **云存储:**
    谷歌存储是谷歌提供的一项服务，用于将数据对象存储到谷歌云中。数据对象可以被称为不可变的实体，它由任何文件的数据组成，与格式无关。它最适合包含结构化数据对象的应用程序，例如大型媒体文件和图像。也支持用于备份的非结构化类型数据对象。

*   **云扳手:**
    谷歌扳手是同类数据存储选项中的第一款，支持非关系水平尺度的关系数据库结构。它具有高度的可扩展性，支持一致的 SQL，并且可以高速使用。它最适合拥有大型数据库的应用程序，例如电子商务、贸易等。*   **云 SQL :**
    云 SQL 是谷歌云提供的捆绑服务。这支持用于 [MySQL](https://www.geeksforgeeks.org/mysql-common-mysql-queries/) 、SQL Server 和 PostgreSQL 的关系数据库服务。这用于存储客户的凭证和客户下的订单。*   **谷歌大表:**
    谷歌大表是谷歌的大数据服务。它用于许多已知的谷歌应用程序，如地图、搜索和 Gmail。它也用于分析工作和繁重的读写情况。*   **Cloud Data Store :**
    Google Datastore is the best suited for the applications where the data is structured and applications process that type of data.his data store is highly used by software developers who are intended to work with structured data.

    **服务差异:**

    <center>

    | 的基础 | 云数据存储 | 谷歌 Bigtable | 云存储 | 云 SQL | 云形扳手 |
    | --- | --- | --- | --- | --- | --- |
    | 类型 | 使用 NoSQL 文件 | NoSQL 宽柱 | blobstore(阻隔器) | 面向联机事务处理的关系数据库 | 面向联机事务处理的关系数据库 |
    | 交易支持 | 不 | 不 | 不 | 支持 | 支持 |
    | 支持复杂查询 | 不 | 不 | 不 | 是的，它支持 | 是的，它支持 |
    | 容量 | 超过万亿字节 | 超过千兆字节 | 超过千兆字节 | 万亿字节 | 千兆字节 |
    | 实体大小 | 1 兆字节/实体 | 10 兆字节/行 | 5tb/对象 | 由数据库引擎决定 | 10，240 MIb/行 |

    </center>