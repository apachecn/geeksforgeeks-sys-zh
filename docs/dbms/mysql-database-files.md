# MySQL |数据库文件

> 原文:[https://www.geeksforgeeks.org/mysql-database-files/](https://www.geeksforgeeks.org/mysql-database-files/)

每当 MySQL 数据库安装完成时，所有与数据库相关的数据和元数据都存储在一个文件夹中。这是实际的数据库模式，其中包含一些值。让我们对此进行更多的探索。

文件扩展名如下:

*   **。frm**–这是包含表的模式或定义的文件的扩展名。
*   **。myd**–这是包含 MyISAM 表数据的文件的扩展名。
*   **。myi**–这是包含 MyISAM 表索引的文件的扩展名。

在**MySQL Server 5.5/data/MySQL**文件夹里面，有些文件是 ***。frm** 、 ***。MYD** ，和 ***。MYI** 、
其中星号是实际的表名。如果使用 MyISAM 引擎，数据文件夹会包含上述所有文件，否则在 InnoDB 的情况下，文件夹包含**。frm** 文件。

这些数据库文件用于备份目的，以保护数据库的某些迁移或升级的模式、数据和索引。Windows 和 Linux 的 MySQL 的配置文件分别是 **my.ini** 和 **my.conf** 。

窗口的路径:

```
C:\Program Files\MySQL\MySQL Server 5.5\my.ini 
```

在 **my.ini** 文件中，如果我们搜索关键字 **basedir** ，就可以得到 MySQL 服务器安装的路径。

同理，如果我们搜索关键字 **datadir** ，就可以得到数据库根目录的路径。除此之外，MySQL 服务器还创建或使用许多其他文件来执行各种活动。其中一些如下

*   **my.cnf** :
    Its a MySQL database configuration file. This is the main configuration file of MySQL server.
    This is found in the root directory where the installation is done. In this file, the user can find the location of data folder.
    The default location of the configuration file is ‘**/etc/my.cnf**‘
    Other file formats which are compatible with MySQL are .ibc, .tmd, .rul, .cnf, .ddl, .ibd, .mysql, .sql, .opt.
    Depending on the table type, tables are stored in files with these extensions.
*   **db.opt** :
    Whenever database is created or changed using MySQL commands, the characteristics of database are stored in text file namely **db.opt** file .
*   **.ibd** :
    These are the files with extensions ***.ibd** which stores the data and index of MySQL InnoDB tables. This type of file is created or used by MySQL InnoDB software and associated with it .
*   **.sock** :
    All the MySQL database connections are managed by a special file called the socket file. This socket file namely mysqld.sock is created by MySQL service automatically which helps in communicating between different processes.
*   **Pid file** :
    The process id of MySQL server is written in such file. The default will be hostname of the MySQL server.

*   **.db** :
    These are the files with extensions ‘ **.db** ‘ which stores the data and indexes of BerkeleyDB storage engine.
*   **error log** :
    The error log file really plays an important role during troubleshooting of application. These are MySQL error log files which will give the exact reason or information for MySQL failure in the server. This effectively helps in the debug process for any error issue raised in MySQL server. By default it will log errors in **hostname.err** file.
*   **Slow Query Log** :
    Slow query log file have all the ‘ *slow* ‘ SQL queries. The performance of the application goes down because of the MySQL queries taking more time to complete than the expected result. So this helps in monitoring the slow queries which helps in improving the queries for higher performance.
*   **general query log** :
    General query log file gives all the general details like server start or end timimgs, up or down details, connect or disconnect details etc. It is enabled by log[=filename]. By default, MySQL will create **hostname.log** for the entries .
*   **binary log files** :
    The binary log files contains detail information related to any table creation or data modifications made to MySQL server. This also have informations regarding the time taken by MySQL statement, state of the server, error codes, metadata for maintenance of log file. This is enabled by -log-bin[=basename] option. By default, its hostname of the server.
*   **.index** :
    To monitor which binary log files are used, a binary log index file is created which contains the names of all binary log files. It is enabled by –log-bin-index[=filename] else basename will be the binary log file with the extension .index. By default, relay log index file name is host_name-relay-bin.index .
*   **.TMD** :
    These are the intermediate database file created by MySQL server created during repair operations. This file contains information regarding database recoveries. These files are also be created by some other MySQL database operations.
*   **TRG and TRN Files** :
    TRG files are trigger parameter files and TRN files are trigger namespace files. In MySQL server, whenever triggers are defined, the definitions are stored in text files namely
    **tablename.TRG** file. It contains triggers for multiple events like BEFORE or AFTER of INSERT, UPDATE or DELETE operations in MySQL.
*   **.ARZ, .ARM and .ARN files** :
    The table data and table metadata files have extensions of **.ARZ** and **.ARM** respectively. An **.ARN** file is the optimization file during optimization process. The files are related to Archive Storage Engine.
*   **。ARZ** :
    ARZ 文件是归档表的元数据文件。具有此扩展名的文件存储表的数据。这些文件包含在由 MySQL 的 **mysqlbackup** 命令创建的备份中。