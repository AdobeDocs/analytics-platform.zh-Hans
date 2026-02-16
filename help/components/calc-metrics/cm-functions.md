---
title: 基本函数
description: 了解基本计算量度函数。
feature: Calculated Metrics
exl-id: 63775753-337b-4dec-a3a2-a3a0ee9aac2e
role: User
source-git-commit: 211f0411d0bf70288cbd46bb219fce7ae99fe03d
workflow-type: tm+mt
source-wordcount: '3599'
ht-degree: 48%

---

# 基本功能


使用[计算量度生成器](cm-workflow/cm-build-metrics.md)可以应用统计和数学函数。本文按字母顺序列出了这些函数及其定义。

>[!NOTE]
>
>当 [!DNL metric] 被标识为函数中的参数时，还允许使用其他量度表达式。例如，[COLUMN MAXIMUM(METRICS)](#column-maximum)还允许[COLUMN MAXIMUM(PageViews + Sessions)](#column-maximum)。



## 表函数与行函数

table函数是其中表的每一行的输出都相同的函数。 行函数是指其中表的每一行的输出都不同的函数。

在适用且相关的情况下，函数具有函数类型注释：[!BADGE 表]{type="Neutral"}或[!BADGE 行]{type="Neutral"}

## Include-Zeros 参数的含义是什么？

它可告知计算中是否包含零。零有时表示&#x200B;*无*，有时又十分重要。

例如，如果您有收入量度，然后又将页面查看次数量度添加到报告中，则您的收入会突然多出一些全部为零的行。您可能不希望该附加量度影响收入栏中的任何&#x200B;**[平均值](cm-functions.md#mean)**、**[行最小值](cm-functions.md#row-min)**、**[四分位数](cm-functions.md#quartile)**&#x200B;以及其他计算。在这种情况下，您需要检查 `include-zeros` 参数。

另一种情况是，您有两个感兴趣的量度，其中一个量度的平均值或最小值较高，因为其中有些行为零。在这种情况下，您可以选择不检查参数，以包含零



## 绝对值 {#absolute-value}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-abs"
>title="绝对值"
>abstract="返回某数字的绝对值。某数字的绝对值是一个具有正值的数字。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL ABSOLUTE VALUE(metric)]**

[!BADGE Row]{type="Neutral"} 返回某数字的绝对值。某数字的绝对值是一个具有正值的数字。

| 参数 | 描述 |
|---|---|
| 量度 | 您想要计算绝对值的量度。 |

**用例**：在分析可能产生负值的量度（如收入增量或百分比变化）时，请确保所有结果均为正。 这有助于关注变化的幅度，而不考虑方向。

**在计算指标生成器**&#x200B;中：将指标或表达式包裹在&#x200B;**绝对值**&#x200B;函数中，例如： **绝对值**（当前收入 — 以前的收入）。 这会将任何负差异转换为正值。

>[!TIP]
>
>使用此选项可测量两个时间段或区段之间的绝对差异，无论性能是增加还是减少。
>

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
| 量度 | 至少需要一个量度，但可以将任意数量的量度作为参数。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：确定划分中的最高值，例如访问次数最多的日期或收入最高的产品。 这有助于突出不同类别中的最佳性能。

**在计算量度生成器**&#x200B;中：按&#x200B;**天**&#x200B;或&#x200B;*产品*&#x200B;划分时，将&#x200B;*列最大值*&#x200B;应用于诸如&#x200B;*收入*&#x200B;或&#x200B;*会话*&#x200B;之类的量度。 该函数返回该列中每一行的最大值。

>[!TIP]
>
>使用[IF](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if)语句(如&#x200B;**IF**(*Revenue* = **列最大值***(Revenue*)， 1， 0))突出显示划分中表现最佳的项。
>

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
| 量度 | 至少需要一个量度，但可以将任意数量的量度作为参数。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：标识划分中表现最差的值，例如转化次数最少的促销活动或收入最低的日期。 这有助于快速显示性能不佳的区段。

**在计算量度生成器**&#x200B;中：按&#x200B;**促销活动**&#x200B;或&#x200B;*天*&#x200B;划分时，将&#x200B;*列最小值*&#x200B;应用于诸如&#x200B;*收入*&#x200B;或&#x200B;*转化率*&#x200B;之类的量度。 该函数返回该列中每行的最小值。

>[!TIP]
>
>使用[IF](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-adv-functions#if)语句(如&#x200B;**IF**(*Revenue* = **列最小值***(Revenue*)， 1， 0))突出显示划分中性能最低的项目。
>


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
| 量度 | 至少需要一个量度，但可以将任意数量的量度作为参数。 |

**用例**：计算划分中所有值的总计，例如所有产品的总收入或所有天的总访问次数。 当需要总计与单个行值进行比较时，这很有用。

**在计算量度生成器**&#x200B;中：在按&#x200B;**产品**&#x200B;或&#x200B;*天*&#x200B;划分时，将&#x200B;*列总和*&#x200B;应用于诸如&#x200B;*收入*&#x200B;或&#x200B;*会话*&#x200B;之类的量度。 此函数返回该列中每一行所有值的总和。

>[!TIP]
>
>当需要引用整体总计以计算份额或总绩效的百分比时使用。
>


## 计数 {#count}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-count"
>title="计数"
>abstract="返回列中某量度的非零值的数量或计数（某个维度内报告的独特元素数）。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL COUNT(metric)]**

[!BADGE Table]{type="Neutral"} 返回列中某量度的非零值的数量或计数（某个维度内报告的独特元素数）。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计数的量度。 |

**用例**：计算计算中包含的数据点数，如日期范围内的天数或细分中的产品数。 当您需要了解聚合值中涉及的项数时，这项功能会很有用。

**在计算量度生成器**&#x200B;中：将&#x200B;**计数**&#x200B;应用于&#x200B;*会话*&#x200B;或&#x200B;*收入*&#x200B;之类的量度以返回当前细分或日期范围中包含的行总数（或数据点）。

>[!TIP]
>
>与&#x200B;**列Sum**&#x200B;一起使用手动计算平均值(例如，**列Sum**（*收入*） / **计数**（收入）)。
>

## 指数 {#exponent}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-exp"
>title="指数"
>abstract="返回 e 的给定次幂。常量 e 等于 2.71828182845904，它是自然对数的底数。EXPONENT 是 LN 的反函数，LN 是某数字的自然对数。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL EXPONENT(metric)]**

[!BADGE 行]{type="Neutral"}返回&#x200B;*e*，其幂为给定数字。 常数&#x200B;*e*&#x200B;等于2.71828182845904，为自然对数的底数。 EXPONENT 是 LN 的反函数，LN 是某数字的自然对数。

| 参数 | 描述 |
|---|---|
| 量度 | 应用于基&#x200B;*e*&#x200B;的指数。 |

**用例**：将&#x200B;*e*&#x200B;提升到给定数字或量度的幂。 在为增长趋势建模或按指数级缩放量度时，这非常有用。

计算量度生成器&#x200B;**中的**：将&#x200B;**指数**&#x200B;与量度一起使用。 例如：**指数**（*会话*）将&#x200B;*e*&#x200B;提升到&#x200B;*会话*&#x200B;量度的幂。

>[!TIP]
>
>与&#x200B;**对数**&#x200B;结合使用以进行高级建模，或在比较增长模式时平滑高度可变的数据。
>


## 平均值 {#mean}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-mean"
>title="平均值"
>abstract="返回列中某量度的算术平均值或平均数"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MEAN(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} 返回列中某量度的算术平均值或平均数。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算平均数的量度。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：计算一组值的算术平均值，例如平均每日收入或每个营销活动的平均访问次数。 这有助于建立比较数据集内各个值的基线。

**在计算量度生成器中**：将&#x200B;**平均值**&#x200B;应用于&#x200B;*收入*&#x200B;或&#x200B;*会话*&#x200B;之类的量度，以返回选定划分或日期范围内所有数据点的平均值。

>[!TIP]
>
>用于了解总体性能趋势，或将其与&#x200B;**标准偏差**&#x200B;结合使用，以测量平均值的一致性。
>

## 中间值 {#median}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-median"
>title="中间值"
>abstract="返回列中某量度的中间值。中间值是位于一组数字中间的数字。也就是说，一半的数字大于或等于中间值，一半的数字小于或等于中间值。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL MEDIAN(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} 返回列中某量度的中间值。中间值是位于一组数字中间的数字。也就是说，一半的数字大于或等于中间值，一半的数字小于或等于中间值。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算中位数的量度。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：标识一组数据中的中间值，如每日收入中值或每次访问页面查看次数中值。 当您想要减少离群值的影响并查看数据的中心趋势时，这非常有用。

**在计算量度生成器中**：将中间值应用于收入或页面查看等量度，以返回选定划分或日期范围内所有数据点的中间值。

>[!TIP]
>
>当您的数据包含可能会扭曲平均值的极端高低时，请使用而不是&#x200B;**平均值**。
>


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
| metric_X | 您想要划分的第一个量度。 |
| metric_Y | 您想要划分的第二个量度。 |

**用例**：将一个数字除以另一个数字后返回余数。 这对于循环或重复模式很有用，例如按顺序识别第n天或营销活动。

计算量度生成器&#x200B;**中的**：将&#x200B;**Modulo**&#x200B;与两个数字输入一起使用。 例如： **Modulo**(*Day Number*， 7)将天数除以七后返回余数，这有助于按周对数据进行分组。

>[!TIP]
>
>与条件逻辑结合使用，以突出显示重复间隔或根据重复周期分段数据。
>

### 更多示例

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

[!BADGE Table]{type="Neutral"} 返回第 n 个百分位数，即 0 至 100 之间的值。当 n &lt; 0 时，该函数使用零。当 n > 100 时，该函数返回 100。

| 参数 | 描述 |
|---|---|
| 量度 | 介于 0 到 100 之间（包括 0 和 100）的百分位数值。 |
| k | 用于定义相对位置的量度列。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：确定给定百分比的数据点低于哪个值，如每日收入或页面查看的第90个百分位数。 这有助于测量分布并检测高性能的离群值。

**在计算量度生成器**&#x200B;中：将&#x200B;**百分位数**&#x200B;应用于&#x200B;*收入*&#x200B;或&#x200B;*会话*&#x200B;之类的量度，并指定所需的百分位值(例如，**百分位数**（*收入*， 90）)。 结果表明，90%的数据点低于阈值。

>[!TIP]
>
>使用设置绩效基准或筛选表现最佳的天数、促销活动或产品。
>

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
| metric_X | 您想要计算其 metric_Y 次方的量度。 |
| metric_Y | 您想要将 metric_X 提升到的次方。 |

**用例**：将一个数字或量度提升为另一个数字或量度的幂，例如平方值或应用指数权重。 在建模增长、缩放值或执行高级数学转换时，这非常有用。

计算量度生成器&#x200B;**中的**：在两个数值或量度之间使用&#x200B;**乘幂运算符**。 例如：*Revenue* ^ 2将&#x200B;*Revenue*&#x200B;值提高到次幂。

>[!TIP]
>
>与&#x200B;**指数**&#x200B;函数类似，但以数学运算符表示，允许计算量度中包含更简洁的公式。
>

## 四分位数 {#quartile}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-quartile"
>title="四分位数"
>abstract="返回某量度的四分位数形式的值。例如，四分位数可用于查找在获得的收入方面排名前 25% 的产品。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL QUARTILE(metric, quartile, include_zeros)]**

[!BADGE Table]{type="Neutral"} 返回某量度的四分位数形式的值。例如，四分位数可用于查找在获得的收入方面排名前 25% 的产品。当四分位数分别等于 `0`（零）、`2` 和 `4` 时，[COLUMN MINIMUM](#column-minimum), [MEDIAN](#median) 和 [COLUMN MAXIMUM](#column-maximum) 返回与 [QUARTILE](#quartile) 相同的值。

| 参数 | 描述 |
|---|---|
| 量度 | 您想要计算四分位数值的量度。 |
| 四分位数 | 指示要返回哪个四分位数值。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：将数据集分为四个相等的部分，以了解值的分配方式，例如按收入或访问确定前25%的天数。 这有助于将性能划分到排名组中，以便进行更深入的比较。

**在计算量度生成器中**：将&#x200B;**Quartile**&#x200B;应用于&#x200B;*Revenue*&#x200B;或&#x200B;*Sessions*&#x200B;之类的量度，并指定要返回的四分位数(例如，**Quartile**(*Revenue*， 3)以查找第三个四分位数或前25%的阈值)。

>[!TIP]
>
>使用将值分组为性能层，例如低、中和高性能的营销活动或产品。
>

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

**用例**：通过将数值结果四舍五入到指定的小数位数来简化数值结果。 这有助于创建更简洁的可视化图表或使计算量度更容易在报表中读取。

在计算量度生成器&#x200B;**中**：将&#x200B;**Round**&#x200B;应用于量度或表达式，并指定小数位数。 例如： **Round**（*转化率*， 2）将值舍入到两位小数。

>[!TIP]
>
>用于标准化报表中的量度格式，尤其是在显示百分比或货币值时。
>

### 更多示例

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

**用例**：计算划分或数据集中返回的总行数，如报表中包含的天数、促销活动或产品。 这有助于了解有多少项目对您的分析做出了贡献。

计算量度生成器&#x200B;**中的**：应用&#x200B;**行计数**&#x200B;以返回当前划分或区段中的总行数。 例如，当按&#x200B;*产品*&#x200B;查看&#x200B;*收入*&#x200B;时，**行数**&#x200B;返回显示的产品数。

>[!TIP]
>
>与其他函数（如&#x200B;**列Sum**）一起使用，手动计算平均值(如&#x200B;**列Sum**（*收入*） / **行计数**())。
>

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
| 量度 | 至少需要一个量度，但可以将任意数量的量度作为参数。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：确定一行中所有量度的最大值，例如确定哪个量度（例如，*收入*、*订单*&#x200B;或&#x200B;*会话*）在特定日期或区段中具有最大值。 这有助于突出显示每行数据中的潜在量度。

计算量度生成器&#x200B;**中的**：在一个计算量度中包含多个量度时应用&#x200B;**行最大值**。 例如：**行最大值**（*收入*，*订单*，*会话*）返回每行的这些量度中的最大值。

>[!TIP]
>
>使用可并排比较相关量度，并确定哪一因素对每行性能的影响最大。
>

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
| 量度 | 至少需要一个量度，但可以将任意数量的量度作为参数。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：确定一行中所有量度的最小值，例如找出哪个量度（例如，*收入*、*订单*&#x200B;或&#x200B;*会话*）在特定日期或区段具有最小值。 这有助于找出每行数据中表现最弱的量度。

计算量度生成器&#x200B;**中的**：比较多个量度时应用&#x200B;**行最小值**。 例如：**行最小值**（*收入*，*订单*，*会话*）返回每行的这些量度中的最小值。

>[!TIP]
>
>与“行最大值”结合使用，以计算性能范围或在并排比较中突出显示性能不佳的量度。
>

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
| 量度 | 至少需要一个量度，但可以将任意数量的量度作为参数。 |

**用例**：将单个行中多个量度的值相加，例如将&#x200B;*Revenue*&#x200B;和&#x200B;*Tax*&#x200B;相加来计算总事务值，或组合来自不同来源的&#x200B;*会话*。 这有助于将相关的量度整合在一起。

计算量度生成器&#x200B;**中的**：应用&#x200B;**行总和**&#x200B;以组合多个量度。 例如：**Row Sum**(*Revenue*， *Tax*)将这两个量度添加到细分中的每一行。

>[!TIP]
>
>用于创建组合总计或将相关的绩效指标分组到单个计算量度中。
>

## 平方根 {#square-root}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-sqrt"
>title="平方根"
>abstract="返回某数字的正平方根。某数字的平方根是该数字二分之一次幂的值。"

<!-- markdownlint-enable MD034 -->


![效果](/help/assets/icons/Effect.svg) **[!UICONTROL SQUARE ROOT(metric, include_zeros)]**

[!BADGE Row]{type="Neutral"} 返回某数字的正平方根。某数字的平方根是该数字二分之一次幂的值。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算平方根的量度。 |

**用例**：返回数字或量度的平方根，例如，在计算标准偏差或标准化数据集中的值时查找方差的根。 这对于高级统计或数据转换计算非常有用。

计算量度生成器&#x200B;**中的**：将&#x200B;**平方根**&#x200B;应用于量度或表达式。 例如： **平方根**(方差（*收入*）)返回&#x200B;*收入*&#x200B;的标准偏差。

>[!TIP]
>
>在需要按比例缩放指标或支持其他依赖根值的统计函数时使用。
>

## 标准偏差 {#standard-deviation}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-stdev"
>title="标准偏差"
>abstract="基于数据的抽样群体，返回变量的标准偏差或平方根。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL STANDARD DEVIATION(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} 基于数据的抽样群体，返回变量的标准偏差或平方根。

| 参数 | 描述 |
|---|---|
| | 您想要计算标准差的量度。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：测量值与平均值差异的程度，例如，评估日收入或访问量在一段时间内的一致程度。 这有助于识别性能的波动性、稳定性或异常波动。

**在计算量度生成器**&#x200B;中：将&#x200B;**标准偏差**&#x200B;应用于&#x200B;*收入*&#x200B;或&#x200B;*会话*&#x200B;之类的量度以计算选定划分或日期范围内的值分布。 例如：**标准偏差**（*收入*）显示每日收入与平均值的偏差量。

>[!TIP]
>
>与&#x200B;*Mean*&#x200B;一起使用，以检测异常或比较营销活动、产品或区段之间的性能一致性。
>

## 变量 {#variance}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="functions-variance"
>title="变量"
>abstract="基于数据的抽样群体返回变量。"

<!-- markdownlint-enable MD034 -->

![效果](/help/assets/icons/Effect.svg) **[!UICONTROL VARIANCE(metric, include_zeros)]**

[!BADGE Table]{type="Neutral"} 基于数据的抽样群体返回变量。

| 参数 | 描述 |
|---|---|
| 量度 | 您希望计算变量的量度。 |
| include_zeros | 是否在计算中包含零值。 |

**用例**：测量数据集中的值从平均值分布到多远，例如分析随着时间的变化有多少每日收入或会话持续时间。 这有助于量化性能的一致性或波动程度。

**在计算量度生成器**&#x200B;中：将&#x200B;**变量**&#x200B;应用于诸如&#x200B;*收入*&#x200B;或&#x200B;*每次访问逗留时间*&#x200B;之类的量度，以计算与平均值的平均平方偏差。 例如：**差异**（*收入*）显示所选范围内的收入值与平均值的差异。

>[!TIP]
>
>请配合&#x200B;**标准偏差**&#x200B;使用，以更好地了解数据可变性并识别性能不可预测的区域。
>

VARIANCE 的方程式为：

![](assets/variance_eq.png){width="100"}

其中 *x* 为抽样平均值，[MEAN(*metric*)](#mean)，*n* 为抽样大小。


为了计算变量，需要查看整列数字。首先，从该数字列表计算平均值。得出平均值后，浏览每个条目，然后执行以下操作：

1. 从数字中减去平均值。

1. 将结果求平方。

1. 再相加求和。

对整列进行迭代后，您将得到一个总数。然后，将该总数除以列中的项目数。 该数字是列的方差。 这是一个数字。 但是，它会显示为一列数字。

在以下三项列的示例中：

| 列 |
|:---:|
| 1 |
| 2 |
| 3 |

此列的平均值为2。 此列的变量将为 ((1 - 2)<sup>2</sup> + (2 - 2)<sup>2</sup> + (3 - 2)<sup>2</sup>/3 = 2/3。

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

Returns the median for a metric in a column. The median is the number in the middle of a set of numbers-that is, half the numbers have values that are greater than or equal to the median, and half are less than or equal to the median.

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