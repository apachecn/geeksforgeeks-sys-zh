# 时间戳协议与 DBMS 中 Thomos 写规则的主要区别

> 原文:[https://www . geesforgeks . org/main-timestamp-protocol-and-thomos-write-rule-in-DBMS/](https://www.geeksforgeeks.org/main-difference-between-timestamp-protocol-and-thomos-write-rule-in-dbms/)

**[时间戳协议](https://www.geeksforgeeks.org/timestamp-based-concurrency-control/) :**
时间戳协议确保系统中的每个事务都预先具有与每个事务相关联的时间戳，该时间戳仅在该时间对系统中要执行的事务有帮助。

这在系统中同时运行大量并发进程的情况下非常有用。因此，它在 ts 计数器的帮助下为系统中的每个事务分配一个唯一的时间戳。

**ts 计数器:**
ts 计数器是用于时间戳协议的计数器。当每个提交操作在系统中发生时，它将其值增加 1。如果一个事务 Ti 已经被分配了时间戳 TS[Ti]，并且一个新的事务进入系统，那么它必须持有一个条件，即 TS[Ti] < TS[Ti]

**[Thomas Write Rule](https://www.geeksforgeeks.org/thomas-write-rule-in-dbms/):**
是时间戳排序协议的修改版。假设事务 Ti 发出写操作(Q):

1.  如果 TS[Ti] < R-TS(Q)，那么 Ti 产生的 Q 值是以前需要的，并且假设该值永远不会产生。因此，系统拒绝写操作并回滚钛。
2.  如果 TS[Ti]
3.  否则，系统执行写操作，并将 w-TS(Q)设置为 TS(Ti)。

**时间戳协议和 Thomas 写规则的区别是:**
这两者之间唯一的区别在于第二个规则，即在时间戳排序协议中，如果 Ti 发出 write (Q)和 TS[Ti] < W-ts(Q)，Ti 就会回滚。但是，在 Thomas writes 规则中，如果 TS(Ti) =R 时间戳(Q)，则可以忽略写操作。