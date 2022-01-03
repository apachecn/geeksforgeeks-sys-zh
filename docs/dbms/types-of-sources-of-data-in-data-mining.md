# 数据挖掘中数据源的类型

> 原文:[https://www . geesforgeks . org/数据挖掘中的数据来源类型/](https://www.geeksforgeeks.org/types-of-sources-of-data-in-data-mining/)

在这篇文章中，我们将讨论在数据挖掘过程中使用的不同数据源。来自多个来源的数据被集成到一个名为**数据仓库**的公共来源中。

**我们来讨论一下可以挖掘什么类型的数据:**

*   **平面文件***   **关系数据库***   **数据仓库***   **事务数据库***   **多媒体数据库***   **空间数据库***   **时间序列数据库***   **World Wide Web(WWW)

    1.  ***Flat file***
        *   A flat file is defined as a data file in the form of text or binary, and its structure can be easily extracted by data mining algorithm.
        *   The data stored in the flat file has no relationship or path between them, just like if a relational database is stored in the flat file, there will be no relationship between tables.
        *   Flat files are represented by a data dictionary. Example: CSV file.
        *   **Application** : It is used for data storage in data warehouse and data transmission between servers.
    2.  ***[relational database]***
        *   A [relational database](https://www.geeksforgeeks.org/relational-model/) is defined as a data set organized in a table with rows and columns.
        *   The physical schema in the relational database is the schema that defines the table structure.
        *   The logical schema in relational database is the schema that defines the relationship between tables.
        *   The standard API of relational database is [SQL](https://www.geeksforgeeks.org/sql-tutorial/) .
        *   **Application** : Data mining, ROLAP model, etc.
    3.  ***【 data warehouse 】***
        *   A data warehouse is defined as a collection of data integrated from multiple sources for query and decision-making.
        *   There are three types of data warehouses: T0 enterprise T1 data warehouse, T2 data mart T3 and T4 virtual T5 warehouse.
        *   There are two ways to update data in the data warehouse: T0, query-driven T1 and T2, update-driven T3.
        *   **Application** : Business decision, data mining, etc.
    4.  ***Transaction database***
        *   A transaction database is a data collection organized by time stamps, dates, etc., which is used to represent transactions in the database.
        *   This type of database can roll back or undo its operation when the transaction is incomplete or uncommitted.
        *   Highly flexible system, users can modify information without changing any sensitive information.
        *   Comply with [acidity](https://www.geeksforgeeks.org/acid-properties-in-dbms/) of database management system.
        *   **Application** : bank, distributed system, object database, etc.
    5.  ***Multimedia database***
        *   The multimedia database consists of audio, video, image and text media.
        *   They can be stored in an object-oriented database.
        *   They are used to store complex information in a pre-specified format.
        *   **Application** : digital library, video on demand, news on demand, music database, etc.
    6.  ***Spatial database***
        *   Store geographic information.
        *   Store data in the form of coordinates, topology, line, polygon, etc.
        *   **Application** : map, global positioning, etc.
    7.  ***Time series database***
        *   The time series database contains stock trading data and activities recorded by users.
        *   Handle an array of numbers indexed by time, date, etc.
        *   Real-time analysis is required.
        *   **Application field** : Extreme value, graphite, Infusi database, etc.
    8.  ***WWW***
        *   WWW refers to the collection of documents and resources, such as audio, video, text, etc., which are identified by the Uniform Resource Locator (URL) through a web browser, linked by HTML pages and accessible through the Internet network.
        *   It is the most heterogeneous repository because it collects data from multiple resources.
        *   With the increasing and changing amount of data, it is dynamic in nature.
        *   **Application** : Online shopping, job hunting, research, study, etc.**