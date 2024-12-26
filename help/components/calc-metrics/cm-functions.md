---
title: 基本功能
description: 计算量度生成器允许您将统计和数学函数应用于生成高级计算指标。
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 47c5fc27d994667933103f864a253e086050bbf8
workflow-type: tm+mt
source-wordcount: '1636'
ht-degree: 100%

---

# 基本功能


使用[计算量度生成器](cm-workflow/cm-build-metrics.md)可以应用统计和数学函数。本文按字母顺序列出了这些函数及其定义。

>[!NOTE]
>
>当 [!DNL metric] 被标识为函数中的参数时，还允许使用其他指标表达式。例如，[COLUMN MAXIMUM(metrics)](#column-maximum) 还允许 [COLUMN MAXIMUM(PageViews + Visits)](#column-maximum)。



## 表函数与行函数

在 table 函数中，输出对于表中的每一行都是相同的。在 row 函数中，输出对于表中的每一行都是不同的。

在适用且相关的情况下，函数会用函数类型注释：[!BADGE 表]{type="Neutral"}[!BADGE 行]{type="Neutral"}

## Include-Zeros 参数的含义是什么？

它可告知计算中是否包含零。零有时表示&#x200B;*无*，有时又十分重要。

例如，如果您有收入量度，然后又将页面查看次数量度添加到报表中，则您的收入会突然多出一些全部为零的行。您可能不希望该附加量度影响收入栏中的任何&#x200B;**[平均值](cm-functions.md#mean)**、**[行最小值](cm-functions.md#row-min)**、**[四分位数](cm-functions.md#quartile)**&#x200B;以及其他计算。在这种情况下，您需要检查 `include-zeros` 参数。

另一种情况是，您有两个感兴趣的指标，其中一个指标的平均值或最小值较高，因为其中有些行为零。在这种情况下，您可以选择不检查参数，以包含零



## 绝对值 {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="绝对值"
>abstract="返回某数字的绝对值。某数字的绝对值是一个具有正值的数字。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您想要计算绝对值的指标。 |


## 列最大值 {#column-maximum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-max"
>title="列最大值"
>abstract="返回某量度列的一组维度元素中的最大值。MAXV 可以在一个列（量度）内跨维度元素垂直估值。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MAXIMUM(metric, include_zeros)]**

返回某量度列的一组维度元素中的最大值。MAXV 可以在一个列（量度）内跨维度元素垂直估值。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个指标，但可以将任意数量的指标作为参数。 |
| include_zeros | 是否在计算中包含零值。 |


## 列最小值 {#column-minimum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-min"
>title="列最小值"
>abstract="返回某量度列的一组维度元素中的最小值。MINV 可以在一个列（量度）内跨维度元素垂直估值。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN MINIMUM(metric, include_zeros)]**

返回某量度列的一组维度元素中的最小值。MINV 可以在一个列（量度）内跨维度元素垂直估值。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个指标，但可以将任意数量的指标作为参数。 |
| include_zeros | 是否在计算中包含零值。 |


## 列总和 {#column-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-col-sum"
>title="列总和"
>abstract="添加列中某量度的所有数值（跨维度元素）。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL COLUMN SUM(metric)]**

添加列中某量度的所有数值（跨维度元素）。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个指标，但可以将任意数量的指标作为参数。 |


## 计数 {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="计数"
>abstract="返回列中某量度的非零值的数量或计数（某个维度内报告的独特元素数）。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计数的量度。 |


## 指数 {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="指数"
>abstract="返回 e 的给定次幂。常数 e 等于 2.71828182845904，它是自然对数的底数。EXPONENT 是 LN 的反函数，LN 是某数字的自然对数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 应用于底数 e 的指数。 |


## 平均值 {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="平均值"
>abstract="返回列中某量度的算术平均值或平均数"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算平均数的量度。 |
| include_zeros | 是否在计算中包含零值。 |


## 中间值 {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="中间值"
>abstract="返回列中某量度的中间值。中间值是位于一组数字中间的数字。也就是说，一半的数字大于或等于中间值，一半的数字小于或等于中间值。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算中位数的量度。 |
| include_zeros | 是否在计算中包含零值。 |


## 取模 {#modulo}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-modulo"
>title="取模"
>abstract="使用带余除法，将 x 除以 y 之后返回余数。 "

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X, metric_Y)]**

使用带余除法，将 x 除以 y 之后返回余数。

| 参数 | 描述 |
|---|---|
| metric_X | 您想要划分的第一个指标。 |
| metric_Y | 您想要划分的第二个指标。 |

### 示例

返回值具有与输入值相同的符号（或为零）。

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

要确保您始终获得正数，请使用

```
MODULO(MODULO(x,y)+y,y)
```

## 百分位数 {#percentile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-percentile"
>title="百分位数"
>abstract="返回第 n 个百分位数，即 0 至 100 之间的值。当 n &lt; 0 时，该函数使用零。当 n > 100 时，该函数返回 100。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL PERCENTILE(metric, k, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 介于 0 到 100 之间（包括 0 和 100）的百分位数值。 |
| k | 用于定义相对位置的量度列。 |
| include_zeros | 是否在计算中包含零值。 |



