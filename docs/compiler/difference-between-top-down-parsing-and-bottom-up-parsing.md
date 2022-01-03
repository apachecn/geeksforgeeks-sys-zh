# 自上而下解析和自下而上解析的区别

> 原文:[https://www . geesforgeks . org/区分自上而下解析和自下而上解析/](https://www.geeksforgeeks.org/difference-between-top-down-parsing-and-bottom-up-parsing/)

解析中出现的[解析技术](https://www.geeksforgeeks.org/parsing-set-1-introduction-ambiguity-and-parsers/)有两种，第一种是[自顶向下解析](https://www.geeksforgeeks.org/compiler-design-classification-top-parsers/)，第二种是[自底向上解析](https://www.geeksforgeeks.org/parsing-set-2-bottom-up-or-shift-reduce-parsers/)。

**自上而下的解析**是一种解析技术，首先查看解析树的最高级别，并使用语法规则向下操作解析树，而**自下而上的解析**是一种解析技术，首先查看解析树的最低级别，并使用语法规则向上操作解析树。

下面给出了区分这两种解析技术的一些区别:

<center>

| S.No | 自顶向下分析 | 自底向上句型分析 |
| 1. | 这是一种解析策略，首先查看解析树的最高级别，然后使用语法规则沿着解析树向下操作。 | 这是一种解析策略，它首先查看解析树的最低层，然后使用语法规则来构建解析树。 |
| 2. | 自顶向下解析试图找到输入字符串最左边的派生。 | 自下而上的语法分析可以定义为试图减少输入字符串以开始一个语法符号。 |
| 3. | 在这种解析技术中，我们以自上而下的方式从顶部(解析树的开始符号)向下(解析树的叶节点)开始解析。 | 在这种解析技术中，我们以自下而上的方式从底部(解析树的叶节点)向上(解析树的开始符号)开始解析。 |
| 4. | 这种解析技术使用最左侧派生。 | 这种解析技术使用最右派生。 |
| 5. | 它的主要决策是选择使用什么生产规则来构造字符串。 | 它的主要决策是选择何时使用生产规则来减少字符串以获得起始符号。 |

</center>