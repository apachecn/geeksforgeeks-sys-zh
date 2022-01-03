# 在 Cassandra 中使用 CSV 文件插入数据

> 原文:[https://www . geesforgeks . org/insert-data-use-a-CSV-file-in-Cassandra/](https://www.geeksforgeeks.org/inserting-data-using-a-csv-file-in-cassandra/)

在本文中，我们将讨论如何使用 CSV 文件将数据插入到表中。我们还将借助示例介绍实现。我们一个一个来讨论。

先决条件–[卡珊德拉简介](https://www.geeksforgeeks.org/introduction-to-apache-cassandra/)

**简介:**
如果你想批量存储数据，那么从 CSV 文件中插入数据是不错的方法之一。如果文件中有数据，那么可以使用 Cassandra 中的 COPY 命令直接将数据插入数据库。当您有一个非常大的数据库，并且您想要快速存储数据，并且您的数据在 CSV 文件中时，这将非常有用，然后您可以直接插入您的数据。

**语法–**
您可以看到下面的 COPY 命令语法供您参考。

```
COPY table_name [( column_list )]
FROM 'file_name path'[, 'file2_name path', ...] | STDIN
[WITH option = 'value' [AND ...]]
```

现在，让我们为实现该方法创建示例数据。

**步骤-1 :**
**创建关键空间–数据**
在这里，您可以使用以下 cqlsh 命令创建关键空间，如下所示。

```
CREATE KEYSPACE data
 WITH REPLICATION = {  
  'class' : 'NetworkTopologyStrategy',  
  'datacenter1' : 1  
  } ;
```

**步骤-2 :**
**创建 Student_personal_data table–**
在这里，可以使用下面的 cqlsh 命令创建 Student _ personal _ data table，如下所示。

```
CREATE TABLE data.Student_personal_data (  
 S_id UUID PRIMARY KEY,  
S_firstname text,  
S_lastname text,    
);
```

**步骤 3 :**
**创建 csv 文件–**
将下面给定的表格视为 CSV 文件，即 personal_data.csv。但是，实际上您可以在 CSV 文件中插入数据并将其保存在计算机驱动器中。

<figure class="table">

| 赛德(UUID) | s _ 名字 | S_lastname |
| --- | --- | --- |
| -=伊甸园美剧 http://sfile . ydy . com =-荣誉出品本字幕仅供学习交流，严禁用于商业途径 | Ashish | 克里斯托弗 |
| -= ytet-伊甸园字幕组=-翻译:粒粒粒尘紫月猫姐夏酷校对:阿衡时间轴:邦德猪 | 约书亚 | D |
| -= ytet-伊甸园字幕组=-翻译:粒粒粒尘紫月猫姐夏酷校对 | 肯恩(男名) | 普通 |
| -=伊甸园美剧 http://sfile . ydy . com =-荣誉出品本字幕仅供学习交流，严禁用于商业途径 | 克里斯廷 | 克里斯托弗 |
| -=伊甸园美剧 http://sfile . ydy . com =-荣誉出品本字幕仅供学习交流，严禁用于商业途径 | 艾莉 | K |
| e6ae 4 cf 0-d358-4d55-b511-85902 FDA 9cc 6 突击步枪 | 丽娜 | M |

**步骤-4 :**
**从 CSV 文件中插入数据–**
在这里，您将看到如何从已有的 CSV 文件中向数据库中插入数据，您可以使用以下 cqlsh 命令，如下所示。

```
COPY data.Student_personal_data (S_id, S_firstname, S_lastname) 
FROM 'personal_data.csv' 
WITH HEADER = TRUE;
```

**第 5 步:**
**验证结果–**
一旦执行了上面的命令，就会得到如下结果。

```
Using 7 child processes

Starting copy of data.Student_personal_data with columns [S_id, S_firstname, S_lastname].
Processed: 6 rows; Rate:      10 rows/s; Avg. rate:      14 rows/s
6 rows imported from 1 files in 0.422 seconds (0 skipped).
```

您可以使用以下命令查看如下输出。

```
select * from data.Student_personal_data;
```

**输出:**

<figure class="table">

| S_id | s _ 名字 | S_lastname |
| --- | --- | --- |
| -=伊甸园美剧 http://sfile . ydy . com =-荣誉出品本字幕仅供学习交流，严禁用于商业途径 | (第一次世界大战时的)协约国 | K |
| e6ae 4 cf 0-d358-4d55-b511-85902 FDA 9cc 6 突击步枪 | 丽娜 | M |
| -= ytet-伊甸园字幕组=-翻译:粒粒粒尘紫月猫姐夏酷校对:阿衡时间轴:邦德猪 | 约书亚 | D |
| -=伊甸园美剧 http://sfile . ydy . com =-荣誉出品本字幕仅供学习交流，严禁用于商业途径 | Ashish | 克里斯托弗 |
| -= ytet-伊甸园字幕组=-翻译:粒粒粒尘紫月猫姐夏酷校对 | 肯恩(男名) | 普通 |
| -=伊甸园美剧 http://sfile . ydy . com =-荣誉出品本字幕仅供学习交流，严禁用于商业途径 | 克里斯廷 | 克里斯托弗 |

</figure>

</figure>