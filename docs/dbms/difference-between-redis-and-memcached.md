# 【Redis 和 Memcached 的区别

> 原文:[https://www . geesforgeks . org/difference-redis-and-memcached/](https://www.geeksforgeeks.org/difference-between-redis-and-memcached/)

**1。Redis :**
Redis 是一个开源、键值、 [NoSQL](https://www.geeksforgeeks.org/introduction-to-nosql/) 数据库。它是一种内存中的数据结构，存储从内存提供的所有数据，并使用磁盘进行存储。它提供了独特的数据模型和高性能，支持各种数据结构，如字符串、列表、集合、哈希，它将其用作数据库缓存或消息代理。它也被称为数据结构服务器。它不支持模式关系数据库管理系统、SQL 或 ACID 事务。

**2。Memcached :**
Memcached 是一个简单的开源内存缓存系统，可以作为临时的内存数据存储。内存中存储的数据具有较高的读写性能，并将数据分发到多个服务器中。它是存储在内存中的字符串对象的键值，该应用编程接口适用于所有语言。Memcached 对于网站来说非常高效。

【Redis 和 Memcached 的区别–

<figure class="table">

| 参数 | REDIS | MEMCACHED |
| 初始版本 | 它于 2009 年发布。 | 它于 2003 年发布。 |
| 开发者 | 它是由萨尔瓦托勒·桑菲利波开发的。 | 它是由 Danga Interactive 开发的。 |
| 使用的内核 | 它使用单核。 | 它使用多个内核。 |
| 钥匙长度 | 在 Redis 中，最大密钥长度为 2GB。 | 在 Memcached 中，最大密钥长度为 250 字节。 |
| 装置 | 与 Memcached 相比，它简单且更容易安装。 | 可能很难安装。 |
| 数据结构 | 它使用列表、字符串、散列、排序集和位图作为数据结构。 | 它只使用字符串和整数作为数据结构。 |
| 速度 | 它的读写速度比 Memcached 慢。 | 它的读写速度比 Redis 高。 |
| 分身术 | 它支持主从复制和多主复制方法。 | 它不支持任何复制方法。 |
| 持久性 | 它比 Memcached 更耐用。 | 它不如 Redis 耐用。 |
| 辅助数据库模型 | 它有文档存储、图形数据库管理系统、搜索引擎和时间序列数据库管理系统作为辅助数据库模型。 | 它没有辅助数据库模型。 |
| 坚持 | 它使用持久数据。 | 它不使用持久数据。 |
| 分割方法 | 它支持分片。 | 它不支持任何分区方法。 |

</figure>