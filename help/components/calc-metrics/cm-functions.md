---
title: 参考——基本函数
description: '计算量度生成器允许您将统计和数学函数应用于生成高级计算量度。 '
translation-type: tm+mt
source-git-commit: 2dab33dca173fcc0eab657b810e85e4740e5d7e0

---


# 参考——基本函数

计算量度生成器允许您将统计和数学函数应用于生成高级计算量度。

这里有一个按字母顺序排列的函数及其定义列表。

>[!NOTE] 当 [!DNL metric] 被标识为函数中的参数时，还允许使用其他量度表达式。例如，[!DNL MAXV(metrics)] 还允许使用 [!DNL MAXV(PageViews + Visits).]

## table 函数与 row 函数

表函数是表中每行的输出相同的函数。 行函数是表中每行的输出不同的函数。

## 绝对值 (Row)

返回一个数的绝对值。一个数的绝对值是该数的正值。

```
ABS(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望求得其绝对值的量度。 |

## 列最大值

返回量度列一组维度元素中的最大值。MAXV 对一个竖列（量度）中的维度元素进行求值运算。

```
MAXV(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望评估的度量。 |

## 列最小值

返回量度列一组维度元素中的最小值。MINV 对一个竖列（量度）中的维度元素进行求值运算。

```
MINV(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望评估的度量。 |

## 列总和

将一列中某个量度的所有数字值相加（一个维度中的所有元素）。

```
SUM(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望其总值或总和的度量。 |

## 计数 (Table)

返回一列中某个量度的数字、计数或非零值（一个维度中报告的具有唯一性的元素的数量）。

```
COUNT(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 要计数的量度。 |

## 指数 (Row)

Returns *e* raised to the power of a given number. The constant *e* equals 2.71828182845904, the base of the natural logarithm. EXP is the inverse of LN, the natural logarithm of a number.

```
EXP(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | The exponent applied to the base *e*. |

## 求幂

幂运算符

<pre>
pow(x,y) = x<sup>y</sup> = x*x*x*… (y 次)
</pre>

## 平均值 (Table)

返回一列中某个量度的算术平均数（平均值）。

```
MEAN(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望求得其平均值的量度。 |

## 中间值 (Table)

返回一列中某个量度的中位数。中位数是指一组数字当中居于中间位置的数，即在这组数字中，有一半的数字大于或等于该中位数，有一半的数字小于或等于该中位数。

```
MEDIAN(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望求得其中位数的量度。 |

## 取模

列1/列2的剩余部分，使用欧几里得分。

返回x除以y后的余数。

```
x = floor(x/y) + modulo(x,y)
```

返回值与输入具有相同的符号（或为零）。

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

返回度量值的第k百分位数。 您可以使用此函数建立接受阈值。 例如，您可以决定检查其分数大于第 90 个百分位数的维度元素。

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
   <td colname="col1"> <i>量度</i> </td> 
   <td colname="col2"> 定义相对位置的量度列。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>k </p> </td> 
   <td colname="col2"> 介于 0 到 100（含 0 和 100）的百分位值。 </td> 
  </tr> 
 </tbody> 
</table>

## 四分位数 (Table)

返回量度的四分位数的值。例如，四分位数可用来找到占收入最高的前 25% 的产品。当四分位数分别等于 0（零）、2、4 时，相应地 MINV、MEDIAN、MAXV 将返回与该四分位数一样的值。

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
   <td colname="col1"> <i>量度</i> </td> 
   <td colname="col2"> 您希望求得其四分位值的量度。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>quart </p> </td> 
   <td colname="col2"> 指示要返回的*值。 </td> 
  </tr> 
 </tbody> 
</table>

*If *quart* = 0, QUARTILE returns the minimum value. 如果 *quart* = 1，则 QUARTILE 返回第一个四分位数（第 25 个百分位数）。如果 *quart* = 2，则 QUARTILE 返回第一个四分位数（第 50 个百分位数）。如果 *quart* = 3，则 QUARTILE 返回第一个四分位数（第 75 个百分位数）。如果 *quart* = 4，则 QUARTILE 返回最大值。

## 轮次

返回给定值的最接近整数。例如，如果您要避免在报告收入时出现货币小数位数，而某产品的收入为 $569.34，则使用公式 Round(*Revenue*) 可将收入四舍五入为最接近的美元数 $569。产品报告$569.51将舍入到最接近的美元，即$570。

```
ROUND(metric)
```

| 参数 | 描述 |
|---|---|
| *数字* | 要舍入的度量。 |

在不指定位数参数的情况下四舍五入与位数参数为 0 是一样的，也就是四舍五入到最接近的整数。在指定位数参数的情况下，如果位数参数为正，则四舍五入到指定的小数位；如果位数参数为负，则对小数点左侧的值进行四舍五入，且后 n 位为 0（n 为位数参数绝对值）。

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

返回一个数的正平方根。正平方根是一个数的 1/2 次幂的值。

```
SQRT(metric)
```

| 参数 | 描述 |
|---|---|
| *数字* | 您希望求得其平方根的量度。 |

## 标准偏差 (Table)

根据一组样本数据返回标准偏差（方差的平方根）。

STDEV的等式是：

![](assets/std_dev.png)

其中x是样本平均值(*度量*), *n是样本大小* 。

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
   <td> <b> <i> 度量</i></b> </td> 
   <td> <p> 您希望求得其标准偏差的量度。 </p> </td> 
  </tr> 
 </tbody> 
</table>

## 变量 (Table)

根据一组样本数据返回方差。

VARIANCE的等式是：

![](assets/variance_eq.png)

其中x是样本均值，MEAN(*metric*), *n是样本大小* 。

```
VARIANCE(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望求得其方差的量度。 |

为了计算方差，您需要查看整列数字。 从那列表的数字中，你首先计算平均值。 获得平均值后，您将逐个进入并执行以下操作：

1. 从数字中减去平均值。

2. 将结果求平方。

3. 再相加求和。

在整个列上重复执行后，您只有一个总计。 然后，将该总数除以列中的项目数。 该数字是列的差异。 这是一个数字。 但是，它显示为一列数字。

例如，假设您有一个三项列：

1

2

3

此列的平均值为2。 此列的变量将为 ((1 - 2)² + (2 - 2)² + (3 - 2)²/3 = 2/3。在临时分析中，其外观如下：

1 2/3

2 2/3

3 2/3
