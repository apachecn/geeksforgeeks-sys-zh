# 数据仓库中的测试

> 原文:[https://www.geeksforgeeks.org/testing-in-data-warehouse/](https://www.geeksforgeeks.org/testing-in-data-warehouse/)

[数据仓库](https://www.geeksforgeeks.org/data-warehousing/)存储着海量的数据，这些数据通常是从文件、数据库管理系统等多个异构来源收集的，以产生有助于决策的统计结果。

**测试**对于数据仓库系统进行数据验证并使其正确高效地工作非常重要。
在数据仓库上执行三个基本级别的测试，如下所示:

1.  **[单元测试](https://www.geeksforgeeks.org/unit-testing-software-testing/)–**
    这种类型的测试是在开发人员端进行的。在单元测试中，模块的每个单元/组件都是单独测试的。对整个数据仓库的各个模块，即程序、SQL Script、过程、Unix shell 进行了验证和测试。
2.  **[【集成测试】](https://www.geeksforgeeks.org/software-engineering-integration-testing/)–**
    在这种类型的测试中，应用程序的各个单元/模块被放在一起或组合在一起，然后根据输入的数量进行测试。执行它是为了检测集成模块中的故障，并测试集成后各种组件是否运行良好。
3.  **[系统测试](https://www.geeksforgeeks.org/system-testing/)—**
    系统测试是对整个数据仓库应用进行验证和测试的测试形式。这种类型的测试由技术测试团队执行。这个测试是在开发人员的团队执行单元测试之后进行的，这个测试的主要目的是检查整个系统是否完全正常工作。

**数据仓库测试的挑战有:**

*   来自多个来源的数据选择和随后的分析提出了巨大的挑战。
*   数据量大且复杂，某些测试策略非常耗时。
*   ETL 测试需要配置单元 SQL 技能，因此它对 SQL 技能有限测试人员提出了挑战。
*   数据仓库中的冗余数据。
*   不一致和不准确的报告。

**ETL 测试分五个阶段进行:**

*   识别数据源和需求。
*   数据采集。
*   实现业务逻辑和维度建模。
*   构建和填充数据。
*   构建报告。