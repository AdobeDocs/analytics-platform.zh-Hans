---
title: 同类群组表概述
description: 了解如何在Analysis Workspace中使用同类群组表进行同类群组分析
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
role: User
source-git-commit: 4bf8c616965718426efe880865acb0e5054b6a31
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 30%

---

# 同类群组表概述 {#cohort-table-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="同类群组表"
>abstract="创建可视化同类群组，根据事件的完成情况对用户进行分组，并分析持续的参与度和一段时间内的流失率。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="同类群组表"
>abstract="根据事件的完成情况分组用户，然后分析这些用户在一段时间内的持续参与和流失程度。<br/><br/>**参数&#x200B;**<br/>**纳入标准**：用于定义您的初始访客同类群组的组件。<br/>**回访标准**：用于确定访客是否已回访的组件。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**&#x200B;中的同类群组表。_<br/>_查看本文的_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**&#x200B;版本的[同类群组表](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis)。_

>[!ENDSHADEBOX]


*同类群组*&#x200B;是在指定时间段内共享相同特征的一组人员。 例如，在您想了解如何让一个同类群组喜欢某个品牌时，![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同类群组表]**&#x200B;可视化图表很有用。 您可以轻松识别趋势中的变化，然后相应地采取回应。（网上提供了有关[!UICONTROL 同类群组分析]的解释说明，例如[同类群组分析基础](https://zh.wikipedia.org/wiki/Cohort_analysis)。）

创建同类群组报表后，您可以组织其组件（特定的维度、量度和过滤器），然后可以与其他任何人员共享这份同类群组报表。请参阅[策划和共享](/help/analysis-workspace/curate-share/curate.md)。

使用[!UICONTROL 同类群组表]可以执行的操作示例：

* 启动旨在推动所需操作的促销活动。
* 在客户生命周期的恰当时间内转变营销预算。
* 识别终止试用或优惠活动的时间，以实现价值最大化。
* 获取在一些领域（例如，定价、升级路径等）内进行 A/B 测试的建议。

[!UICONTROL 同类群组表]适用于具有[!UICONTROL Analysis Workspace]访问权限的所有Customer Journey Analytics客户。


>[!BEGINSHADEBOX]

观看演示视频，请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[Analysis Workspace中的同类群组分析](https://video.tv.adobe.com/v/23990/?quality=12&learn=on){target="_blank"}。

{{videoaa}}

>[!ENDSHADEBOX]


>[!IMPORTANT]
>
>[!UICONTROL 同类群组分析]不支持不可过滤的量度（包括计算量度）、非整数量度（如收入）或发生次数。 只有可在筛选器中使用的量度才能在[!UICONTROL 同类群组分析]中使用，并且这些量度一次只能递增1。

Customer Journey Analytics中的同类群组表支持基于双精度指标（或任何基于数字的指标）。 例如，Purchase.Value(a double)可用作包含/返回量度。 此外，通过Analytics Source Connector传递到Adobe Experience Platform的所有量度也是双精度的。

## 同类群组表功能

以下部分介绍了同类群组分析功能，这些功能允许您对正在构建的同类群组进行精细控制。

有关创建同类群组并运行[!UICONTROL 同类群组分析]报表的更多详细信息，请参阅[配置同类群组表](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

### [!UICONTROL 保留]表

[!UICONTROL 维系]同类群组表返回人员：每个数据单元格显示了同类群组中在该时间段内执行操作的原始人数和百分比。 您最多可以包含 3 个量度和 10 个过滤器。

![显示同类群组中人员的单位和百分比的演绎版同类群组报告。](assets/retention-report.png)

### [!UICONTROL 流失]表

[!UICONTROL 流失率]同类群组表与维系率表完全相反，会显示随着时间的推移，您的同类群组中已流失或从不满足回访标准的人员。 您最多可以包含 3 个量度和 10 个过滤器。

![显示不符合同类群组回访标准的单位和人员百分比的客户流失表。](assets/churn-report.png)

### [!UICONTROL 滚动计算]

您可以根据前一列而不是所包含的列计算维系率或流失率，该列称为滚动计算。

![显示基于上一列数据的计算的同类群组保留报表。](assets/retention-report-rolling.png)

### [!UICONTROL 延迟]表

延时表衡量包含事件发生之前和之后经过的时间。 测量滞后时间是进行事前和事后分析的绝佳工具。 **[!UICONTROL 已包括]**&#x200B;列位于该表的中心，而包含事件之前和之后的时间段则分别显示在两侧。

![显示事件前后经过时间的同类群组报告。](assets/retention-report-latency.png)

### [!UICONTROL 自定义维度]同类群组

您可以创建基于选定维度的同类群组，而不是基于时间的同类群组（默认设置）。 使用维度（如[!UICONTROL 城市地域]、[!UICONTROL 营销渠道]、[!UICONTROL 促销活动]、[!UICONTROL 产品]、[!UICONTROL 页面]、[!UICONTROL 区域]或任何其他维度）来显示维系率的变化情况。 基于这些维度的不同值。

![显示自定义报告的同类群组报告具有所选维度，而不是默认的基于时间的同类群组。](assets/retention-dimensions.png)

>[!MORELIKETHIS]
>
>[配置同类群组表](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
>