## 幂运算符 {#power-operator}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pow"
>title="幂运算符"
>abstract="返回 x 的 y 次方。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER OPERATOR(metric_X, metrix_Y)]**

返回 x 的 y 次方。

| 参数 | 描述 |
|---|---|
| metric_X | 您想要计算其 metric_Y 次方的指标。 |
| metric_Y | 您想要将 metric_X 提升到的次方。 |


## 四分位数 {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="四分位数"
>abstract="返回某量度的四分位数形式的值。例如，四分位数可用于查找在获得的收入方面排名前 25% 的产品。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE 表]{type="Neutral"}当四分位数分别等于 `0`（零）、`2` 和 `4` 时，[COLUMN MINIMUM](#column-minimum), [MEDIAN](#median) 和 [COLUMN MAXIMUM](#column-maximum) 返回与 [QUARTILE](#quartile) 相同的值。

| 参数 | 描述 |
|---|---|
| 量度 | 您想要计算四分位数值的指标。 |
| 四分位数 | 指示要返回哪个四分位数值。 |
| include_zeros | 是否在计算中包含零值。 |


## 轮次 {#round}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-round"
>title="轮次"
>abstract="在没有&#x200B;*数字*&#x200B;参数的情况下四舍五入，与在&#x200B;*数字*&#x200B;参数为 0 的情况下四舍五入是相同的，都会四舍五入为最接近的整数。使用&#x200B;*数字*&#x200B;参数，ROUND 返回小数点右侧的&#x200B;*数字*&#x200B;位数。如果&#x200B;*数字*&#x200B;为负，则在小数点左侧返回 0。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric, number)]**

在没有&#x200B;*数字*&#x200B;参数的情况下四舍五入，与在&#x200B;*数字*&#x200B;参数为 0 的情况下四舍五入是相同的，都会四舍五入为最接近的整数。使用&#x200B;*数字*&#x200B;参数，ROUND 返回小数点右侧的&#x200B;*数字*&#x200B;位数。如果&#x200B;*数字*&#x200B;为负，则在小数点左侧返回 0。

| 参数 | 描述 |
|---|---|
| 量度 | 要舍入的量度。 |
| 数字 | 返回小数点右边的多少位数字。（如果负数返回小数点左侧的零）。 |

