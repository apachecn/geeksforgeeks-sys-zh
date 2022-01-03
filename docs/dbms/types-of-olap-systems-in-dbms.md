# 数据库管理系统中 OLAP 系统的类型

> 原文:[https://www . geeksforgeeks . org/type-of-OLAP-system-in-DBMS/](https://www.geeksforgeeks.org/types-of-olap-systems-in-dbms/)

OLAP 服务器主要有以下三种类型:

1.  **Relational OLAP (ROLAP) – Star Schema based –** 
    The ROLAP is based on the premise that data need not to be stored multidimensionally in order to viewed multidimensionally, and that it is possible to exploit the well-proven relational database technology to handle multidimensionality of data.In ROLAP data is stored in a relational database.In essence, each action of slicing and dicing is equivalent to adding a “WHERE” clause in SQL statement. ROLAP can handle large amounts of data. ROLAP can leverage functionalities inherent in the relational database. 
2.  **Multidimensional OLAP (MOLAP) – Cube based –** 
    MOLAP stores data on disks in a specialized multidimensional array structure. OLAP is performed on it relying on the random access capability of the arrays. Arrays element are determined by dimension instances, and the fact data or measured value associated with each cell is usually stored in the corresponding array element. In MOLAP, the multidimensional array is usually stored in a linear allocation according to nested traversal of the axes in some predetermined order. 

    但是与 ROLAP 不同，ROLAP 只存储具有非零事实的记录，所有数组元素都在 MOLAP 中定义，因此，数组通常倾向于稀疏，空元素占据了大部分。由于存储和检索成本在评估在线性能效率时都很重要，MOLAP 系统通常包括高级索引和哈希等配置，以便在执行查询以处理稀疏数组时定位数据。MOLAP 立方体是快速的数据检索，最适合切片和切割，它们可以执行复杂的计算。所有计算都是在创建多维数据集时预先生成的。

3.  **Hybrid OLAP (HOLAP) –** 
    HOLAP is a combination of ROLAP and MOLAP. HOLAP servers allows storing the large data volumes of detail data.On the one hand, HOLAP leverages the greater scalability of ROLAP. On the other hand, HOLAP leverages the cube technology for faster performance and for summary-type information. Cubes are smaller than MOLAP since detail data is kept in the relational database. The database are used to stores data in the most functional way possible. 

**一些其他类型的 OLAP:**

1.  **Web OLAP (WOLAP) –** 
    It is a Web browser based technology.In traditional OLAP application is accessible by the client/server but in this OLAP application is accessible by the web browser. It is a three tier architecture which consist of client, middleware and database server. The most appealing features of this style of OLAP was (past tense intended, since few products categorize themselves this way) the considerably lower investment involved on the client side (“all that’s needed is a browser”) and enhanced accessibility to connect to the data. A Web based application requires no deployment on the client machine. All that is required is a Web browser and a network connection to the intranet or Internet. 
2.  **Desktop OLAP (DOLAP) –** 
    DOLAP stands for desktop analytical processing.In that user can download the data from the source and work with the dataset, or on their desktop. Functionality is limited compare to other OLAP application. It has cheaper cost. 
3.  **Mobile OLAP (MOLAP) –** 
    MOLAP is wireless functionality or mobile devices. User is work and access the data through the mobile devices. 
4.  **空间 OLAP(SOLAP)–**
    将地理信息系统(GIS)和 OLAP 的功能合并到单一用户界面 SOLAP 出口中。创建 SOLAP 是因为数据以字母数字、图像和向量的形式出现。这提供了对驻留在空间数据库上的数据的简单而快速的探索。

参见–[OLAP vs OLTP](https://www.geeksforgeeks.org/dbms-olap-vs-oltp/)T2】