---
title: 基本功能
description: 计算指标生成器允许您将统计和数学函数应用于生成高级计算指标。
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 1a84fc71eb29ceabf3a3c5c3e333b78b882ea966
workflow-type: tm+mt
source-wordcount: '1185'
ht-degree: 30%

---

# 基本功能


[计算量度生成器](cm-workflow/cm-build-metrics.md)允许您应用统计和数学函数。 本文按字母顺序列出了各个函数及其定义。

>[!NOTE]
>
>当 [!DNL metric] 被标识为函数中的参数时，还允许使用其他指标表达式。例如，[COLUMN MAXIMUM(METRICS)](#column-maximum)还允许[COLUMN MAXIMUM(PageViews + Visits)](#column-maximum)。



## table函数与row函数

在 table 函数中，输出对于表中的每一行都是相同的。在 row 函数中，输出对于表中的每一行都是不同的。

在适用和相关的情况下，使用函数类型对函数进行注释： [!BADGE 表]{type="Neutral"}[!BADGE 行]{type="Neutral"}

## include-zeros参数的含义是什么？

它可告知计算中是否包含零。有时零表示&#x200B;*无*，但有时它很重要。

例如，如果您有一个收入指标，然后向报表中添加了一个页面查看次数量度，那么您的收入会突然出现更多的行，这些行全部为零。 您可能不希望该额外的量度影响收入列中的任何&#x200B;**[MEAN](cm-functions.md#mean)**、**[ROW MINIMUM](cm-functions.md#row-min)**、**[QUARTILE](cm-functions.md#quartile)**&#x200B;以及更多计算。 在这种情况下，您需要检查`include-zeros`参数。

另一种情况是，您有两个感兴趣的量度，而其中一个量度的平均值或最小值较高，因为某些行为零。  在这种情况下，您可以选择不检查参数以包含零



## 绝对值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 绝对值（量度）]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 要为其计算绝对值的指标。 |


## 列最大值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列最大值（量度，include_zeros）]**

返回某量度列的一组维度元素中的最大值。MAXV 可以在一个列（量度）内跨维度元素垂直估值。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个量度，但可将任意数量的量度作为参数。 |
| include_zeros | 是否在计算中包括零值。 |


## 列最小值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列最小值（量度，include_zeros）]**

返回某量度列的一组维度元素中的最小值。MINV 可以在一个列（量度）内跨维度元素垂直估值。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个量度，但可将任意数量的量度作为参数。 |
| include_zeros | 是否在计算中包括零值。 |


## 列总和

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 列总和（量度）]**

添加列中某指标的所有数值（跨维度元素）。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个量度，但可将任意数量的量度作为参数。 |


## 计数

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 计数（量度）]**

[!BADGE Table]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计数的量度。 |


## 指数

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 指数（量度）]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 应用于基础e的指数。 |


## 平均值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric， include_zeros)]**

[!BADGE Table]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 要为其计算平均值的指标。 |
| include_zeros | 是否在计算中包括零值。 |


## 中间值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric， include_zeros)]**

[!BADGE Table]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算中间值的指标。 |
| include_zeros | 是否在计算中包括零值。 |


## 取模

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MODULO(metric_X， metric_Y)]**

使用带余除法，将 x 除以 y 之后返回余数。

| 参数 | 描述 |
|---|---|
| metric_X | 您希望除的第一个量度。 |
| metric_Y | 您要除的第二个量度。 |

### 示例

返回值具有与输入值相同的符号（或为零）。

```
MODULO(4,3) = 1
MODULO(-4,3) = -1
MODULO(-3,3) = 0
```

为确保始终获得正数，请使用

```
MODULO(MODULO(x,y)+y,y)
```

## 百分点值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 百分位数(metric， k， include_zeros)]**

[!BADGE Table]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 介于 0 到 100 之间（包括 0 和 100）的百分位数值。 |
| k | 用于定义相对位置的量度列。 |
| include_zeros | 是否在计算中包括零值。 |



