# 数据库管理系统|第 10 集

> 原文:[https://www . geesforgeks . org/database-management-systems-set-10/](https://www.geeksforgeeks.org/database-management-systems-set-10/)

GATE CS 2005 考试提出了以下问题。

**1)设 R 为关系实例，模式 R = (A，B，C，D)。我们定义 r1 = '从 r 中选择 A，B，C '，r2 = '从 r 中选择 A，D '。设 s = r1 * r2，其中*表示自然连接。假设 r 分解成 r1 和 r2 是有损耗的，下面哪一个是真的？**
(a) s 是 r 的子集
(b) r U s = r
(c) r 是 s 的子集
(d) r * s = s

回答(c)
考虑以下例子，其中 r 有损分解为 r1 和 r2。我们可以看到 r 是 s 的子集。

```
Table r
 A      B      C      D
---------------------------
 1     10     100    1000    
 1     20     200    1000    
 1     20     200    1001 

Table r1
 A      B      C
------------------
 1     10     100 
 1     20     200 

Table r2
 A     D  
-----------
 1    1000  
 1    1001

Table s (natural join of r1 and r2)
 A      B      C      D
---------------------------
 1     10     100    1000    
 1     20     200    1000    
 1     10     100    1001 
 1     20     200    1001 

```

**2)让 E1 和 E2 是一个简单单值属性的 E/R 图中的两个实体。R1 和 R2 是 E1 和 E2 之间的两种关系，其中 R1 是一对多，R2 是多对多。R1 和 R2 没有自己的特点。在关系模型中表示这种情况所需的最小表数是多少？**T4(a)2
(b)3
(c)4
(d)5

答案(b)
详见[http://geeksquiz.com/gate-gate-cs-2005-question-75/](http://geeksquiz.com/gate-gate-cs-2005-question-75/)解释。

**3)考虑一个关系方案 R = (A、B、C、D、E、H)，以下函数依赖项在该关系方案上保持:{ A–>B、BC–>D、E–>C、D–>A }。R 的候选键有哪些？**T4(a)AE、BE
(b) AE、BE、DE
(c) AEH、BEH、BCH
(d) AEH、BEH、DEH

回答(d)
一组属性 S 是关系 R 的候选键如果 S 的闭包是 R 的所有属性并且不存在 S 的子集其闭包是 R 的所有属性的话
AEH 的闭包，即 AEH+= { ABCDEH }
BEH 的闭包，即 BEH+= { ABCDEH }
DEH 的闭包，即 DEH+ = {ABCDEH}

所有往年论文/解答/说明、教学大纲、重要日期、笔记等请见 [GATE Corner](http://geeksquiz.com/gate-corner-2/) 。

如果您发现任何答案/解释不正确，或者您想分享更多关于上述主题的信息，请写评论。