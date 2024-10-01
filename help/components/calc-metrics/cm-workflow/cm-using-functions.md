---
description: 您可以使用函数过滤/排序数据，以及执行统计分析。
title: 使用函数
feature: Calculated Metrics
exl-id: 7a41aa4e-90c6-4242-a801-2eef6b524cfe
source-git-commit: 664576605b8be098a751609536e388c304c65513
workflow-type: tm+mt
source-wordcount: '4051'
ht-degree: 97%

---

# 使用函数

您可以使用函数过滤、排序数据，以及进行简单和复杂的统计分析。

有关所有函数的列表，请参阅[基本函数](/help/components/calc-metrics/cm-functions.md)和[高级函数](/help/components/calc-metrics/cm-adv-functions.md)。


>[!NOTE]
>
>当 [!DNL metric] 被标识为函数中的参数时，还允许使用其他量度表达式。例如，[!DNL MAXV(metrics)] 还允许使用 [!DNL MAXV(PageViews + Visits).]
>

>[!NOTE]
>
>计算量度生成器的定义中包含函数时，应始终在拖入量度或过滤器之前应用该函数。
>

## table 函数与 row 函数

在 table 函数中，输出对于表中的每一行都是相同的。在 row 函数中，输出对于表中的每一行都是不同的。

## Include-Zeros 参数的含义

它可告知计算中是否包含零。零有时表示“无”，有时又十分重要。

例如，如果您有收入量度，然后又将页面查看次数量度添加到报表中，则您的收入会突然多出一些全部为零的行。您也许不希望这影响到收入列中已有的任何 MEAN、MIN、QUARTILE 等计算。在这种情况下，您需要检查 include-zeros 参数。

另一方面，如果您有两个感兴趣的量度，则因为其中一个量度的某些行是零而说该量度具有更高的平均值或最小值，这是不合理的，因此，在这种情况下，您不需要检查参数是否包含零。

<!-- This video is way too outdated and too much AA oriented to comfortably show as part of CJA functionality 

