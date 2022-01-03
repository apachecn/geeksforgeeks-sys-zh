# 什么是分片？

> 原文:[https://www.geeksforgeeks.org/what-is-sharding/](https://www.geeksforgeeks.org/what-is-sharding/)

**分片**是一个非常重要的概念，它帮助系统根据分片过程将数据保存到不同的资源中。

**碎片**这个词的意思是“**整个**的一小部分”。因此，分割意味着将较大的部分分成较小的部分。

在 DBMS 中，分片是一种数据库分区类型，在这种类型中，大型数据库被划分或分割成较小的数据，也称为分片。这些碎片不仅更小，而且更快，因此易于管理。

**需要切分:**

考虑一个非常大的数据库，它的分片还没有完成。例如，让我们以一个学院的数据库为例，其中整个学院的所有学生记录(现在和过去)都保存在一个数据库中。因此，它将包含非常非常大量的数据，比如 100，000 条记录。

现在，当我们需要从这个数据库中找到一个学生时，每次大约需要进行 100，000 次交易才能找到这个学生，这是非常非常昂贵的。

现在考虑同样的大学生记录，根据年份分成更小的数据碎片。现在每个数据碎片将只有大约 1000-5000 个学生记录。因此，不仅数据库变得更加易于管理，而且每次的事务成本也降低了一个巨大的因素，这是通过分片实现的。

因此这就是为什么需要分片。

**分片的特点:**

*   Make the database smaller by slicing.
*   Make the database fragment faster.
*   Make the fragmented database easier to manage.
*   Sometimes slicing can be a complicated operation.
*   Fragmentation reduces the transaction cost of the database.