### 示例

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```

## 行计数 {#row-count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-rows"
>title="行计数"
>abstract="返回给定列的行计数（一个维度中报告的独特元素计数）。将&#x200B;*超出的独特数*&#x200B;计为 1。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ROW COUNT()]**

返回给定列的行计数（一个维度中报告的独特元素计数）。将&#x200B;*超出的独特数*&#x200B;计为 1。


## 行最大值 {#row-max}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-max"
>title="行最大值"
>abstract="每一行中所有列的最大值。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MAX(metric, include_zeros)]**

每一行中所有列的最大值。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个指标，但可以将任意数量的指标作为参数。 |
| include_zeros | 是否在计算中包含零值。 |


## 行最小值 {#row-min}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-min"
>title="行最小值"
>abstract="每一行中所有列的最小值。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ROW MIN(metric, include_zeros)]**

每一行中所有列的最小值。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个指标，但可以将任意数量的指标作为参数。 |
| include_zeros | 是否在计算中包含零值。 |



## 行总和 {#row-sum}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-row-sum"
>title="行总和"
>abstract="每一行中所有列的总和。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ROW SUM(metric, include_zeros)]**

每一行中所有列的总和。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个指标，但可以将任意数量的指标作为参数。 |


## 平方根 {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="平方根"
>abstract="返回某数字的正平方根。某数字的平方根是该数字二分之一次幂的值。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算平方根的量度。 |


## 标准偏差 {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="标准偏差"
>abstract="基于数据的抽样群体，返回变量的标准偏差或平方根。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| | 您想要计算标准差的指标。 |
| include_zeros | 是否在计算中包含零值。 |


## 方差 {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="方差"
>abstract="基于数据的抽样群体返回变量。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算变量的量度。 |
| include_zeros | 是否在计算中包含零值。 |


VARIANCE 的方程式为：

![](assets/variance_eq.png){width="100"}

其中 *x* 为抽样平均值，[MEAN(*metric*)](#mean)，*n* 为抽样大小。


为了计算变量，需要查看整列数字。首先，从该数字列表计算平均值。得出平均值后，浏览每个条目，然后执行以下操作：

1. 从数字中减去平均值。

1. 将结果求平方。

1. 再相加求和。

对整列进行迭代后，您将得到一个总数。然后，将该总数除以列中的项目数。得出的数值就是列变量。它是单个数字。但它会显示为一列数字。

在以下三项列的示例中：

| 列 |
|:---:|
| 1 |
| 2 |
| 3 |

此列的平均值为 2。此列的变量将为 ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3。

<!--

## Absolute Value (Row)

Returns the absolute value of a number. The absolute value of a number is the number with a positive value.

```
ABS(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the absolute value.  |

## Column Maximum

Returns the largest value in a set of dimension elements for a metric column. MAXV evaluates vertically within a single column (metric) across dimension elements.

```
MAXV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Minimum 

Returns the smallest value in a set of dimension elements for a metric column. MINV evaluates vertically within a single column (metric) across dimension elements.

```
MINV(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | A metric that you would like to have evaluated.  |

## Column Sum 

Adds all of the numeric values for a metric within a column (across the elements of a dimension).

```
SUM(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the total value or sum.  |

## Count (Table) 

Returns the number, or count, of non-zero values for a metric within a column (the number of unique elements reported within a dimension).

```
COUNT(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric that you want to count.  |

## Exponent (Row) 

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The exponent applied to the base *e*.  |

## Exponentiation 

Power Operator


pow(x,y) = x<sup>y</sup> = x*x*x*… (y times)


## Mean (Table) 

Returns the arithmetic mean, or average, for a metric in a column.

```
MEAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the average.  |

## Median (Table) 

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers—that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

```
MEDIAN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the median.  |

## Modulo 

The remainder of col1 / col2, using Euclidean division.

Returns the remainder after dividing x by y.

```
x = floor(x/y) + modulo(x,y)
```

The return value has the same sign as the input (or is zero).

```
modulo(4,3) = 1 
modulo(-4,3) = -1 
modulo(-3,3) = 0
```

To always get a positive number, use 

```
modulo(modulo(x,y)+y,y)
```

## Percentile (Table) 

Returns the k-th percentile of values for a metric. You can use this function to establish a threshold of acceptance. For example, you can decide to examine dimension elements who score above the 90  percentile.

```
PERCENTILE(metric,k)
```

<table id="table_35CD840ACFB44CD9979881DB8823CC53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric column that defines relative standing. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> The percentile value in the range 0 to 100, inclusive. </td> 
  </tr> 
 </tbody> 
</table>

## Quartile (Table) 

Returns the quartile of values for a metric. For example, quartiles can be used to find the top 25% of products driving the most revenue. MINV, MEDIAN, and MAXV return the same value as QUARTILE when quart is equal to 0 (zero), 2, and 4, respectively.

```
QUARTILE(metric,quart)
```

<table id="table_64EA3DAAE77541439D59FAF0353F83A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Argument </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <i>metric</i> </td> 
   <td colname="col2"> The metric for which you want the quartile value. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> Indicates which *value to return. </td> 
  </tr> 
 </tbody> 
</table>

&#42;If *quart* = 0, QUARTILE returns the minimum value. If *quart* = 1, QUARTILE returns the first quartile (25 percentile). If *quart* = 2, QUARTILE returns the first quartile (50 percentile). If *quart* = 3, QUARTILE returns the first quartile (75 percentile). If *quart* = 4, QUARTILE returns the maximum value.

## Round 

Returns the nearest integer for a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula Round( *Revenue*) to round revenue to the nearest dollar, or $569. A product reporting $569.51 will be round to the nearest dollar, or $570.

```
ROUND(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric you want to round.  |

Round without a digits parameter is the same as round with a digits parameter of 0, namely round to the nearest integer. With a digits parameter it returns that many digits to the right of the decimal. If digits is negative, it returns 0's to the left of the decimal.

```
round( 314.15, 0) = 314 
round( 314.15, 1) = 314.1 
round( 314.15, -1) = 310 
round( 314.15, -2) = 300
```

## Row Count 

Returns the count of rows for a given column (the number of unique elements reported within a dimension). "Uniques exceeded" is counted as 1.

## Row Max 

The maximum of the columns in each row.

## Row Min 

The minimum of the columns in each row.

## Row Sum

The sum of the columns of each row.

## Square Root (Row) 

Returns the positive square root of a number. The square root of a number is the value of that number raised to the power of 1/2.

```
SQRT(metric)
```

|  Argument  | Description  |
|---|---|
|  *number* | The metric for which you want the square root.  |

## Standard Deviation (Table) 

Returns the standard deviation, or square root of the variance, based on a sample population of data.

The equation for STDEV is:

![](assets/std_dev.png)

where x is the sample mean (*metric*) and *n* is the sample size.

```
STDEV(metric)
```

<table id="table_8BCF2E4B02434AABAAD026FB3C4E8B2F"> 
 <tbody> 
  <tr> 
   <td> <b> Argument</b> </td> 
   <td> <b> Description</b> </td> 
  </tr> 
  <tr> 
   <td> <b> <i> metric</i> </b> </td> 
   <td> <p> The metric for which you want for standard deviation. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variance (Table) 

Returns the variance based on a sample population of data.

The equation for VARIANCE is:

![](assets/variance_eq.png)

where x is the sample mean, MEAN(*metric*), and *n* is the sample size.

```
VARIANCE(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric for which you want the variance.  |

In order to calculate a variance you look at an entire column of numbers. From that list of numbers you first calculate the average. Once you have the average you go through each entry and do the following:

1. Subtract the average from the number.

2. Square the result.

3. Add that to the total.

Once you have iterated over the entire column you have a single total. You then divide that total by the number of items in the column. That number is the variance for the column. It is a single number. It is, however, displayed as a column of numbers.

In case of a three-item column:

1

2

3

The average of this column is 2. The variance for the column will be ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3.

-->