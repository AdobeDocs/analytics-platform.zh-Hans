---
title: 趋势分析
description: 随着时间的推移衡量用户参与度。
exl-id: b632475f-371e-4156-9ffc-b138325aa120
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
role: User
source-git-commit: e42f04eaa06a761803e76b64a5a16674fb4af57d
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 92%

---

# [!UICONTROL 趋势]分析 {#trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_trends_button"
>title="趋势"
>abstract="随着时间的推移衡量用户参与度。"

<!-- markdownlint-enable MD034 -->

![GraphTrend](/help/assets/icons/GraphTrend.svg) **[!UICONTROL 趋势]**&#x200B;分析提供了关于产品绩效或用户行为随时间变化的宝贵洞察。该报告的横轴是时间间隔，而纵轴衡量的是您所期望的事件。


>[!VIDEO](https://video.tv.adobe.com/v/3421666/?quality=12&learn=on)

## 用例

该分析的用例包括：

* **评估产品性能**：通过了解趋势，您可以评估产品在给定时间内的整体绩效。通过分析用户参与度、采用率或转化率等量度，您可以确定产品的绩效是正在提高、停滞不前还是正在下降。
* **功能采用**：通过查看趋势，您可以了解到用户采用您发布的新功能或更新的情况。您可以确定哪些功能很受欢迎，以及哪些功能需要改进。这些信息可以帮助您根据数据做出决策，以确定优先开发哪些功能。
* **用户行为**：趋势可以提供对用户行为随时间变化的洞察。通过检查用户采取的具体操作，您可以识别用户可能流失的模式。您可以将通过此分析得出的洞察与[漏斗](funnel.md)相结合，以获得更多有关行为的洞察。
* **A/B 测试和实验**：如果您在产品内运行 A/B 测试，则可以使用趋势来判断哪些测试随着时间的推移最为成功。

## 界面

请参阅[界面](../overview.md#interface)，了解引导分析界面的概述。以下设置专用于此分析：

### 查询边栏

查询边栏允许您配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[频率](frequency.md)之间切换。
* **[!UICONTROL 事件和量度]**：您想要衡量的事件或量度。每项选择都以图表系列和表格行来表示。在查询中，事件和量度不能组合在一起；一旦您进行了第一次选择，剩余的查询选择必须属于同一类型。最多可以包括五项选择。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。 <ul><li>**[!UICONTROL 选项]**&#x200B;包括[!UICONTROL 用户]、[!UICONTROL 事件]、[!UICONTROL 会话]、[!UICONTROL 用户百分比]、每个会话的[!UICONTROL 事件]和每个用户的[!UICONTROL 事件]。</li><li>[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}其他&#x200B;**[!UICONTROL B2B选项]**&#x200B;可用于Customer Journey Analytics B2B edition： [!UICONTROL 全局帐户]，[!UICONTROL 帐户]，[!UICONTROL 购买团体]，[!UICONTROL 机会]，[!UICONTROL 全局帐户百分比]，[!UICONTROL 帐户百分比]，[!UICONTROL 购买团体百分比]，[!UICONTROL 机会百分比]，[!UICONTROL 每个全球帐户的事件]，[!UICONTROL 每个全球帐户的事件帐户]、每个购买团体的[!UICONTROL 个事件]和每个机会的[!UICONTROL 个事件]。</li></ul>计为选项仅适用于事件查询，并在量度查询中会被移除。
* **[!UICONTROL 区段]**：您要测量的区段。每个选定的区段都会使图表系列和表格行的数量加倍。最多可以包括五个区段。
* **[!UICONTROL 细分属性]**：根据所选属性的值细分图表系列和表格行。支持单一细分属性。表中显示前 20 个值，在图表中最多可查看 10 个值。您可以通过切换![显示隐藏图标](../assets/hide-in-chart.png)图标来隐藏或显示图表中的某一行。

### 图表设置

[!UICONTROL 趋势]分析提供以下图表设置，这些设置可在图表上方的菜单中进行调整：

* **[!UICONTROL 图表类型]**：您想要使用的可视化类型。相关选项包括线形图、条形图、堆积条形图和堆积面积图。

### 叠加图

向图表添加附加数据。当图表上显示多个系列时，仅在悬停时显示叠加图。

* **[!UICONTROL 异常检测]**：对趋势分析运行[异常检测](/help/analysis-workspace/c-anomaly-detection/anomaly-detection.md)。离群值以点状显示，您可以将鼠标悬停其上以获取更多信息。
* **[!UICONTROL 趋势线叠加]**：在图表中添加趋势线，有助于更清晰地描绘数据中的图案。
   * [!UICONTROL 线形图]：创建直线回归线。最适合以稳定速率增加或减少的简单线性数据。方程式：`y = a + b * x`
   * [!UICONTROL 对数]：创建一条弯曲的回归线。最适合快速增加或减少然后变得更加平稳的数据。方程式：`y = a + b * log(x)`
   * [!UICONTROL 均线]：根据一组平均值创建平滑的趋势线。均线也称为滚动平均值，使用特定数量的先前数据点（由您的选择决定），对其求平均值，然后使用平均值作为线条中的点。示例包括七天均线或四周均线。可用的均线选项取决于您选择的间隔和日期范围。

### 时间比较

{{apply-time-comparison}}


### 日期范围

您需要分析的日期范围。此设置包含两个部分：

* **[!UICONTROL 间隔]**：您想要查看趋势数据的日期粒度。有效的选项包括每小时、每天、每周、每月和每季度。相同的日期范围可以有不同的间隔，这会影响图表中的数据点数和表格中的列数。例如，以每日粒度查看跨越三天的分析仅会显示三个数据点，而以每小时粒度查看跨越三天的分析则会显示 72 个数据点。
* **[!UICONTROL 日期]**：开始和结束日期。为方便您使用，我们提供滚动日期范围预设以及之前保存的自定义范围，或者您可以使用日程表选择器选择固定的日期范围。


<!--

## Example

See below for an example of the analysis.

![Trends compare](../assets/trends-compare.png)

-->