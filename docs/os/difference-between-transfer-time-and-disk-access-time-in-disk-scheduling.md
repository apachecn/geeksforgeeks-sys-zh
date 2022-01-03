# 磁盘调度中传输时间和磁盘访问时间的差异

> 原文:[https://www . geesforgeks . org/传输时间和磁盘访问时间的差异磁盘调度/](https://www.geeksforgeeks.org/difference-between-transfer-time-and-disk-access-time-in-disk-scheduling/)

**1。传输时间:**
传输所需数据量所需的时间。它可以通过给定的公式计算

```
Transfer time,
= Data to be transfer / transfer rate 
```

**待传输数据**在问题中给出，**传输速率**有时给出，有时不给出。

可以用给定的公式计算。

```
Transfer Rate,
= {(Number of heads or number of surfaces in the disk)
     *(capacity of one track or number of sectors in each track)
       *(Number of rotations in each track to reach the required sector)}
```

**2。数据访问时间:**
是访问数据所需的总时间。这意味着从磁盘读取/写入数据所需的总时间。
以下是计算数据访问时间的公式:

```
Data access time,
= {(Seek time) + (Rotational Latency) + (Data Transfer Time)} 
```

**注:**

*   **寻道时间–**读写头从当前位置移动到所需磁道所需的时间。
*   **旋转延迟–**扇区进入读写磁头所需的时间。

**磁盘调度中传输时间和磁盘访问时间的差值:**

<center>

| 不，先生。 | 数据传输时间 | 数据访问时间 |
| --- | --- | --- |
| one | 传输所需数据量所需的时间。 | 这是访问数据所需的总时间。这意味着从磁盘读取/写入数据所需的总时间。 |
| Two | 为了计算数据传输时间，我们只需要传输速率 | 为了计算数据访问时间，我们需要寻道时间、旋转延迟和数据传输时间 |
| three | 因此，为了计算数据传输时间，不需要数据访问时间 | 为了计算数据访问时间，需要数据传输时间 |
| four | 传输时间=要传输的数据/传输速率 | 数据访问时间= {(寻道时间)+(旋转延迟)+(数据传输时间)} |

</center>