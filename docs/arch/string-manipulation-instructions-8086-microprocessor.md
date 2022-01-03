# 8086 微处理器中的串操作指令

> 原文:[https://www . geesforgeks . org/string-operation-instructions-8086-微处理器/](https://www.geeksforgeeks.org/string-manipulation-instructions-8086-microprocessor/)

字符串是内存中连续位置可用的一系列数据字节或字。它被称为字节串或字串。它们的内存总是按顺序分配的。用于操作字符串的指令称为字符串操作指令。

下表显示了字符串操作指令列表:

T21T31T50T54】noneT58】MOVSBT60T62 DS:SI 给出的双字内容变为 ES:DI

| 操作码 | 操作数 | 说明 | 例 |
| --- | --- | --- | --- |
| REP | 指令 | 重复给定指令直到 CX！= 0 | REP MOVSB |
| REPE | 指令 | 重复给定指令而 CX = 0 | REPE |
| REPZ | 指令 | 重复给定指令而 ZF = 1 | REPZ | REPNE | 指令= 0 | REPNE |
| REPNZ | 指令 | 重复给出的指令，而 ZF = 0 | REPNZ |
| MOVSB | 将 DS:SI 给出的字节内容移动到 ES:DI |
| MOVD |
| LODSB | none | 将地址 DS:SI 处的字节移入 AL； SI 为 incr/decr by 1 | LODSB |
| LODSW | none | 将地址 DS: SI 处的单词移入 AX；SI 为 incr/decr by 2 | LODSW |
| LODSD | none | 将地址 DS:SI 处的双字移入 EAX；SI 为 incr/decr by 4 | LODSD |
| STOSB | none | 将 AL 的内容移动到 ES:DI 给定的字节地址；DI 为 incr/dec by 1 | STOSB |
| STOSW | none | 将 AX 的内容移动到 ES:DI 给定的字地址；DI 为 incr/decr by 2 | STOSW |
| STOSD | none | 将 EAX 的内容移动到 ES:DI 给定的 DOUBLE WORD 地址；DI 为 incr/decr by 4 | STOSD |
| SCASB | none | 将 ES:DI 处的字节与 AL 进行比较，并根据结果设置标志 | SCASB |
| SCASW | none | 将 ES:DI 处的字与 | CMPSB | none | 将 ES:DI 处的字节与 DS:SI 处的字节进行比较，并设置标志 | CMPSB |
| CMPSW | none | 将 ES:DI 处的字与 DS:SI 处的字进行比较，并设置标志 | CMPSW |