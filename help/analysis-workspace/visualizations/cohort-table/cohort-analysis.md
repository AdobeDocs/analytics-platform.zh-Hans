---
title: 同类群组表概述
description: 了解如何更深入地挖掘受众周围的数据，并通过同类群组分析将数据划分为相关的群组。 在Analysis Workspace中使用同类群组分析。
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '719'
ht-degree: 91%

---

# 同类群组表概述 {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="同类群组表"
>abstract="创建同类群组可视化图表，根据事件的完成情况对用户进行分组，并分析持续的参与度和一段时间内的流失率。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="同类群组表"
>abstract="根据事件的完成情况分组用户，然后分析这些用户在一段时间内的持续参与和流失程度。指定其他设置，如粒度、同类群组分析类型以及是否使用滚动计算。您可以设置高级选项，根据所选维度生成延迟表或自定义维度同类群组。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;中的同类群组表。_<br/>_请参阅本文中_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 版本的[同类群组表](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis)。_

>[!ENDSHADEBOX]


*cohort* 是指一组在特定期限内共享相同特性的人员。例如，在您想了解如何让一个同类群组喜欢某个品牌时，![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同类群组表]**&#x200B;可视化图表就能派上用场。您可以轻松识别趋势中的变化，然后相应地采取回应。（网上提供了有关[!UICONTROL 同类群组分析]的解释说明，例如[同类群组分析基础](https://zh.wikipedia.org/wiki/Cohort_analysis)。）

创建队列报表后，您可以组织其组件（特定的维度、指标和区段），然后可以与其他任何人员共享这份队列报表。请参阅[策划和共享](/help/analysis-workspace/curate-share/curate.md)。

使用[!UICONTROL 同类群组表]可以实现的作用（示例）：

* 旨在刺激所需操作的启动营销活动。
* 在客户生命周期的正确时间转移营销预算。
* 识别终止试用或优惠活动的时间以实现价值的最大化。
* 获取在一些领域（例如，定价、升级路径等）内进行 A/B 测试的建议。

[!UICONTROL 同类群组表]适用于具有 [!UICONTROL Analysis Workspace] 访问权限的所有 Customer Journey Analytics 客户。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analysis Workspace 中的同类群组分析](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"}以观看演示视频。

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL 同类群组分析]不支持不可分段的量度（包括计算量度）、非整数量度（例如收入）或发生次数。只有可以在区段中使用的量度才能在[!UICONTROL 同类群组分析]中使用，并且它们一次只能递增 1。

Customer Journey Analytics 中的同类群组表支持基于双倍量度（或任何基于数值的量度）。例如，Purchase.Value（双倍）可用作包含/返回量度。此外，通过 Analytics Source Connector 传递到 Adobe Experience Platform 的所有量度也都是双倍的。

## 同类群组表功能

以下部分介绍了同类群组分析功能，可对您正在构建的同类群组进行微调控制。

有关创建同类群组和运行[!UICONTROL 同类群组分析]报告的更多详细信息，请参阅[配置同类群组表](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

### 维系率表

[!UICONTROL 维系率]同类群组表回访人员：每个数据单元格显示了同类群组中在该时段内执行操作的原始人数和百分比。您最多可以包含 3 个指标和 10 个区段。

![维系率同类群组报告显示了同类群组中的人员单位和百分比。](assets/retention-report.png)

### 流失率表

[!UICONTROL 流失率]同类群组表与维系率表完全相反，会显示随着时间的推移，您的同类群组中已流失或从不满足回访标准的人员。您最多可以包含 3 个指标和 10 个区段。

![流失率表显示了不符合同类群组回访标准的人员单位和百分比。](assets/churn-report.png)

### 滚动计算

您可以根据上一列而不是包括的列来计算维系率或流失率，这称为滚动计算。

![同类群组维系率报告显示了基于上一列数据的计算结果。](assets/retention-report-rolling.png)

### 延时表

延迟表衡量在发生包含事件之前和之后经过的时间。衡量延迟是进行事件之前和之后分析的绝佳工具。**[!UICONTROL 已包括]**&#x200B;列位于该表的中心，而包含事件之前和之后的时间段则分别显示在两侧。

![同类群组报告显示了发生事件之前和之后经过的时间。](assets/retention-report-latency.png)

### 自定义维度同类群组

您可以创建基于所选维度的同类群组，而不是（默认的）基于时间的同类群组。使用[!UICONTROL 地理城市]、[!UICONTROL 营销渠道]、[!UICONTROL 营销活动]、[!UICONTROL 产品]、[!UICONTROL 页面]、[!UICONTROL 区域]等维度或任何其他维度来显示维系率的变化情况。根据这些维度的不同值。

![同类群组报告显示具有选定维度的自定义报告，而不是默认的基于时间的同类群组。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[配置同类群组表](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>

