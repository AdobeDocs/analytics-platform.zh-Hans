---
title: 趋势分析
description: 随着时间的推移衡量用户参与度。
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '781'
ht-degree: 6%

---

# [!UICONTROL 趋势] 分析 {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_trends_button"
>title="趋势"
>abstract="随着时间的推移衡量用户参与度。"

<!-- markdownlint-enable MD034 -->

![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL Trends]**&#x200B;分析可针对产品性能或用户在一段时间内的行为提供宝贵的见解。 此报告的水平轴是一个时间间隔，而垂直轴测量所需的事件。

>[!VIDEO](https://video.tv.adobe.com/v/3421666/?learn=on)

## 用例

此分析的用例包括：

* **评估产品性能**：趋势允许您评估给定时间段内产品的总体性能。 通过分析用户参与度、采用率或转化率等量度，您可以确定产品性能是提高、停滞还是下降。
* **功能采用**：趋势允许您了解用户如何采用您发布的新功能或更新。 您可以确定哪些功能最受欢迎以及哪些功能需要改进。 通过此信息，您可以根据哪些功能来制定数据驱动型决策，从而确定开发工作的优先级。
* **用户行为**：趋势可以提供有关用户行为随时间变化的洞察。 通过检查用户执行的特定操作，您可以识别用户可能流失的模式。 您可以将此分析中的见解与[漏斗](funnel.md)相结合，以获得有关行为的更多见解。
* **A/B测试和实验**：如果您在产品中运行A/B测试，则可以使用趋势来衡量哪些测试随着时间的推移最成功。

## 界面

有关引导式分析界面的概述，请参阅[界面](../overview.md#interface)。 以下设置特定于此分析：

### 查询边栏

利用查询边栏，可配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[频率](frequency.md)之间切换。
* **[!UICONTROL 事件和量度]**：要测量的事件或量度。 每个选择都表示为图表系列和表格行。 无法在查询中组合事件和量度；一旦您进行了第一次选择，其余查询选择必须属于同一类型。 您最多可以包括5个选项。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。选项包括事件、会话、用户、用户百分比、每个会话的事件和每个用户的事件。 计为选项仅适用于事件查询，因量度查询而被删除。
* **[!UICONTROL 区段]**：您要测量的区段。每个选定区段都会使图表系列和表行的数量加倍。 您最多可以包含五个区段。
* **[!UICONTROL 划分属性]**：按选定属性的值划分图表系列和表行。 支持单个划分属性。 表中显示前20个值，最多可以在图表中查看10个值。 通过切换![显示隐藏图标](../assets/hide-in-chart.png)图标，可以隐藏或显示图表中的行。

### 图表设置

[!UICONTROL 趋势]分析提供了以下图表设置，可在图表上方的菜单中调整这些设置：

* **[!UICONTROL 图表类型]**：要使用的可视化图表类型。 选项包括折线图、条形图、栈叠条形图和栈叠面积图。

### 叠加

向图表添加其他数据。 当图表上显示多个系列时，叠加仅显示在悬停上。

* **[!UICONTROL 异常检测]**：对趋势分析运行[异常检测](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)。 离群值显示为圆点，您可以将光标悬停在这些圆点上以获取更多信息。
* **[!UICONTROL 趋势线叠加]**：向图表添加趋势线，这有助于在数据中描绘更清晰的模式。
   * [!UICONTROL 线性]：创建一条直的回归线。 最适合以稳定速率增加或减少的简单线性数据。 方程式：`y = a + b * x`
   * [!UICONTROL 对数]：创建曲线回归线。 最适合快速增加或减少的数据，然后变得更加均衡。 方程式：`y = a + b * log(x)`
   * [!UICONTROL 均线]：根据一组平均值创建平滑趋势线。 均线也称为滚动平均值，它使用特定数量的以前数据点（由您的选择确定），对其求平均值，并将平均值用作折线中的点。 示例包括7天均线或4周均线。 可用的移动平均值选项取决于您选择的间隔和日期范围。

### 时间比较

{{apply-time-comparison}}


### 日期范围

分析所需的日期范围。 此设置包含两个组件：

* **[!UICONTROL 时间间隔]**：要查看趋势数据的日期粒度。 有效选项包括每小时、每天、每周、每月和每季度。 相同日期范围可以有不同的时间间隔，这会影响图表中的数据点数和表中的列数。 例如，查看具有每日粒度的跨三天的分析将只显示三个数据点，而具有每小时粒度的跨三天的分析将显示72个数据点。
* **[!UICONTROL 日期]**：开始和结束日期。 您可以为方便起见，使用滚动日期范围预设和以前保存的自定义范围，也可以使用日历选择器来选择固定日期范围。


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->