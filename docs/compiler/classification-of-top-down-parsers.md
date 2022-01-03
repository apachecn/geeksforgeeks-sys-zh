# 自上而下解析器的分类

> 原文:[https://www . geesforgeks . org/classification-of-top-down-parser/](https://www.geeksforgeeks.org/classification-of-top-down-parsers/)

句法分析分为两类，即自顶向下的句法分析和自底向上的句法分析。自顶向下的解析基于最左侧的派生，而自底向上的解析依赖于反向最右侧的派生。

构建从根开始一直到叶的解析树的过程是自顶向下解析。

1.  The top-down parser is constructed from grammar without ambiguity and left recursion.
2.  The top-down parser uses the leftmost derivation to build the parsing tree.
3.  It allows grammar that is not affected by left factorization.

## **自上而下解析的分类–**

**1。回溯:**蛮力技术

**2。无回溯:**

1.  Recursive descent analysis
2.  Predictive or non-recursive parsing or LL(1) parsing or table-driven parsing

### **递归下降解析–**

1.  每当非终端用户第一次使用时，就选择第一个选项，并将其与给定的输入/输出字符串进行比较
2.  如果没有匹配，那么使用第二种选择，并与给定的输入/输出字符串进行比较。
3.  如果再次找不到匹配项，则选择替代项，依此类推。
4.  此外，如果至少有一个备选项匹配，则 I/P 字符串解析成功。

### **LL(1)或表驱动程序或预测解析器–**

1.  在 LL1 中，第一个 L 代表从左到右，第二个 L 代表最左边的派生。1 代表解析器在解析句子时使用的一些前瞻标记。
2.  LL(1)解析是从没有左递归、公共前缀和歧义的语法构建的。
3.  LL(1)解析器依赖于 1 个前瞻符号来预测扩展解析树的生产。
4.  这个解析器是非递归的。