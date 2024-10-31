---
title: 转化趋势分析
description: 跟踪转化率随时间的变化。
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 7%

---

# [!UICONTROL 转化趋势] 分析 {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_conversiontrends_button"
>title="转化趋势"
>abstract="跟踪转化率随时间发生的变化。"

<!-- markdownlint-enable MD034 -->


![转化趋势](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL 转化趋势]**&#x200B;分析提供了转化率随时间变化的趋势可视化图表。 水平轴是一个时间间隔，而垂直轴表示转化率。


>[!VIDEO](https://video.tv.adobe.com/v/3421662/?learn=on)


## 用例

此分析的用例包括：

* **跟踪优化工作**：在使用[漏斗](funnel.md)分析确定要改善的关键瓶颈后，您可以使用此分析来跟踪这些优化如何随时间影响转化率。
* **A/B测试评估**：评估在漏斗环境中进行的A/B测试或试验的有效性。 通过比较不同变体之间的转化率，您可以轻松确定哪些测试提供了较高的转化率，从而做出有关哪些变体将永久实施的数据驱动型决策。
* **一段时间内的营销活动评估**：衡量一段时间内的营销活动有效性。 您可以创建一个区段，该区段重点关注接触了给定营销活动的用户，并将其转化率与其他营销活动进行比较。 您还可以将当前转化率与过去运行的类似促销活动进行比较。

## 界面

有关引导式分析界面的概述，请参阅[界面](../overview.md#interface)。 以下设置特定于此分析：

### 查询边栏

利用查询边栏，可配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[漏斗](funnel.md)之间切换。
* **[!UICONTROL 步骤]**：要跟踪的事件接触点。 图表中的每个条形表示一个步骤。 您最多可以包含十个步骤。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。选项包括[!UICONTROL 用户]和[!UICONTROL 会话]。
* **[!UICONTROL 区段]**：要与其比较漏斗的区段。 所选的每个区段会将每个步骤拆分为多个条。 每种颜色代表不同的区段。 您最多可以包含三个区段。

### 图表设置

[!UICONTROL 转化趋势]分析提供了以下图表设置，可在图表上方的菜单中调整这些设置：

* **[!UICONTROL 图表类型]**：要使用的可视化图表类型。 选项包括[!UICONTROL 行]。
* **[!UICONTROL 转换自]**：确定从步骤到步骤的百分比计算。 选项包括从[!UICONTROL 第一步]或[!UICONTROL 上一步]计算转换。

>[!NOTE]
>
>转化趋势分析表中的&#x200B;**Average**&#x200B;列与[漏斗分析](funnel.md)表中的&#x200B;**Total**&#x200B;列不同。 前者是间隔列的平均值（例如，每日转化率的平均值），而后者是整个日期范围内的汇总计算。

### 时间比较

{{apply-time-comparison}}


### 日期范围

分析所需的日期范围。 此设置包含两个组件：

* **[!UICONTROL 时间间隔]**：要查看趋势数据的日期粒度。 有效选项包括每小时、每天、每周、每月和每季度。 同一日期范围可以有不同的时间间隔，这会影响图表中的数据点数和表中的列数。 例如，查看具有每日粒度的跨三天的分析将只显示三个数据点，而具有每小时粒度的跨三天的分析将显示72个数据点。
* **[!UICONTROL 日期]**：开始和结束日期。 您可以为方便起见，使用滚动日期范围预设和以前保存的自定义范围，也可以使用日历选择器来选择固定日期范围。

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
