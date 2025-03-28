---
title: 高级功能
description: 可通过以下方法访问这些函数：选中函数下拉列表中的显示高级。
feature: Calculated Metrics
exl-id: 3689a499-817d-4a59-8a1f-5f7bda297268
role: User
source-git-commit: 6788275ba4bfcfbe385e45e6a20de996d8103393
workflow-type: tm+mt
source-wordcount: '4659'
ht-degree: 97%

---

# 高级功能

使用[计算量度生成器](cm-workflow/cm-build-metrics.md)可以应用统计和数学函数。本文记录了按字母顺序排列的高级函数及其定义列表。

在组件面板中的![效果](/help/assets/icons/Effect.svg)**[!UICONTROL 功能]**&#x200B;列表下方选择&#x200B;**[!UICONTROL 显示全部]**，即可访问这些功能。向下滚动查看&#x200B;**[!UICONTROL 高级功能]**&#x200B;列表。

## 表函数与行函数

在 table 函数中，输出对于表中的每一行都是相同的。在 row 函数中，输出对于表中的每一行都是不同的。

在适用且相关的情况下，函数会用函数类型注释：[!BADGE 表]{type="Neutral"}[!BADGE 行]{type="Neutral"}

## Include-Zeros 参数的含义是什么？

它可告知计算中是否包含零。零有时表示&#x200B;*无*，有时又十分重要。

例如，如果您有收入量度，然后又将页面查看次数量度添加到报告中，则您的收入会突然多出一些全部为零的行。您可能不希望该附加量度影响收入栏中的任何&#x200B;**[平均值](cm-functions.md#mean)**、**[行最小值](cm-functions.md#row-min)**、**[四分位数](cm-functions.md#quartile)**&#x200B;以及其他计算。在这种情况下，您需要检查 `include-zeros` 参数。

另一种情况是，您有两个感兴趣的量度，其中一个量度的平均值或最小值较高，因为其中有些行为零。在这种情况下，您可以选择不检查参数，以包含零。


## 与 {#and}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-and"
>title="与"
>abstract="连词。不等于零被认为是真，等于零被认为是假。输出为 0（假）或 1（真）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL AND(logical_test)]**

连词。不等于零被认为是真，等于零被认为是假。输出为 0（假）或 1（真）。

| 参数 | 描述 |
|---|---|
| logical_test | 至少需要一个参数，但可以接受任意数量的参数。任何可被计算为 TRUE 或 FALSE 的值或表达式 |


## 非重复近似计数 {#approximate_count_distinct}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count-distinct-metric"
>title="非重复近似计数"
>abstract="返回适用于所选维度的维度项的非重复近似计数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL APPROXIMATE COUNT DISTINCT(dimension)]**


返回适用于所选维度的维度项的非重复近似计数。


| 参数 | 描述 |
|---|---|
| 维度 | 您希望计算非重复近似项目计数的维度 |

### 示例

此函数的常见用例是您想要获取客户的近似数量。



## 反余弦 {#arc-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-acos"
>title="反余弦"
>abstract="返回某量度的反余弦。反余弦是一个其余弦为数字的角度。返回的角度为范围在 0（零）到 pi 之间的弧度。如果要将结果从弧度转换为角度，请将其乘以 180/PI()。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ARC COSINE(metric)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| 量度 | 所需角的余弦，其范围介于 -1 到 1 之间 |



## 反正弦 {#arc-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-asin"
>title="反正弦"
>abstract="返回一个数值的反正弦（或逆正弦）值。反正弦是一个其正弦为数值的角度。返回的角度为范围在 -pi/2 到 pi/2 之间的弧度。要以角度表示反正弦，请将结果乘以 180/PI()。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ARC SINE(metric)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| 量度 | 所需角的正弦，其范围介于 -1 到 1 之间 |



## 反正切 {#arc-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-atan"
>title="反正切"
>abstract="返回一个数值的反正切（或逆正切）值。反正切是一个其正切为数值的角度。返回的角度为范围在 -pi/2 到 pi/2 之间的弧度。要以角度表示反正切，请将结果乘以 180/PI( )。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ARC TANGENT(metric)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| 量度 | 所需角的正切，其范围介于 -1 到 1 之间 |



## Cdf-T {#cdf-t}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-t"
>title="Cdf-T"
>abstract="返回自由度为 n 的学生 t 分布中，随机变量 z 分数小于列值的概率。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-T(metric, number)]**

返回自由度为 n 的学生 t 分布中，随机变量 z 分数小于列值的概率。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望求学生 t 分布累积分布函数的量度 |
| 数字 | 学生 t 分布的累积分布函数所对应的自由度 |

### 示例

```
CDF-T(-∞, n) = 0
CDF-T(∞, n) = 1
CDF-T(3, 5) ? 0.99865
CDF-T(-2, 7) ? 0.0227501
CDF-T(x, ∞) ? cdf_z(x)
```


## Cdf-Z {#cdf-z}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cdf-z"
>title="Cdf-Z"
>abstract="返回正态分布中随机变量 z 分数小于列值的概率。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CDF-Z(metric, number)]**