Watch this [video](https://youtu.be/SSyWvomnewI) to understand the use of functions.

-->

+++ 基本功能


## 绝对值 (Row)

返回某数字的绝对值。某数字的绝对值是一个具有正值的数字。

```
ABS(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求绝对值的指标。 |

## 列最大值

返回某指标列的一组维度元素中的最大值。MAXV 可以在一个列（指标）内跨维度元素垂直估值。

```
MAXV(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望计算的指标。 |

## 列最小值

返回某指标列的一组维度元素中的最小值。MINV 可以在一个列（指标）内跨维度元素垂直估值。

```
MINV(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望计算的指标。 |

## 列总和

添加列中某指标的所有数字值（跨维度元素）。

```
SUM(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求总值或总和的指标。 |

## 计数 (Table)

返回列中某指标的非零值的数量或计数（某个维度内报告的独特元素数）。

```
COUNT(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望计数的指标。 |

## 指数 (Row)

返回 *e* 的给定次幂。常数 *e* 等于 2.71828182845904，它是自然对数的底数。EXP 是 LN 的反函数，LN 是某数字的自然对数。

```
EXP(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 应用于底数 *e* 的指数。 |

## 求幂

幂运算符


pow(x，y) = x<sup>y</sup> = x *x* x*... （y次）


## 平均值 (Table)

返回列中某指标的算术平均值或平均数。

```
MEAN(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求平均数的指标。 |

## 中间值 (Table)

返回列中某指标的中间值。中间值是指位于一组数字正中间的那个数字，也就是说有一半数字的值大于或等于该中间值，还有一半数字的值小于或等于该中间值。

```
MEDIAN(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求中间值的指标。 |

## 取模

使用欧几里得除法求得 col1 / col2 的余数。

返回 x 除以 y 之后的余数。

```
x = floor(x/y) + modulo(x,y)
```

返回值具有与输入值相同的符号（或为零）。

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

要始终获得正数，请使用

```
modulo(modulo(x,y)+y,y)
```

## 百分位数 (Table)

返回某指标的 k-th 百分位数形式的值。您可以使用此函数确立一个接受阈值。例如，您可以决定检查其分数大于第 90 个百分位数的维度元素。

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> 用于定义相对位置的指标列。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> 介于 0 到 100 之间（包括 0 和 100）的百分位数值。 </td> 
  </tr> 
 </tbody> 
</table>

## 四分位数 (Table)

返回某指标的四分位数形式的值。例如，四分位数可用于查找在获得的收入方面排名前 25% 的产品。当 quart 分别等于 0（零）、2 和 4 时，MINV、MEDIAN 和 MAXV 可返回与 QUARTILE 相同的值。

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 参数 </th> 
   <th colname="col2" class="entry"> 描述 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> 您希望求四分位数值的指标。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> 指示要返回哪个*值。 </td> 
  </tr> 
 </tbody> 
</table>

&#42;如果 *quart* = 0，则 QUARTILE 会返回最小值。如果 *quart* = 1，则 QUARTILE 返回第一个四分位数（第 25 个百分位数）。如果 *quart* = 2，则 QUARTILE 返回第一个四分位数（第 50 个百分位数）。如果 *quart* = 3，则 QUARTILE 返回第一个四分位数（第 75 个百分位数）。如果 *quart* = 4，则 QUARTILE 返回最大值。

## 轮次

返回给定值的最接近整数。例如，如果您要避免在报告收入时出现货币小数位数，而某产品的收入为 $569.34，则使用公式 Round(*Revenue*) 可将收入四舍五入为最接近的美元数 $569。报告 $569.51 的产品将四舍五入为最接近的美元数 $570。

```
ROUND(metric)
```

| 参数 | 描述 |
|---|---|
| *数字* | 您希望舍入的指标。 |

在没有位数参数的情况下四舍五入，与在位数参数为 0 的情况下四舍五入是相同的，都会四舍五入为最接近的整数。使用位数参数，可在小数点右侧返回多位数字。如果位数为负，则在小数点左侧返回 0。

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## 行计数

返回给定列的行数（某个维度内报告的独特元素数）。“超出的独特数”将记为 1。

## 行最大值

每行列数的最大值。

## 行最小值

每行列数的最小值。

## 行总和

每行列数的总值。

## 平方根 (Row)

返回某数字的正平方根。某数字的平方根是该数字二分之一次幂的值。

```
SQRT(metric)
```

| 参数 | 描述 |
|---|---|
| *数字* | 您希望求平方根的指标。 |

## 标准偏差 (Table)

基于数据的抽样群体，返回变量的标准偏差或平方根。

STDEV 的方程式为：

![](../assets/std_dev.png)

其中，x 为抽样平均值 (*metric*)，*n* 为抽样大小。

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> 参数</b> </td> 
   <td> <b> 描述</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> 您希望求标准偏差的量度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 变量 (Table)

基于数据的抽样群体返回变量。

VARIANCE 的方程式为：

![](../assets/variance_eq.png)

其中，x 为抽样平均值 MEAN(*metric*)，*n* 为抽样大小。

```
VARIANCE(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求变量的指标。 |

为了计算变量，需要查看整列数字。首先，从该数字列表计算平均值。得出平均值后，浏览每个条目，然后执行以下操作：

1. 从数字中减去平均值。

2. 将结果求平方。

3. 再相加求和。

对整列进行迭代后，您将得到一个总数。然后，将该总数除以列中的项目数。得出的数值就是列变量。它是单个数字。但它会显示为一列数字。

对于包含三个项目的列：

1

2

3

此列的平均值为 2。此列的变量将为 ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3。

+++

+++ 高级功能


## AND

返回其参数的值。使用 NOT 确保值不等于某一特定值。

>[!NOTE]
>
>0（零）表示 False，而任何其他值均表示 True。

```
AND(logical_test1,[logical_test2],...)
```

| 参数 | 描述 |
|---|---|
| *logical_test1* | 必需。任何可被计算为 TRUE 或 FALSE 的值或表达式。 |
| *logical_test2* | 可选。您希望计算为 TRUE 或 FALSE 的其他条件。 |

## 非重复近似计数（维度）

返回适用于所选维度的维度项目的非重复近似计数。该函数使用非重复近似计数的 HyperLogLog (HLL) 方法。该函数已配置为保证该值在 95% 的实际值的 5% 以内。

```
Approximate Count Distinct (dimension)
```

| 参数 |  |
|---|---|
| *dimension* | 您想要的非重复近似项目计数的维度 |

### 用例示例

Approximate Count Distinct (customer ID eVar) 是此函数的常见用例。

新“近似客户”计算量度的定义：

![显示客户ID (eVar1)的近似县别不同新维度定义](../assets/approx-count-distinct.png)

以下表示在报告中使用“近似客户”量度的方式：

![显示独特访客和大约客户的自由格式表](../assets/approx-customers.png)

### 比较计数函数

Approximate Count Distinct() 是对 Count() 和 RowCount() 函数所做出的改进，因为创建的量度可用于任何维度报表，以呈现单独维度项目的近似计数。例如，“移动设备类型”报表中使用的客户 ID 计数。

由于 Approximate Count Distinct() 使用了 HLL 方法，而 Count() 和 RowCount() 属于精确计数，因而此函数的准确性要略小于 Count() 和 RowCount()。

## 反余弦 (Row)

返回某量度的反余弦。反余弦是一个其余弦为数字的角。返回的角为范围在 0（零）到 pi 之间的弧度。如果要将结果从弧度转换为角度，请将其乘以 180/PI( )。

```
ACOS(metric)
```

| 参数 |  |
|---|---|
| *metric* | 所需角的余弦，其范围介于 -1 到 1 之间。 |

## 反正弦 (Row)

返回某数字的反正弦。反正弦是一个其正弦为数字的角。返回的角为范围在 -pi/2 到 pi/2 之间的弧度。要以角度表示反正弦，请将结果乘以 180/PI( )。

```
ASIN(metric)
```

| 参数 |  |
|---|---|
| *metric* | 所需角的余弦，其范围介于 -1 到 1 之间。 |

## 反正切 (Row)

返回某数字的反正切。反正切是一个其正切为数字的角。返回的角为范围在 -pi/2 到 pi/2 之间的弧度。要以角度表示反正切，请将结果乘以 180/PI( )。

```
ATAN(metric)
```

| 参数 |  |
|---|---|
| *metric* | 所需角的余弦，其范围介于 -1 到 1 之间。 |

## 指数回归：预测的 Y (Row)

计算预测的 y 值 (metric_Y)，假定已知的 x 值 (metric_X) 使用“最小二乘法”计算基于以下方程式的最佳拟合直线。

```
ESTIMATE.EXP(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## Cdf-T

返回在 n 自由度的学生 t 分布下，其 Z 分数小于 x 的值的百分比。

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

返回在正态分布下，其 Z 分数小于 x 的值的百分比。

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499
```

## 向上取整 (Row)

返回不小于给定值的最小整数。例如，如果您要避免在报告收入时出现货币小数位数，而某产品的收入为 $569.34，则使用公式 CEILING(*Revenue*) 可将收入向上舍入为最接近的美元数 $570。

```
CEILING(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 要舍入的量度。 |

## 置信度

[!UICONTROL 置信度]是一种概率度量，可表明有多少证据能够表明给定变量与控制变量相同。置信度越高，表明支持控制变量和非控制变量具有相同性能的假设的证据越少。

```
fx Confidence (normalizing-container, success-metric, control, significance-threshold)
```

| 参数 | 描述 |
| --- | --- |
| 标准化容器 | 运行测试的基础（人、会话或事件）。 |
| 成功指标 | 用户正在将变量与之比较的一个或多个指标。 |
| 控制 | 试验中所有其他变量要与之进行比较的变量。输入控制变量维度项目的名称。 |
| 显著性阈值 | 此函数中的阈值默认设置为 95%。 |

{style="table-layout:auto"}

## 余弦 (Row)

返回给定角的余弦。如果角以角度表示，则将该角乘以 PI( )/180。

```
COS(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求余弦的弧度角。 |

## 立方根

返回某数字的正立方根。某数字的立方根是该数字三分之一次幂的值。

```
CBRT(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求立方根的量度。 |

## 累积

返回最后 N 行的 x 总和（按维度排序，将哈希值用于基于字符串的字段）。

如果 N &lt;= 0，则使用所有之前的行。由于它是按维度排序的，因此它仅对于具有自然顺序的维度（例如日期或路径长度）有用。

```
| Date | Rev  | cumul(0,Rev) | cumul(2,Rev) |
|------+------+--------------+--------------|
| May  | $500 | $500         | $500         |
| June | $200 | $700         | $700         |
| July | $400 | $1100        | $600         |
```

## 累积平均数

返回最后 N 行的平均数。

如果 N &lt;= 0，则使用所有之前的行。由于它是按维度排序的，因此它仅对于具有自然顺序的维度（例如日期或路径长度）有用。

>[!NOTE]
>
>使用收入/人员之类的比率量度时，它可能不会按预期工作：它会计算比率的平均值，而不是总计最后N行的收入并总计最后N行的人员数，然后将二者相除。 它使用的是

```
cumul(revenue)/cumul(person)
```

## 等于

返回与某一数字或字符串值完全匹配的项目。

## 指数回归_ 相关系数 (Table)

返回相关系数 *r*，它介于回归方程式的两个量度列（*metric_A* 和 *metric_B*）之间。

```
CORREL.EXP(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 指数回归：截距 (Table)

返回截距 *b*，它介于以下方程式的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
INTERCEPT.EXP(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 指数回归：斜率 (Table)

返回斜率 *a*，它介于以下方程式的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
SLOPE.EXP(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 向下取整 (Row)

返回不大于给定值的最大整数。例如，如果您要避免在报告收入时出现货币小数位数，而某产品的收入为 $569.34，则使用公式 FLOOR(*Revenue*) 可将收入向下舍入为最接近的美元数 $569。

```
FLOOR(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望舍入的量度。 |

## 大于

返回数字计数大于输入值的项目。

## 大于或等于

返回数字计数大于或等于输入值的项目。

## 双曲余弦 (Row)

返回某数字的双曲余弦。

```
COSH(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求双曲余弦的弧度角。 |

## 双曲正弦 (Row)

返回某数字的双曲正弦。

```
SINH(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求双曲正弦的弧度角。 |

## 双曲正切 (Row)

返回某数字的双曲正切。

```
TANH(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求双曲正切的弧度角。 |

## IF (Row)

IF 函数可在您指定的条件计算为 TRUE 时返回一个值，在该条件计算为 FALSE 时返回另一个值。

```
IF(logical_test, [value_if_true], [value_if_false])
```

| 参数 | 描述 |
|---|---|
| *logical_test* | 必需。任何可被计算为 TRUE 或 FALSE 的值或表达式。 |
| *[value_if_true]* | 您希望在 *logical_test* 参数计算为 TRUE 时返回的值。（如果未包含此参数，则此参数默认为 0。） |
| *[value_if_false]* | 您希望在 *logical_test* 参数计算为 FALSE 时返回的值。（如果未包含此参数，则此参数默认为 0。） |

## 小于

返回数字计数小于输入值的项目。

## 小于或等于

返回数字计数小于或等于输入值的项目。

## 提升

返回某个特定变量在向控件变量进行转化时具有的提升。它是给定变量与基线之间的性能差异除以基线的性能，并以百分比表示。

```
fx Lift (normalizing-container, success-metric, control)
```

| 参数 | 描述 |
| --- | --- |
| 标准化容器 | 运行测试的基础（人、会话或事件）。 |
| 成功指标 | 用户正在将变量与之比较的一个或多个指标。 |
| 控制 | 试验中所有其他变量要与之进行比较的变量。输入控制变量维度项的名称。 |

{style="table-layout:auto"}

## 线性回归_ 相关系数

Y = a X + b。返回相关系数。

## 线性回归_ 截距

Y = a X + b。返回 b。

## 线性回归_ 预测的 Y

Y = a X + b。返回 Y。

## 线性回归_ 斜率

Y = a X + b。返回 a。

## 以 10 为底的对数 (Row)

返回某数字以 10 为底数的对数。

```
LOG10(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求以 10 为底数的对数的正实数。 |

## 对数回归：相关系数 (Table)

返回相关系数 *r*，它介于回归方程式 [!DNL Y = a ln(X) + b] 的两个量度列（*metric_X* 和 *metric_Y*）之间。它是使用 CORREL 方程式计算的。

```
CORREL.LOG(metric_X,metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 对数回归：截距 (Table)

返回截距 *b* 作为最小二乘法回归，它介于回归方程式 [!DNL Y = a ln(X) + b] 的两个量度列（*metric_X* 和 *metric_Y*）之间。它是使用 INTERCEPT 方程式计算的。

```
INTERCEPT.LOG(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 对数回归：预测的 Y（行）

计算预测的 [!DNL y] 值 (metric_Y)，假定已知的 [!DNL x] 值 (metric_X) 使用“最小二乘法”计算基于 [!DNL Y = a ln(X) + b] 的最佳拟合直线。该值使用 ESTIMATE 方程式进行计算。

在回归分析中，此函数计算预测的 [!DNL y] 值 (*metric_Y*)，假定已知的 [!DNL x] 值 (*metric_X*) 使用对数计算 [!DNL Y = a ln(X) + b] 的最佳拟合直线。[!DNL a] 值对应每个 x 值，而 [!DNL b] 则是一个常数值。

```
ESTIMATE.LOG(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 对数回归：斜率 (Table)

返回斜率 *a*，它介于回归方程式 [!DNL Y = a ln(X) + b] 的两个量度列（*metric_X* 和 *metric_Y*）之间。它是使用 SLOPE 方程式计算的。

```
SLOPE.LOG(metric_A, metric_B)
```

| 参数 | 描述 |
|---|---|
| *metric_A* | 要指定为因变数的量度。 |
| *metric_B* | 要指定为自变数的量度。 |

## 自然对数

返回某数字的自然对数。自然对数以常数 *e* (2.71828182845904) 为底数。LN 是 EXP 函数的反函数。

```
LN(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求自然对数的正实数。 |

## NOT

如果数字为 0，则返回 1；如果为其他数字，则返回 0。

```
NOT(logical)
```

| 参数 | 描述 |
|---|---|
| *logical* | 必需。可被计算为 TRUE 或 FALSE 的值或表达式。 |

使用 NOT 时，需要知道表达式（&lt;、>、=、&lt;> 等）返回值 0 还是 1。

## 不等于

返回不包含输入值的完全匹配项的所有项目。

## 或 (Row)

如果有任何参数为 TRUE，则返回 TRUE；如果所有参数均为 FALSE，则返回 FALSE。

>[!NOTE]
>
>0（零）表示 False，而任何其他值均表示 True。

```
OR(logical_test1,[logical_test2],...)
```

| 参数 | 描述 |
|---|---|
| *logical_test1* | 必需。任何可被计算为 TRUE 或 FALSE 的值或表达式。 |
| *logical_test2* | 可选。您希望计算为 TRUE 或 FALSE 的其他条件。 |

## Pi

返回常数 PI (3.14159265358979)，精确到 15 位数字。

```
PI()
```

[!DNL PI] 函数没有参数。

## 幂回归：相关系数 (Table)

返回相关系数 *r*，它介于 [!DNL Y = b*X] 的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
CORREL.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 幂回归：截距 (Table)

返回截距 *b*，它介于 [!DNL Y = b*X] 的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 幂回归：预测的 Y (Row)

计算预测的 [!DNL y] 值 ([!DNL metric_Y])，假定已知的 [!DNL x] 值 ([!DNL metric_X]) 使用“最小二乘法”计算 [!DNL Y = b*X] 的最佳拟合直线。

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 幂回归：斜率 (Table)

返回斜率 *a*，它介于 [!DNL Y = b*X] 的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
SLOPE.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 二次回归：相关系数 (Table)

返回相关系数 *r*，它介于 [!DNL Y=(a*X+b)]**** 的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 二次回归：截距 (Table)

返回截距 *b*，它介于 [!DNL Y=(a*X+b)]**** 的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
INTERCEPT.POWER(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 二次回归：预测的 Y (Row)

计算预测的 [!DNL y] 值 (metric_Y)，假定已知的 [!DNL x] 值 (metric_X) 使用最小二乘法计算使用 [!DNL Y=(a*X+b)]**** 的最佳拟合直线。

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

| 参数 | 描述 |
|---|---|
| *metric_A* | 要指定为因变数的量度。 |
| *metric_B* | 要指定为因变数的量度。 |

## 二次回归：斜率 (Table)

返回斜率 *a*，它介于 [!DNL Y=(a*X+b)]**** 的两个量度列（*metric_X* 和 metric_Y）之间。

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 倒数回归：相关系数 (Table)

返回相关系数 *r*，它介于 [!DNL Y = a/X+b] 的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 您希望与 *metric_Y* 关联的量度。 |
| *metric_Y* | 您希望与 *metric_X* 关联的量度。 |

## 倒数回归：截距 (Table)

返回截距 *b*，它介于 [!DNL Y = a/X+b] 的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 倒数回归：预测的 Y (Row)

计算预测的 [!DNL y] 值 (metric_Y)，假定已知的 [!DNL x] 值 (metric_X) 使用最小二乘法计算使用 [!DNL Y = a/X+b] 的最佳拟合直线。

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 倒数回归：斜率 (Table)

返回斜率 *a*，它介于 [!DNL Y = a/X+b] 的两个量度列（*metric_X* 和 *metric_Y*）之间。

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

| 参数 | 描述 |
|---|---|
| *metric_X* | 要指定为因变数的量度。 |
| *metric_Y* | 要指定为自变数的量度。 |

## 正弦 (Row)

返回给定角的正弦。如果角以角度表示，则将该角乘以 PI( )/180。

```
SIN(metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求正弦的弧度角。 |

## T 分数

Z 分数的别名，即由平均值偏差除以标准偏差

## T 测试

通过 col 的 t 分数和 n 自由度，执行以 m 结尾的 t 测试。

签名为 `t_test( x, n, m )`。在下面，它只是调用 `m*cdf_t(-abs(x),n)`。（这类似于运行 `m*cdf_z(-abs(x))` 的 z 测试函数。）

其中，`m` 为尾数，`n` 为自由度。这些应为数字（整个报表的常量，即不按行发生变化）。

`X` 为 t 测试统计数据，通常是基于量度的公式（例如 zscore），每行都将对其进行评估。

返回值是指在给定自由度和尾数的情况下，获得测试统计数据 x 的几率。

**示例：**

1. 用其查找离群值：

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. 将其与 `if` 结合使用，以忽略过高或过低的跳出率，并对其他内容的访问次数进行计数：

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## 正切

返回给定角的正切。如果角以角度表示，则将该角乘以 PI( )/180。

```
TAN (metric)
```

| 参数 | 描述 |
|---|---|
| *metric* | 您希望求正切的弧度角。 |

## Z 分数 (Row)

返回基于正态分布的 Z 分数，或正态分数。Z 分数是一个标准偏差数，观测分数来自平均值。Z 分数为 0（零）表示分数与平均值相同。Z 分数可以为正数或负数，用于指示该分数在平均值之上还是之下，以及依据多少个标准偏差。

Z 分数的方程式为：

![](../assets/z_score.png)

其中，[!DNL x] 为原始分数，[!DNL μ] 为群体平均值，[!DNL σ] 为群体标准偏差。

>[!NOTE]
>
>[!DNL μ] (mu) 和 [!DNL σ] (sigma) 会使用该量度自动计算。

Z 分数（量度）

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> 参数 </th>
   <th colname="col2" class="entry"> 描述 </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> 返回其首个非零参数的值。 </p> </td>
  </tr>
 </tbody>
</table>

## Z 测试

通过 A 的 Z 分数，执行以 n 结尾的 Z 测试。

返回当前行在列中偶然可见的几率。

>[!NOTE]
>
>假定值为正态分布。

+++

