---
title: 转化趋势分析
description: 跟踪转化率随时间发生的变化。
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
exl-id: 75501e77-a172-48b4-9c91-b12d39e93c37
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 99%

---

# [!UICONTROL 转化趋势]分析 {#conversion-trends}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_conversiontrends_button"
>title="转化趋势"
>abstract="跟踪转化率随时间发生的变化。"

<!-- markdownlint-enable MD034 -->


![转化趋势](/help/assets/icons/ConversionTrends.svg) **[!UICONTROL 转化趋势]**&#x200B;分析提供了随时间变化的转化率趋势的可视化图表。横轴是时间间隔，纵轴表示转化率。


>[!VIDEO](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/guided-analysis/conversion-trends)


## 用例

该分析的用例包括：

* **跟踪优化工作**：在使用[漏斗](funnel.md)分析确定您想要改进的关键瓶颈后，您可以使用此分析来跟踪这些优化如何影响一段时间内的转化率。
* **A/B 测试评估**：评估在漏斗环境中进行的 A/B 测试或实验的有效性。通过比较不同变体之间的转化率，您可以轻松确定哪些测试可提供更高的转化率，从而做出基于数据的决策，确定永久实施哪些变体。
* **随着时间的推移对营销活动的评估**：衡量营销活动随时间推移的有效性。您可以创建一个区段，其中重点关注参与过特定营销活动的用户，并将其转化率与其他营销活动进行比较。您还可以将当前的转化率与过去开展的类似营销活动进行比较。

## 界面

请参阅[界面](../overview.md#interface)，了解引导分析界面的概述。以下设置专用于此分析：

### 查询边栏

查询边栏允许您配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[漏斗](funnel.md)之间切换。
* **[!UICONTROL 步骤]**：您想要追踪的事件接触点。图表中的每个条形代表一个步骤。您最多可以包含 10 个步骤。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。选项包括[!UICONTROL 用户]和[!UICONTROL 会话]。
* **[!UICONTROL 区段]**：您想要比较漏斗的区段。每个选定的区段会将每个步骤分成多个条形。每种颜色代表不同的区段。最多可以包括三个区段。

### 图表设置

[!UICONTROL 转化趋势]分析提供以下图表设置，这些设置可在图表上方的菜单中进行调整：

* **[!UICONTROL 图表类型]**：您想要使用的可视化类型。相关选项包括[!UICONTROL 线形图]。
* **[!UICONTROL 转换依据]**：确定各步骤之间的百分比计算方式。相关选项包括从[!UICONTROL 第一步]或[!UICONTROL 上一步]计算转化率。

>[!NOTE]
>
>转化趋势分析表中的&#x200B;**平均值**&#x200B;列与[漏斗分析](funnel.md)表中的&#x200B;**总计**&#x200B;列不同。前者是区间列的平均值（例如，每日转化率的平均值），而后者是跨整个日期范围的聚合计算值。

### 时间比较

{{apply-time-comparison}}


### 日期范围

您需要分析的日期范围。此设置包含两个部分：

* **[!UICONTROL 间隔]**：您想要查看趋势数据的日期粒度。有效的选项包括每小时、每天、每周、每月和每季度。相同的日期范围可以有不同的间隔，这会影响图表中的数据点数和表格中的列数。例如，以每日粒度查看跨越三天的分析仅会显示三个数据点，而以每小时粒度查看跨越三天的分析则会显示 72 个数据点。
* **[!UICONTROL 日期]**：开始和结束日期。为方便您使用，我们提供滚动日期范围预设以及之前保存的自定义范围，或者您可以使用日程表选择器选择固定的日期范围。

<!--
## Example

See below for an example of the analysis.

![Conversion trends time compare](../assets/conversion-trends-compare.png)

-->