## 幂运算符

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 乘幂运算符(metric_X， metrix_Y)]**

返回x的幂y。

| 参数 | 描述 |
|---|---|
| metric_X | 您希望提升到metric_Y次幂的量度。 |
| metric_Y | 您希望将metric_X提升到的幂。 |


## 四分位数

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric， quartile， include_zeros)]**

[!BADGE Table]{type="Neutral"}当QUARTILE分别等于`0` （零）、`2`和`4`时，[COLUMN MINIMUM](#column-minimum)、[MEDIAN](#median)和[COLUMN MAXIMUM](#column-maximum)返回与[QUARTILE](#quartile)相同的值。

| 参数 | 描述 |
|---|---|
| 量度 | 您要为其计算四分位数值的指标。 |
| 四分位数 | 指示要返回的四分位数值。 |
| include_zeros | 是否在计算中包括零值。 |


## 轮次

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ROUND(metric， number)]**

不带&#x200B;*number*&#x200B;参数的四舍五入与带&#x200B;*number*&#x200B;参数为0的四舍五入相同，也就是四舍五入到最接近的整数。  使用&#x200B;*number*&#x200B;参数时，ROUND将返回小数点右边的&#x200B;*number*&#x200B;位数。  如果&#x200B;*number*&#x200B;为负数，则返回小数点左边的0。

| 参数 | 描述 |
|---|---|
| 量度 | 要舍入的量度。 |
| 数字 | 要返回的小数点右侧的位数。 （如果为负，则在小数点左边返回零）。 |

### 示例

```
ROUND( 314.15, 0) = 314
ROUND( 314.15, 1) = 314.1
ROUND( 314.15, -1) = 310
ROUND( 314.15, -2) = 300
```


## 行计数

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 行计数()]**

返回给定列的行计数（一个维度中报告的独特元素计数）。超过&#x200B;*个唯一值*&#x200B;将被计为1。


## 行最大值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 行MAX（指标，include_zeros）]**

每行列数的最大值。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个量度，但可将任意数量的量度作为参数。 |
| include_zeros | 是否在计算中包括零值。 |

## 行最小值

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 行最小值（量度，include_zeros）]**

每行列数的最小值。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个量度，但可将任意数量的量度作为参数。 |
| include_zeros | 是否在计算中包括零值。 |



## 行总和

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 行SUM（量度，include_zeros）]**

每一行中所有列的总和。

| 参数 | 描述 |
|---|---|
| 量度 | 至少需要一个量度，但可将任意数量的量度作为参数。 |


## 平方根

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 平方根（量度，include_zeros）]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 要为其计算平方根的指标。 |


## 标准偏差

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 标准偏差（量度，include_zeros）]**

[!BADGE Table]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| | 要为其计算标准偏差的指标。 |
| include_zeros | 是否在计算中包括零值。 |


## 方差

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric， include_zeros)]**

[!BADGE Table]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 要为其计算方差的量度。 |
| include_zeros | 是否在计算中包括零值。 |


VARIANCE 的方程式为：

![](assets/variance_eq.png){width="100"}

其中&#x200B;*x*&#x200B;为样本平均值，[MEAN（*个度量*）](#mean)和&#x200B;*n*&#x200B;为样本大小。


要计算方差，您需要查看整列数字。 首先，从该数字列表计算平均值。获得平均值后，请浏览每个条目并执行以下操作：

1. 从数字中减去平均值。

1. 将结果求平方。

1. 再相加求和。

一旦您迭代了整列，就会得到一个总计。 然后，将该总数除以列中的项目数。得出的数值就是列变量。它是单个数字。但它会显示为一列数字。

在以下三项列的示例中：

| 列 |
|:---:|
| 1 |
| 2 |
| 3 |

此列的平均值为 2。列的变量为((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3) = 2/3。




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