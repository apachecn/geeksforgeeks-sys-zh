# 区分直写和回写方法

> 原文:[https://www . geesforgeks . org/区分直写和回写方法/](https://www.geeksforgeeks.org/differentiate-between-write-through-and-write-back-methods/)

先决条件–[直写和回写缓存](https://www.geeksforgeeks.org/write-through-and-write-back-in-cache/)

在读取操作期间，当中央处理器确定高速缓存中的一个字时，主存储器不包括在传输中。因此，当操作是写操作时，系统有两种方式可以继续。

**1。写通法:**最简单的方法是当缓存内存包含指定地址的字时，并行更新缓存内存时，每次内存写操作都更新主内存。这可以称为直写方法。

**2。回写方法:**
在写操作期间，回写方法中只更新缓存位置。然后，用一个标志来标记该位置，以便以后从高速缓存中删除该字时，将其复制到主存储器中。对于回写方法，原因是在一个字保留在缓存中的期间，它可以被更新多次。因此，只要该字保留在缓存中，主缓存中的副本就无关紧要。这仅仅是当该字从高速缓存中被移位时，该高速缓存需要被重写到主存储器中的精确副本。

**区分直写和回写方法:**

<figure class="table">

| 没有。 | 直写法 | 回写方法 |
| --- | --- | --- |
| one | 在这种方法中，每次存储器写操作都更新主存储器，如果高速缓冲存储器包含指定地址的字，则并行更新高速缓冲存储器。 | 在这种方法中，在写操作期间只更新缓存位置。 |
| Two | 主内存总是包含与缓存相同的数据。 | 主内存和缓存可能有不同的数据。 |
| three | 典型程序中内存写操作的次数较多。 | 典型程序中存储器写操作的次数较少 |
| four | 当通过直接存储器存取通信的输入/输出设备将接收最新的数据。 | 当通过直接存储器存取通信的输入/输出设备不能接收最新数据时。 |
| five | 这是一个同时写缓存和主存的过程。 | 这是一个写缓存的过程，数据从缓存中移除，首先复制到主内存。 |

</figure>