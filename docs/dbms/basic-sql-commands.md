# 基本 SQL 命令

> 原文:[https://www.geeksforgeeks.org/basic-sql-commands/](https://www.geeksforgeeks.org/basic-sql-commands/)

**<u>提问:</u>考虑下面给出的表格 ITEM，将命令写在** [**SQL**](https://www.geeksforgeeks.org/sql-tutorial/) **中 1–10，输出 11–20**

**<u>表:项目</u>**

<figure class="table">

| **S_No** | **项目名称** | **公司** | **成本** | **采购 _ 数量** | **DOP** |
| one | 班长 | 字母表 | Six thousand three hundred | Twenty | 2010-05-30 |
| Two | 中央处理器 | 累积分布函数（Cumulative Distribution Function 的缩写） | Eight thousand | Thirty | 2010-07-23 |
| three | 老鼠 | 菲兹西蒙综合医院 | Two hundred and fifty | Twenty-five | 2010-08-04 |
| four | 不间断电源 | HIJ | Two thousand one hundred | Ten | 2010-06-19 |
| five | 打印机 | JKL | Eight thousand four hundred | four | 2010-11-27 |
| six | 扫描仪 | JKL | Four thousand five hundred | six | 2010-08-14 |

**<u>编写的</u>**[**<u>SQL</u>**](https://www.geeksforgeeks.org/sql-tutorial/)**<u>命令为 1。数到 10。</u>**

**1。显示“2010-08-05”之后购买的项目名称和成本。**

```
Select Item_Name,Cost from ITEM where DOP>"2010-08-05";
```

**2。显示按采购日期排列的采购数量大于 10 的物料的信息。**

```
Select * from ITEM where Purchase_Qty>10 ORDER BY DOP;
```

**3。显示“JKL”公司项目的平均成本价。**

```
Select avg(cost) from ITEM where Company="JKL";
```

**4。显示名称以字母“M”**开头的项目的所有信息。

```
Select * from ITEM where Item_Name like "M%";
```

**5。显示公司名称中包含字母“J”的项目的最高成本价。**

```
Select max(Cost) from ITEM where Company like '%J%;
```

**6。显示采购数量大于 5 的物料的所有详细信息，按采购日期的降序排列。**

```
Select * from ITEM where Purchase_Qty>5 order by DOP desc;
```

**7。显示物料号、物料名称和所有物料的成本，其中物料名称的第二位是字母“o”。**

```
Select S_No,Item_Name,Cost from ITEM where instr(Item_Name,'o')=2;
```

**8。要显示公司，按购买月份分组的最小购买数量。**

```
Select Company,min(Purchase_Qty) from ITEM group by month(DOP);
```

**9。显示表 ITEM 的结构。**

```
Desc ITEM;
```

**10。将采购数量设置为“JKL”公司的 31。**

```
Update ITEM set Purchase_Qty=31 where Company='JKL'; 
```

**<u>为下面的</u>**[**<u>SQL</u>**](https://www.geeksforgeeks.org/sql-tutorial/)**<u>查询 11–20 写输出。</u>**

**11 时。从成本> 6000 和采购数量< 25 的项目中选择数量(*)；**
*<u>输出:</u>*

<figure class="table">

| **计数(*)** |
| Two |

**12 时。从成本< 5000 的项目中选择最大(采购数量)；**
*<u>输出:</u>*

<figure class="table">

| **最大(采购数量)** |
| Twenty-five |

**13。从采购数量>为 25 的项目中选择平均值(成本)；**
*<u>输出:</u>*

<figure class="table">

| **平均(成本)** |
| Eight thousand |

**14。从项目名称=扫描仪的项目中选择成本+200 作为“销售价格”；**
*<u>输出:</u>*

<figure class="table">

| **售价** |
| Four thousand seven hundred |

**15。从采购数量> =10 的项目中选择物料编号、物料名称、采购数量；**
*<u>输出:</u>*

<figure class="table">

| **S_No** | **项目名称** | **采购 _ 数量** |
| one | 班长 | Twenty |
| Two | 中央处理器 | Thirty |
| three | 老鼠 | Twenty-five |
| four | 不间断电源 | Ten |

**16。从项目中选择 Ucase(项目名称)、Lcase(公司)；**
*<u>输出:</u>*

<figure class="table">

| ucase(item _ name) | **Lcase(公司)** |
| 班长 | 字母表 |
| 中央处理器 | 累积分布函数（Cumulative Distribution Function 的缩写） |
| 老鼠 | 菲兹西蒙综合医院 |
| 不间断电源 | hij |
| 打印机 | jkl |
| 扫描仪 | jkl |

**17。从项目中选择 S_No，DOP，其中月份(DOP)= 8；**
*<u>输出:</u>*

<figure class="table">

| **S_No** | **DOP** |
| three | 2010-08-04 |
| six | 2010-08-14 |

**18。从项目中选择平均(成本)、最大(采购数量)；**
*<u>输出:</u>*

<figure class="table">

| **平均(成本)** | **最大(采购数量)** |
| Four thousand nine hundred and twenty-five | Thirty |

**19。从项目中选择项目名称，其中项目名称像“% e %”；**
*<u>输出:</u>*

<figure class="table">

| **项目名称** |
| 老鼠 |
| 打印机 |
| 扫描仪 |

**20。从 ITEM 中选择*其中长度(ITEM _ Name)= 3；**
*<u>输出:</u>*

<figure class="table">

| **S_No** | **项目名称** | **公司** | **成本** | **采购 _ 数量** | **DOP** |
| Two | 中央处理器 | 累积分布函数（Cumulative Distribution Function 的缩写） | Eight thousand | Thirty | 2010-07-23 |
| four | 不间断电源 | HIJ | Two thousand one hundred | Ten | 2010-06-19 |

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>

</figure>