返回正态分布中随机变量 z 分数小于列值的概率。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望求标准正态分布累积分布函数的量度 |

### 示例

```
CDF-Z(-∞) = 0
CDF-Z(∞) = 1
CDF-Z(0) = 0.5
CDF-Z(2) ? 0.97725
CDF-Z(-3) ? 0.0013499
```

## 上限 {#ceiling}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ceil"
>title="上限"
>abstract="返回不小于给定值的最小整数。例如，如果您要避免在报告收入时出现货币小数位数，而某产品的收入为 $569.34，则使用公式 CEILING(Revenue) 可将收入向上舍入为最接近的美元数 $570。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CEILING(metric)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 要舍入的量度 |


## 置信度 {#confidence}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence"
>title="置信度"
>abstract="使用[时间统一中心极限定理和渐近置信序列](https://arxiv.org/pdf/2103.06476)中所述的 WASKR 方法计算任意时间有效的置信度。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

使用[时间统一中心极限定理和渐近置信序列](https://arxiv.org/pdf/2103.06476)中所述的 WASKR 方法计算任意时间有效的置信度。

置信度是一种概率度量，可表明有多少证据能够表明给定变量与控制变量相同。置信度越高，表明支持控制变量和非控制变量具有相同性能的假设的证据越少。

| 参数 | 描述 |
| --- | --- |
| 标准化容器 | 运行测试的基础（人员、会话或事件）。 |
| success-metric | 用户正在将变量与之比较的一个或多个量度。 |
| 控制 | 试验中所有其他变量要与之进行比较的变量。输入控制变量维度项的名称。 |
| 显著性阈值 | 此函数中的阈值默认设置为 95%。 |


## 置信度（下限） {#confidence-lower}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-lower"
>title="置信度（下限）"
>abstract="使用[时间统一中心极限定理和渐近置信序列](https://arxiv.org/pdf/2103.06476)中所述的 WASKR 方法计算任意时间有效的置信度（**下限**）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

使用[时间统一中心极限定理和渐近置信序列](https://arxiv.org/pdf/2103.06476)中所述的 WASKR 方法计算任意时间有效的置信度（**下限**）。

置信度是一种概率度量，可表明有多少证据能够表明给定变量与控制变量相同。置信度越高，表明支持控制变量和非控制变量具有相同性能的假设的证据越少。

| 参数 | 描述 |
| --- | --- |
| 标准化容器 | 运行测试的基础（人员、会话或事件）。 |
| success-metric | 用户正在将变量与之比较的一个或多个量度。 |
| 控制 | 试验中所有其他变量要与之进行比较的变量。输入控制变量维度项的名称。 |
| 显著性阈值 | 此函数中的阈值默认设置为 95%。 |

## 置信度（上限） {#confidence-upper}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-confidence-interval-upper"
>title="置信度（上限）"
>abstract="使用[时间统一中心极限定理和渐近置信序列](https://arxiv.org/pdf/2103.06476)中所述的 WASKR 方法计算任意时间有效的置信度（**上限**）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CONFIDENCE(normalizing-container, success-metric, control, significance-treshold)]**

使用[时间统一中心极限定理和渐近置信序列](https://arxiv.org/pdf/2103.06476)中所述的 WASKR 方法计算任意时间有效的置信度（**上限**）。

置信度是一种概率度量，可表明有多少证据能够表明给定变量与控制变量相同。置信度越高，表明支持控制变量和非控制变量具有相同性能的假设的证据越少。

| 参数 | 描述 |
| --- | --- |
| 标准化容器 | 运行测试的基础（人员、会话或事件）。 |
| success-metric | 用户正在将变量与之比较的一个或多个量度。 |
| 控制 | 试验中所有其他变量要与之进行比较的变量。输入控制变量维度项的名称。 |
| 显著性阈值 | 此函数中的阈值默认设置为 95%。 |


## 余弦 {#cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cos"
>title="余弦"
>abstract="返回给定角度的余弦。如果角以角度表示，则将该角乘以 PI()/180。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL COSINE(metric)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望求余弦的弧度角 |


## 立方根 {#cube-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cube-root"
>title="立方根"
>abstract="返回某数字的正立方根。某数字的立方根是该数字三分之一次幂的值。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CUBE ROOT(metric)]**


返回某数字的正立方根。某数字的立方根是该数字三分之一次幂的值。


| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算立方根的量度 |



## 累积 {#cumulative}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul"
>title="累积"
>abstract="返回 x 列最后 n 个元素的和。如果 n > 0，则对最后 n 个元素或 x 求和。如果 n &lt; 0，则对前面的元素求和。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE(number, metric)]**

返回 x 列最后 n 个元素的和。如果 n > 0，则对最后 n 个元素或 x 求和。如果 n &lt; 0，则对前面的元素求和。

| 参数 | 描述 |
| --- | --- |
| 数字 | 返回总和的最后 N 行。如果 N &lt;= 0，则使用所有之前的行。 |
| 量度 | 您希望求累计总和的量度。 |

### 示例

| 日期 | 收入 | CUMULATIVE(0, Revenue) | CUMULATIVE(2, Revenue) |
|------|------:|--------------:|--------------:|
| 5 月 | $500 | $500 | $500 |
| 6 月 | $200 | $700 | $700 |
| 7 月 | $400 | $1100 | $600 |


## 累积（平均） {#cumulative-average}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cumul-avg"
>title="累积（平均）"
>abstract="返回 x 列最后 n 个元素的平均值。如果 n > 0，则对最后 n 个元素或 x 求和。如果 n &lt; 0，则对前面的元素求和。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL CUMULATIVE AVERAGE(number, metric)]**

返回 x 列最后 n 个元素的平均值。如果 n > 0，则对最后 n 个元素或 x 求和。如果 n &lt; 0，则对前面的元素求和。

| 参数 | 描述 |
| --- | --- |
| 数字 | 返回平均值的最后 N 行。如果 N &lt;= 0，则使用所有之前的行。 |
| 量度 | 您希望求累计平均值的量度。 |

>[!NOTE]
>
>此函数不适用于每人收入等比率量度。该函数对比率求平均值，而不是对最后 N 行的收入求和，对最后 N 行的人数求和，然后再除以它们。<br/>相反，使用 [**[!UICONTROL CUMULATIVE(revenue)]**](#cumulative) ![除以](/help/assets/icons/Divide.svg) [**[!UICONTROL CUMULATIVE(person)]**](#cumulative)。
>


## 等于 {#equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-eq"
>title="等于"
>abstract="等于。输出为 0（假）或 1（真）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL EQUAL()]**

等于。输出为 0（假）或 1（真）。


| 参数 | 描述 |
|---|---|
| metric_X | 要用于比较的指标。 |
| metric_Y | 要用作比较的量度。 |

### 示例

`Metric 1 = Metric 2`


## 指数回归：相关系数 {#exponential-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-exp"
>title="指数回归：相关系数"
>abstract="指数回归：Y = a exp(X) + b。返回相关系数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE 表]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| metric_X | 您希望与 metric_Y 关联的量度 |
| metric_Y | 您希望与 metric_X 关联的量度 |
| include_zeros | 是否在计算中包含零值 |

## 指数回归：预测的 Y {#exponential-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-exp"
>title="指数回归：预测的 Y"
>abstract="指数回归：Y = a exp(X) + b。返回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为独立数据的量度。 |
| metric_Y | 您希望指定为从属数据的量度。 |
| include_zeros | 是否在计算中包含零值 |


## 指数回归：截距 {#exponential-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-exp"
>title="指数回归：截距"
>abstract="指数回归：Y = a exp(X) + b。返回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |


## 指数回归：斜率 {#exponential-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-exp"
>title="指数回归：斜率"
>abstract="指数回归：Y = a exp(X) + b。返回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENTIAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**


[!BADGE 表]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |


## Floor {#floor}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-floor"
>title="Floor"
>abstract="返回不大于给定值的最大整数。例如，如果您要避免在报告收入时出现货币小数位数，而某产品的收入为 $569.34，则使用公式 FLOOR(Revenue) 可将收入向下舍入为最接近的美元数 $569。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL FLOOR(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 要舍入的量度。 |


## 大于 {#greather-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-gt"
>title="大于"
>abstract="输出为 0（假）或 1（真）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN()]**

输出为 0（假）或 1（真）。

| 参数 | 描述 |
|---|---|
| metric_X | 要用于比较的基本量度。 |
| metric_Y | 要用作比较的量度。 |

### 示例

`Metric 1 > Metric 2`


## 大于或等于 {#greater-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ge"
>title="大于或等于"
>abstract="大于或等于输出为 0（假）或 1（真）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL GREATER THAN OR EQUAL()]**

大于或等于输出为 0（假）或 1（真）。

| 参数 | 描述 |
|---|---|
| metric_X | 要用于比较的基本量度。 |
| metric_Y | 要用作比较的量度。 |

### 示例

`Metric 1 >= Metric 2`



## 双曲余弦 {#hyperbolic-cosine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-cosh"
>title="双曲余弦"
>abstract="返回某数字的双曲余弦。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC COSINE(metric)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| 量度 | 您希望求双曲余弦的弧度角 |



## 双曲正弦 {#hyperbolic-sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sinh"
>title="双曲正弦"
>abstract="返回某数字的双曲正弦。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC SINE(metric)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望求双曲正弦的弧度角 |


## 双曲正切 {#hyperbolic-tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tanh"
>title="双曲正切"
>abstract="返回某数字的双曲正切。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL HYPERBOLIC TANGENT(metric)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望求双曲正切的弧度角 |


## 如果 {#if}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-if"
>title="如果"
>abstract="如果条件参数的值非零（真），则结果为 value_if_true 参数的值。否则，它会是 value_if_false 参数的值。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL IF(logical_test, value_if_true, value_if_false)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| logical_test | 必填。任何可被计算为 TRUE 或 FALSE 的值或表达式 |
| value_if_true | 您希望在 logical_test 参数计算为 TRUE 时返回的值。（如果未包含此参数，则此参数默认为 0。） |
| value_if_false | 当 logical_test 参数的计算结果为 FALSE 时，您希望返回的值。（如果不包含，则此参数默认为 0。） |


## 小于 {#less-than}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-lt"
>title="小于"
>abstract="输出为 0（假）或 1（真）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN()]**

输出为 0（假）或 1（真）。

| 参数 | 描述 |
|---|---|
| metric_X | 要用于比较的指标。 |
| metric_Y | 要用作比较的量度。 |

### 示例

`Metric 1 < Metric 2`


## 小于或等于 {#less-than-or-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-le"
>title="小于或等于"
>abstract="小于或等于。输出为 0（假）或 1（真）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LESS THAN OR EQUAL()]**

小于或等于。输出为 0（假）或 1（真）。

| 参数 | 描述 |
|---|---|
| metric_X | 要用于比较的指标。 |
| metric_Y | 要用作比较的量度。 |

### 示例

`Metric 1 <= Metric 2`



## 提升 {#lift}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-lift"
>title="提升"
>abstract="与控制值相比，比率的提升。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 提升(normalizing-container， success-metric， control)]**

与控制值相比，比率的提升。

| 参数 | 描述 |
| --- | --- |
| 标准化容器 | 运行测试的基础（人员、会话或事件）。 |
| success-metric | 用户正在将变量与之比较的一个或多个量度。 |
| 控制 | 试验中所有其他变量要与之进行比较的变量。输入控制变量维度项的名称。 |



## 线性回归：相关系数 {#linear-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-linear"
>title="线性回归：相关系数"
>abstract="线性回归：Y = a X + b。返回相关系数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**


[!BADGE 表]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| metric_X | 您希望与 metric_Y 关联的量度 |
| metric_Y | 您希望与 metric_X 关联的量度 |
| include_zeros | 是否在计算中包含零值 |



## 线性回归：截距 {#linear-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-linear"
>title="线性回归：截距"
>abstract="线性回归：Y = a X + b。返回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE 表]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |



## 线性回归：预测的 Y {#linear-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-linear"
>title="线性回归：预测的 Y"
>abstract="线性回归：Y = a X + b。返回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |



## 线性回归：斜率 {#linear-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-linear"
>title="线性回归：斜率"
>abstract="线性回归：Y = a X + b。返回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LINEAR REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |


## 常用对数 {#log-base-ten}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log10"
>title="常用对数"
>abstract="返回某数字以 10 为底数的对数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG BASE 10(metric)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| 量度 | 您希望求以 10 为底数对数的正实数 |


## 对数回归：相关系数 {#log-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-log"
>title="对数回归：相关系数"
>abstract="对数回归：Y = a ln(X) + b。返回相关系数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望与 metric_Y 关联的量度 |
| metric_Y | 您希望与 metric_X 关联的量度 |
| include_zeros | 是否在计算中包含零值 |


## 对数回归：截距 {#log-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-log"
>title="对数回归：截距"
>abstract="对数回归：Y = a ln(X) + b。返回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |



## 对数回归：预测的 Y {#log-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-log"
>title="对数回归：预测的 Y"
>abstract="对数回归：Y = a ln(X) + b。返回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |



## 对数回归：斜率 {#log-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-log"
>title="对数回归：斜率"
>abstract="对数回归：Y = a ln(X) + b。返回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL LOG REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |



## 自然对数 {#natural-log}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-log"
>title="自然对数"
>abstract="返回某数字的自然对数。自然对数以常数 e (2.71828182845904) 为底数。LN 是 EXP 函数的反函数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL NATURAL LOG(metric)]**

返回某数字的自然对数。自然对数以常数 e (2.71828182845904) 为底数。LN 是 EXP 函数的反函数。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望求自然对数的正实数 |



## 不为 {#not}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-not"
>title="不为"
>abstract="作为布尔值的取反。输出为 0（假）或 1（真）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL NOT(logical)]**

作为布尔值的取反。输出为 0（假）或 1（真）。

| 参数 | 描述 |
|---|---|
| logical | 必填。可被计算为 TRUE 或 FALSE 的值或表达式 |



## 不等于 {#not-equal}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ne"
>title="不等于"
>abstract="不等于。输出为 0（假）或 1（真）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL NOT EQUAL()]**


不等于。输出为 0（假）或 1（真）。


| 参数 | 描述 |
|---|---|
| metric_X | 要用于比较的指标。 |
| metric_Y | 要用作比较的量度。 |

### 示例

`Metric 1 != Metric 2`


## 或 {#or}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-or"
>title="或"
>abstract="析取。不等于零被认为是真，等于零被认为是假。输出为 0（假）或 1（真）。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL OR(logical_test)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| logical_test | 至少需要一个参数，但可以接受任意数量的参数。任何可被计算为 TRUE 或 FALSE 的值或表达式 |


>[!NOTE]
>
>0（零）表示 False，而任何其他值均表示 True。


## Pi {#pi}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-pi"
>title="Pi"
>abstract="返回 Pi: 3.14159..."

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL PI()]**

返回 Pi: 3.14159...


## 幂回归：相关系数 {#power-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-power"
>title="幂回归：相关系数"
>abstract="幂回归：Y = b X ^ a. 返回相关系数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望与 metric_Y 关联的量度 |
| metric_Y | 您希望与 metric_X 关联的量度 |
| include_zeros | 是否在计算中包含零值 |



## 幂回归：截距 {#power-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-power"
>title="幂回归：截距"
>abstract="幂回归：Y = b X ^ a. 返回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**


[!BADGE 表]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |


## 幂回归：预测的 Y {#power-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-power"
>title="幂回归：预测的 Y"
>abstract="幂回归：Y = b X ^ a. 返回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |



## 幂回归：斜率 {#power-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-power"
>title="幂回归：斜率"
>abstract="幂回归：Y = b X ^ a. 返回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL POWER REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |



## 二次回归：相关系数 {#quadratic-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-quadratic"
>title="二次回归：相关系数"
>abstract="二次回归：Y = (a + bX) ^ 2，返回相关系数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望与 metric_Y 关联的量度 |
| metric_Y | 您希望与 metric_X 关联的量度 |
| include_zeros | 是否在计算中包含零值 |

## 二次回归：截距 {#quadratic-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-quadratic"
>title="二次回归：截距"
>abstract="二次回归：Y = (a + bX) ^ 2，返回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |


## 二次回归：预测的 Y {#quadratic-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-quadratic"
>title="二次回归：预测的 Y"
>abstract="二次回归：Y = (a + bX) ^ 2，返回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |


## 二次回归：斜率 {#quadratic-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-quadratic"
>title="二次回归：斜率"
>abstract="二次回归：Y = (a + bX) ^ 2，返回 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL QUADRATIC REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |



## 倒数回归：相关系数 {#reciprocal-regression-correlation-coefficient}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-corr-reciprocal"
>title="倒数回归：相关系数"
>abstract="倒数回归：Y = a + b X ^ -1。返回相关系数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: CORRELATION COEFFICIENT(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望与 metric_Y 关联的量度 |
| metric_Y | 您希望与 metric_X 关联的量度 |
| include_zeros | 是否在计算中包含零值 |


## 倒数回归：截距 {#reciprocal-regression-intercept}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-intercept-reciprocal"
>title="倒数回归：截距"
>abstract="倒数回归：Y = a + b X ^ -1。返回 a。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: INTERCEPT(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |


## 倒数回归：预测的 Y {#reciprocal-regression-predicted-y}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-pred-reciprocal"
>title="倒数回归：预测的 Y"
>abstract="倒数回归：Y = a + b X ^ -1。返回 Y。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: PREDICTED Y(metric_X, metric_Y, include_zeros)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |


## 倒数回归：斜率 {#reciprocal-regression-slope}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-ls-slope-reciprocal"
>title="倒数回归：斜率"
>abstract="倒数回归：Y = a + b X ^ -1。返回结果 b。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL RECIPROCAL REGRESSION: SLOPE(metric_X, metric_Y, include_zeros)]**

[!BADGE 表]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| metric_X | 您希望指定为从属数据的量度 |
| metric_Y | 您希望指定为独立数据的量度 |
| include_zeros | 是否在计算中包含零值 |



## 样本方差

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-waskr-variance-estimate"
>title="样本方差"
>abstract="使用公式 (sum(metric^2) / (N - 1)) - (sum(metric))^2/(N*(N-1)) 计算样本方差的估计值。其中 N 是标准化容器的计数。<br/>这可作为&#x200B;*随时有效的*&#x200B;置信度计算的一部分。一般来说，这个函数单独使用并无用处，但可用于检查计算结果或&#x200B;*手动*&#x200B;执行置信度计算。"

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL 样本变量(normalizing-container， success-metric)]**

计算样本方差的估计值。

| 参数 | 描述 |
| --- | --- |
| 标准化容器 | 运行测试的基础（人员、会话或事件）。 |
| success-metric | 用户正在将变量与之比较的一个或多个量度。 |

<!-- markdownlint-enable MD034 -->



## 正弦 {#sine}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sin"
>title="正弦"
>abstract="返回给定角的正弦。如果角以角度表示，则将该角乘以 PI( )/180。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL SINE(metric)]**


[!BADGE 行]{type="Neutral"}


| 参数 | 描述 |
|---|---|
| 量度 | 您希望求正弦的弧度角 |




## T 分数 {#t-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-score"
>title="T 分数"
>abstract="与[平均值](cm-functions.md#mean)的偏差除以标准差。[Z-Score](#z-score) 的别名。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL T-SCORE(metric, include_zeros)]**

与[平均值](cm-functions.md#mean)的偏差除以标准差。[Z-Score](#z-score) 的别名。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望求 T 分数的量度 |
| include_zeros | 是否在计算中包含零值 |


## T 测试 {#t-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-t-test"
>title="T 测试"
>abstract="执行尾长为 m 的 t 测试，其中 x 为 t 分数，n 为自由度。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL T-TEST(metric, degrees, tails)]**

执行尾长为 m 的 t 测试，其中 x 为 t 分数，n 为自由度。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望执行 T 测试的量度 |
| 度 | 自由度 |
| 尾 | 用于执行 T 测试的尾长 |

### 详细信息

签名为 T-TEST(metric, degrees, tails)。在下面，只需调用 ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-T(-ABSOLUTE VALUE(tails), degrees)]](#cdf-t)**。此函数类似于 **[Z-TEST](#z-test)** 函数，该函数运行 ***m*** ![CrossSize75](/help/assets/icons/CrossSize75.svg) **[[!DNL CDF-Z(-ABSOLUTE VALUE(tails))]](#cdf-z)**。

- ***m*** 是尾数。
- ***n*** 是自由度，对于整个报告来说应该是一个常数，也就是说不会逐行改变。
- ***x*** 为 T 测试统计数据，通常是基于量度的公式（例如 **[Z-SCORE](#z-score)**），每行都将对其进行评估。

返回值是指在给定自由度和尾数的情况下，获得测试统计数据 x 的几率。

### 示例

1. 使用函数求离群值：

   ```
   T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2)
   ```

1. 将函数与 **[IF](#if)** 结合使用，以忽略过高或过低的跳出率，并对其他内容的会话进行计数：

   ```
   IF(T-TEST(Z-SCORE(bouncerate), ROW COUNT - 1, 2) < 0.01, 0, sessions )
   ```



## 正切 {#tangent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-tan"
>title="正切"
>abstract="返回给定角的正切。如果角以角度表示，则将该角乘以 PI( )/180。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL TANGENT(metric)]**

返回给定角的正切。如果角以角度表示，则将该角乘以 PI( )/180。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望求正切的弧度角 |



## Z-Score {#z-score}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-score"
>title="Z-Score"
>abstract="与平均值的偏差除以标准差。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL Z-SCORE(metric, include_zeros)]**

[!BADGE 行]{type="Neutral"}

| 参数 | 描述 |
|---|---|
| 量度 | 您希望求 Z 分数的量度 |
| include_zeros | 是否在计算中包含零值 |

Z 分数为 0（零）表示分数与平均值相同。Z 分数可以为正数或负数，用于指示该分数在平均值之上还是之下，以及依据多少个标准偏差。

Z 分数的方程式为：

![](assets/z_score.png)

其中，***[!DNL x]*** 为原始分数，***[!DNL μ]*** 为群体平均值，***[!DNL σ]*** 为群体标准偏差。

>[!NOTE]
>
>***[!DNL μ]*** (mu) 和 ***[!DNL σ]*** (sigma) 会使用该量度自动计算。



## Z 测试 {#z-test}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-z-test"
>title="Z 测试"
>abstract="通过 x 的 z 分数，执行以 n 结尾的 z-test。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL Z-TEST(metric_tails)]**

通过 x 的 z 分数，执行以 n 结尾的 z-test。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望执行 Z 测试的量度 |
| 尾 | 用于执行 Z 测试的尾长 |

>[!NOTE]
>
>假定值为正态分布。




<!--



## AND

Returns the value of its argument. Use NOT to make sure that a value is not equal to one particular value.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
AND(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Approximate Count Distinct (dimension)

Returns the approximated distinct count of dimension items for the selected dimension. The function uses the HyperLogLog (HLL) method of approximating distinct counts.&nbsp; It is configured to guarantee the value is within 5% of the actual value 95% of the time.

```
Approximate Count Distinct (dimension)
```

|  Argument  |  |
|---|---|
|  *dimension* | The dimension for which you want the approximate distinct item count.  |

### Example Use Case

Approximate Count Distinct (customer ID eVar) is a common use case for this function.

Definition for a new 'Approximate Customers' calculated metric:

![Approximate county distinct new dimension definition showing Customer ID (eVar1)](assets/approx-count-distinct.png)

This is how the "Approximate Customers" metric could be used in reporting:

![Freeform Table showing Unique Visitors and Approximate Customers ](assets/approx-customers.png)

### Comparing Count Functions

Approximate Count Distinct() is an improvement over Count() and RowCount() functions because the metric created can be used in any dimensional report to render an approximated count of items for a separate dimension. For example, a count of customer IDs used in a Mobile Device Type report.

This function will be marginally less accurate than Count() and RowCount() because it uses the HLL method, whereas Count() and RowCount() are exact counts.

## Arc Cosine (Row)

Returns the arccosine, or inverse of the cosine, of a metric. The arccosine is the angle whose cosine is number. The returned angle is given in radians in the range 0 (zero) to pi. If you want to convert the result from radians to degrees, multiply it by 180/PI( ).

```
ACOS(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Sine (Row)

Returns the arcsine, or inverse sine, of a number. The arcsine is the angle whose sine is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arcsine in degrees, multiply the result by 180/PI( ).

```
ASIN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Arc Tangent (Row)

Returns the arctangent, or inverse tangent, of a number. The arctangent is the angle whose tangent is number. The returned angle is given in radians in the range -pi/2 to pi/2. To express the arctangent in degrees, multiply the result by 180/PI( ).

```
ATAN(metric)
```

|  Argument  |  |
|---|---|
|  *metric* | The cosine of the angle you want from -1 to 1. |

## Exponential Regression: Predicted Y (Row)

Calculates the predicted y-values (metric_Y), given the known x-values (metric_X) using the "least squares" method for calculating the line of best fit based on .

```
ESTIMATE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Cdf-T

Returns the percentage of values in a student's t-distribution with n degrees of freedom that have a z-score less than x.

```
cdf_t( -∞, n ) = 0
cdf_t(  ∞, n ) = 1
cdf_t( 3, 5 ) ? 0.99865
cdf_t( -2, 7 ) ? 0.0227501
cdf_t( x, ∞ ) ? cdf_z( x )
```

## Cdf-Z

Returns the percentage of values in a normal distribution that have a z-score less than x.

```
cdf_z( -∞ ) = 0
cdf_z( ∞ ) = 1
cdf_z( 0 ) = 0.5
cdf_z( 2 ) ? 0.97725
cdf_z( -3 ) ? 0.0013499

```

## Exponential Regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns ( *metric_X* and *metric_Y*) for

```
INTERCEPT.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Exponential Regression: Slope (Table)

Returns the slope, *a*, between two metric columns ( *metric_X* and *metric_Y*) for .

```
SLOPE.EXP(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Floor (Row)

Returns the largest integer not greater than a given value. For example, if you want to avoid reporting currency decimals for revenue and a product has $569.34, use the formula FLOOR( *Revenue*) to round revenue down to the nearest dollar, or $569.

```
FLOOR(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The metric you want to round.  |

## Greater Than

Returns items whose numeric count is greater than the value entered.

## Greater Than or Equal

Returns items whose numeric count is greater than or equal to the value entered.

## Hyperbolic Cosine (Row)

Returns the hyperbolic cosine of a number.

```
COSH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic cosine.  |

## Hyperbolic Sine (Row)

Returns the hyperbolic sine of a number.

```
SINH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic sine.  |

## Hyperbolic Tangent (Row)

Returns the hyperbolic tangent of a number.

```
TANH(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want to find the hyperbolic tanget.  |

## IF (Row)

The IF function returns one value if a condition you specify evaluates to TRUE, and another value if that condition evaluates to FALSE.

```
IF(logical_test, [value_if_true], [value_if_false])
```

|  Argument  | Description  |
|---|---|
|  *logical_test* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *[value_if_true]* | The value that you want to be returned if the *logical_test* argument evaluates to TRUE. (This argument defaults to 0 if not included.)  |
|  *[value_if_false]* | The value that you want to be returned if the *logical_test* argument evaluates to FALSE. (This argument defaults to 0 if not included.)  |

## Less Than

Returns items whose numeric count is less than the value entered.

## Less Than or Equal

Returns items whose numeric count is less than or equal to the value entered.

## Lift

Returns the Lift a particular variant had in conversions over a control variant. It is the difference in performance between a given variant and the baseline, divided by the performance of the baseline, expressed as a percentage. 

```
fx Lift (normalizing-container, success-metric, control)
```

| Argument | Description |
| --- | --- |
| Normalizing Container | The basis (People, Sessions, or Events) on which a test will be run. |
| Success Metric | The metric or metrics that a user is comparing variants with. |
| Control | The variant that all other variants in the experiment are being compared with. Enter the name of the control variant dimension item. |

{style="table-layout:auto"}

## Linear regression_ Correlation Coefficient

Y = a X + b. Returns the correlation coefficient

## Linear regression_ Intercept

Y = a X + b. Returns b.

## Linear regression_ Predicted Y

Y = a X + b. Returns Y.

## Linear regression_ Slope

Y = a X + b. Returns a.

## Log Base 10 (Row)

Returns the base-10 logarithm of a number.

```
LOG10(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the base-10 logarithm.  |

## Log regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the CORREL equation.

```
CORREL.LOG(metric_X,metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Log regression: Intercept (Table)

Returns the intercept *b* as the least squares regression between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the INTERCEPT equation.

```
INTERCEPT.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log Regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the "least squares" method for calculating the line of best fit based on [!DNL Y = a ln(X) + b]. It is calculated using the ESTIMATE equation.

In regression analysis, this function calculates the predicted [!DNL y] values (*metric_Y*), given the known [!DNL x] values (*metric_X*) using the logarithm for calculating the line of best fit for the regression equation [!DNL Y = a ln(X) + b]. The [!DNL a] values correspond to each x value, and [!DNL b] is a constant value.

```
ESTIMATE.LOG(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Log regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for the regression equation [!DNL Y = a ln(X) + b]. It is calculated using the SLOPE equation.

```
SLOPE.LOG(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the independent data.  |

## Natural Log

Returns the natural logarithm of a number. Natural logarithms are based on the constant *e* (2.71828182845904). LN is the inverse of the EXP function.

```
LN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The positive real number for which you want the natural logarithm.  |

## NOT

Returns 1 if the number is 0 or returns 0 if another number.

```
NOT(logical)
```

|  Argument  | Description  |
|---|---|
|  *logical* | Required. A value or expression that can be evaluated to TRUE or FALSE.  |

Using NOT requires knowing if the expressions (<, >, =, <> , etc.) return 0 or 1 values.

## Not equal

Returns all items that do not contain the exact match of the value entered.

## Or (Row)

Returns TRUE if any argument is TRUE, or returns FALSE if all arguments are FALSE.

>[!NOTE]
>
>0 (zero) means False, and any other value is True.

```
OR(logical_test1,[logical_test2],...)
```

|  Argument  | Description  |
|---|---|
|  *logical_test1* | Required. Any value or expression that can be evaluated to TRUE or FALSE.  |
|  *logical_test2* | Optional. Additional conditions that you want to evaluate as TRUE or FALSE  |

## Pi

Returns the constant PI, 3.14159265358979, accurate to 15 digits.

```
PI()
```

The [!DNL PI]function has no arguments.

## Power regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
CORREL.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Power regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
 INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values ( [!DNL metric_Y]), given the known [!DNL x] values ( [!DNL metric_X]) using the "least squares" method for calculating the line of best fit for [!DNL Y = b*X].

```
 ESTIMATE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Power regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = b*X].

```
SLOPE.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
CORREL.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Quadratic regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y=(a*X+b)]****.

```
INTERCEPT.POWER(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Quadratic regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y=(a*X+b)]**** .

```
ESTIMATE.QUADRATIC(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_A* | A metric that you would like to designate as the dependent data.  |
|  *metric_B* | A metric that you would like to designate as the dependent data.  |

## Quadratic regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and metric_Y) for [!DNL Y=(a*X+b)]****.

```
SLOPE.QUADRATIC(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Correlation coefficient (Table)

Returns the correlation coefficient, *r*, between two metric columns (*metric_X)* and *metric_Y*) for [!DNL Y = a/X+b].

```
CORREL.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to correlate with *metric_Y*.  |
|  *metric_Y* | A metric that you would like to correlate with *metric_X*.  |

## Reciprocal regression: Intercept (Table)

Returns the intercept, *b*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
INTERCEPT.RECIPROCAL(metric_A, metric_B)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Predicted Y (Row)

Calculates the predicted [!DNL y] values (metric_Y), given the known [!DNL x] values (metric_X) using the least squares method for calculating the line of best fit using [!DNL Y = a/X+b].

```
ESTIMATE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Reciprocal regression: Slope (Table)

Returns the slope, *a*, between two metric columns (*metric_X* and *metric_Y*) for [!DNL Y = a/X+b].

```
SLOPE.RECIPROCAL(metric_X, metric_Y)
```

|  Argument  | Description  |
|---|---|
|  *metric_X* | A metric that you would like to designate as the dependent data.  |
|  *metric_Y* | A metric that you would like to designate as the independent data.  |

## Sine (Row)

Returns the sine of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
SIN(metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the sine.  |

## T-Score

Alias for Z-Score, namely the deviation from the mean divided by the standard deviation

## T-Test

Performs an m-tailed t-test with t-score of col and n degrees of freedom.

The signature is `t_test( x, n, m )`. Underneath, it simply calls `m*cdf_t(-abs(x),n)`. (This is similar to the z-test function which runs `m*cdf_z(-abs(x))`.

Here, `m` is the number of tails, and `n` is the degrees of freedom. These should be numbers (constant for the whole report, i.e. not changing on a row by row basis).

`X` is the t-test statistic, and would often be a formula (e.g. zscore) based on a metric and will be evaluated on every row.

The return value is the probability of seeing the test statistic x given the degrees of freedom and number of tails.

**Examples:**

1. Use it to find outliers:

   ```
   t_test( zscore(bouncerate), row-count-1, 2)
   ```

1. Combine it with `if` to ignore very high or low bounce rates, and count visits on everything else:

   ```
   if ( t_test( z-score(bouncerate), row-count, 2) < 0.01, 0, visits )
   ```

## Tangent

Returns the tangent of the given angle. If the angle is in degrees, multiply the angle by PI( )/180.

```
TAN (metric)
```

|  Argument  | Description  |
|---|---|
|  *metric* | The angle in radians for which you want the tangent.  |

## Z-Score (Row)

Returns the Z-score, or normal score, based upon a normal distribution. The Z-score is the number of standard deviations an observation is from the mean. A Z-score of 0 (zero) means the score is the same as the mean. A Z-score can be positive or negative, indicating whether it is above or below the mean and by how many standard deviations.

The equation for Z-score is:

![](assets/z_score.png)

where [!DNL x] is the raw score, [!DNL μ] is the mean of the population, and [!DNL σ] is the standard deviation of the population.

>[!NOTE]
>
>[!DNL μ] (mu) and[!DNL σ] (sigma) are automatically calculated from the metric.

Z-score(metric)

<table id="table_AEA3622A58F54EA495468A9402651E1B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Argument </th>
   <th colname="col2" class="entry"> Description </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> <i>metric</i> </td>
   <td colname="col2"> <p> Returns the value of its first non-zero argument. </p> </td>
  </tr>
 </tbody>
</table>

## Z-Test

Performs an n-tailed Z-test with Z-score of A.

Returns the probability that the current row could be seen by chance in the column.

>[!NOTE]
>
>Assumes that the values are normally distributed.

-->