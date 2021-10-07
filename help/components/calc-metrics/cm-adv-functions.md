---
title: 引用 - 高级函数
description: 可通过以下方法访问这些函数：选中函数下拉列表中的显示高级。
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
source-git-commit: d6902af2d5e8a706e6b572c3daca2f60661dbbe9
workflow-type: tm+mt
source-wordcount: '2944'
ht-degree: 99%

---

# 引用 - 高级函数

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 略有不同。[了解详情...](/help/getting-started/cja-aa.md)

可通过以下方法访问这些函数：选中&#x200B;**[!UICONTROL 函数]**&#x200B;下拉列表中的&#x200B;**[!UICONTROL 显示高级]**。

## table 函数与 row 函数

在 table 函数中，输出对于表中的每一行都是相同的。在 row 函数中，输出对于表中的每一行都是不同的。

## Include-Zeros 参数的含义

它可告知计算中是否包含零。零有时表示“无”，有时又十分重要。

例如，如果您有收入量度，然后又将页面查看次数量度添加到报表中，则您的收入会突然多出一些全部为零的行。您也许不希望这影响到收入列中已有的任何 MEAN、MIN、QUARTILE 等计算。在这种情况下，您需要检查 include-zeros 参数。

另一方面，如果您有两个感兴趣的量度，则因为其中一个量度的某些行是零而说该量度具有更高的平均值或最小值，这是不合理的，因此，在这种情况下，您不需要检查参数是否包含零。

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
| *logical_test1* | 必需. 任何可被计算为 TRUE 或 FALSE 的值或表达式。 |
| *logical_test2* | 可选。您希望计算为 TRUE 或 FALSE 的其他条件 |

## 非重复近似计数（维度）

返回适用于所选维度的维度项目的非重复近似计数。该函数使用非重复近似计数的 HyperLogLog (HLL) 方法。该函数已配置为保证该值在 95% 的实际值的 5% 以内。

```
Approximate Count Distinct (dimension)
```

| 参数 |  |
|---|---|
| *维度* | 您想要的非重复近似项目计数的维度 |

## 用例示例

Approximate Count Distinct (customer ID eVar) 是此函数的常见用例。

新“近似客户”计算量度的定义：

![](assets/approx-count-distinct.png)

以下表示在报告中使用“近似客户”量度的方式：

![](assets/approx-customers.png)

## 超出的独特数

Count()、RowCount() 和 Approximate Count Distinct() 会受到[“超出的独特数”限制](https://experienceleague.adobe.com/docs/analytics/technotes/low-traffic.html?lang=en)的约束。如果维度在特定月份内达到“超出的独特数”限制，则该值将计数为 1 个维度项目。

## 比较计数函数

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
| *量度* | 所需角的余弦，其范围介于 -1 到 1 之间。 |

## 反正切 (Row)

返回某数字的反正切。反正切是一个其正切为数字的角。返回的角为范围在 -pi/2 到 pi/2 之间的弧度。要以角度表示反正切，请将结果乘以 180/PI( )。

```
ATAN(metric)
```

| 参数 |  |
|---|---|
| *量度* | 所需角的余弦，其范围介于 -1 到 1 之间。 |

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
| *量度* | 要舍入的量度。 |

## 余弦 (Row)

返回给定角的余弦。如果角以角度表示，则将该角乘以 PI( )/180。

```
COS(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望求余弦的弧度角。 |

## 立方根

返回某数字的正立方根。某数字的立方根是该数字三分之一次幂的值。

```
CBRT(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望求立方根的量度。 |

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
>使用收入/访客之类的比率量度时，它可能不会按预期工作：它会计算比率的平均值，而不是总计最后 N 行的收入并总计最后 N 行的访客数，然后将二者相除。它使用的是

```
cumul(revenue)/cumul(visitor)
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
| *量度* | 您希望舍入的量度。 |

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
| *量度* | 您希望求双曲余弦的弧度角。 |

## 双曲正弦 (Row)

返回某数字的双曲正弦。

```
SINH(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望求双曲正弦的弧度角。 |

## 双曲正切 (Row)

返回某数字的双曲正切。

```
TANH(metric)
```

| 参数 | 描述 |
|---|---|
| *量度* | 您希望求双曲正切的弧度角。 |

## IF (Row)

IF 函数可在您指定的条件计算为 TRUE 时返回一个值，在该条件计算为 FALSE 时返回另一个值。

```
IF(logical_test, [value_if_true], [value_if_false])
```

| 参数 | 描述 |
|---|---|
| *logical_test* | 必需. 任何可被计算为 TRUE 或 FALSE 的值或表达式。 |
| *[value_if_true]* | 您希望在 *logical_test* 参数计算为 TRUE 时返回的值。（如果未包含此参数，则此参数默认为 0。） |
| *[value_if_false]* | 您希望在 *logical_test* 参数计算为 FALSE 时返回的值。（如果未包含此参数，则此参数默认为 0。） |

## 小于

返回数字计数小于输入值的项目。

## 小于或等于

返回数字计数小于或等于输入值的项目。

## 线性回归_ 相关系数

Y = a X + b。返回相关系数

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
| *量度* | 您希望求以 10 为底数的对数的正实数。 |

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
| *量度* | 您希望求自然对数的正实数。 |

## NOT

如果数字为 0，则返回 1；如果为其他数字，则返回 0。

```
NOT(logical)
```

| 参数 | 描述 |
|---|---|
| *logical* | 必需. 可被计算为 TRUE 或 FALSE 的值或表达式。 |

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
| *logical_test1* | 必需. 任何可被计算为 TRUE 或 FALSE 的值或表达式。 |
| *logical_test2* | 可选。您希望计算为 TRUE 或 FALSE 的其他条件 |

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
| *量度* | 您希望求正弦的弧度角。 |

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
| *量度* | 您希望求正切的弧度角。 |

## Z 分数 (Row)

返回基于正态分布的 Z 分数，或正态分数。Z 分数是一个标准偏差数，观测分数来自平均值。Z 分数为 0（零）表示分数与平均值相同。Z 分数可以为正数或负数，用于指示该分数在平均值之上还是之下，以及依据多少个标准偏差。

Z 分数的方程式为：

![](assets/z_score.png)

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
   <td colname="col1"> <i>量度</i> </td>
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
