---
title: 什么是同类群组分析？
description: 了解Analysis Workspace中的同期群分析
translation-type: tm+mt
source-git-commit: fc5a462f3d216d8cae3ce060a45ec79a44c4c918
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 44%

---


# What is [!UICONTROL Cohort Analysis]?

>[!NOTE] 您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

*`cohort`* 是指一组在特定期限内共享相同特性的人员。[!UICONTROL 例如，在您想了解如何让一个同类群组喜欢某个品牌时，同类群组分析就能派上用场。]您可以轻松识别趋势中的变化，然后相应地采取回应(Explanations of [!UICONTROL Cohort Analysis] are available on the web, such as at [Cohort Analysis 101](https://en.wikipedia.org/wiki/Cohort_analysis).)

创建队列报表后，您可以组织其组件（特定的维度、量度和区段），然后可以与其他任何人员共享这份队列报表。请参阅[策划与共享](/help/analysis-workspace/curate-share/curate.md)。

Examples of what you can do with [!UICONTROL Cohort Analysis]:

* 启动旨在推动所需操作的促销活动。
* 在客户生命周期的恰当时间内转变营销预算。
* 识别何时结束试用或优惠，以实现最大价值。
* 获取在一些领域（例如，定价、升级路径等）内进行 A/B 测试的建议。
* View a [!UICONTROL Cohort Analysis] report within a Guided Analysis report.

[!UICONTROL 群组分析] 适用于所有拥有Analysis Workspace访问权限的AdobeAnalytics [!UICONTROL 客户]。

[YouTube 上的同类群组分析](https://www.youtube.com/watch?v=kqOIYrvV-co&amp;index=45&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:36)

>[!IMPORTANT]
>
>[!UICONTROL 同期群分析] 不支持不可过滤的指标（包括计算指标）、非整数指标（如收入）或发生次数。 只有可在区段中使用的指标才能用于
>[!UICONTROL 同期群分析]，而且每次只能增加1。

## 同类群组分析功能

以下功能允许对您正在构建的群组进行微调控制：

### [!UICONTROL 维系率表]

A [!UICONTROL Retention] cohort report returns visitors: each data cell shows the raw number and percentage of visitors in the cohort who did the action during that time period. 您最多可以包含 3 个量度和 10 个区段。

![](assets/retention-report.png)

### [!UICONTROL 流失率表]

A [!UICONTROL Churn] cohort is the inverse of a retention table and shows the visitors who fell out or never met the return criteria for your cohort over time. 您最多可以包含 3 个量度和 10 个区段。

![](assets/churn-report.png)

### [!UICONTROL 滚动计算]

允许您根据前一列而不是所包含的列计算维系率或流失率。

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL 延时表]

衡量包含事件发生之前和之后经过的时间。此表非常适用于进行事件之前/之后分析。The **[!UICONTROL Included]** column is in the center of the table and time periods before and after the inclusion event are shown on both sides.

![](assets/cohort-latency.png)

### [!UICONTROL 自定义维度同类群组]

创建基于所选维度的同类群组，而不是默认的基于时间的同类群组。Use dimensions such as [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region], or any other dimension in Adobe Analytics to show how retention changes based on the different values of these dimensions.

![](assets/cohort-customizable-cohort-row.png)

有关如何设置和运行同期群报告的说明，请转 [至配置同期群分析报告](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。

