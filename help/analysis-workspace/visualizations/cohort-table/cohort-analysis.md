---
title: 什么是同类群组分析？
description: 了解 Analysis Workspace 中的同类群组分析
feature: Visualizations
exl-id: 3e3a70cd-70ec-4d4d-81c3-7902716d0b01
source-git-commit: 5dd25745f3ae872a70f60c53a1340ba59552665d
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 91%

---

# 什么是[!UICONTROL 同类群组分析]？

*`cohort`* 是指一组在特定期限内共享相同特性的人员。例如，在您想了解如何让一个同类群组喜欢某个品牌时，[!UICONTROL 同类群组分析]就能派上用场。您可以轻松识别趋势中的变化，然后相应地采取回应。（网上提供了有关[!UICONTROL 同类群组分析]的解释说明，例如[同类群组分析基础](https://zh.wikipedia.org/wiki/Cohort_analysis)。）

创建同类群组报表后，您可以组织其组件（特定的维度、量度和过滤器），然后可以与其他任何人员共享这份同类群组报表。请参阅[策划和共享](/help/analysis-workspace/curate-share/curate.md)。

使用[!UICONTROL 同类群组分析]可以实现的作用（示例）：

* 启动旨在推动所需操作的促销活动。
* 在客户生命周期的恰当时间内转变营销预算。
* 识别终止试用或优惠活动的时间，以实现价值的最大化。
* 获取在一些领域（例如，定价、升级路径等）内进行 A/B 测试的建议。
* 在引导分析报表中查看[!UICONTROL 同类群组分析]报表。

[!UICONTROL 同类群组分析]适用于具有 [!UICONTROL Analysis Workspace] 访问权限的所有 Customer Journey Analytics 客户。

[同类群组分析视频教程](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/cohort-analysis/cohort-analysis-workspace.html?lang=zh-Hans)（4 分 36 秒）

>[!IMPORTANT]
>
>[!UICONTROL 同类群组分析] 不支持不可过滤的量度（包括计算量度）、非整数量度（如收入）或发生次数。 只有可在过滤器中使用的量度才能用于 [!UICONTROL 同类群组分析]，并且这些值一次只能递增1。

## 同类群组分析功能

以下功能允许您对正在构建的同类群组进行精细控制：

### [!UICONTROL 维系率表]

[!UICONTROL 维系]同类群组报表返回访客：每个数据单元格显示了同类群组中在该时间段内执行操作的访客原始数量和百分比。您最多可以包含 3 个量度和 10 个过滤器。

![](assets/retention-report.png)

### [!UICONTROL 流失率表]

[!UICONTROL 流失率]同类群组与维系率表完全相反，会显示随着时间的推移，您的同类群组中已流失或从不满足回访标准的访客。您最多可以包含 3 个量度和 10 个过滤器。

![](assets/churn-report.png)

### [!UICONTROL 滚动计算]

允许您根据前一列而不是所包含的列计算维系率或流失率。

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL 延时]表

衡量包含事件发生之前和之后经过的时间。此表非常适用于进行事件之前/之后分析。**[!UICONTROL 已包括]**&#x200B;列位于该表的中心，而包含事件之前和之后的时间段则分别显示在两侧。

![](assets/cohort-latency.png)

### [!UICONTROL 自定义维度]同类群组

创建基于所选维度的同类群组，而不是默认的基于时间的同类群组。在 Customer Journey Analytics 中使用[!UICONTROL 营销渠道]、[!UICONTROL 促销活动]、[!UICONTROL 产品]、[!UICONTROL 页面]、[!UICONTROL 区域]或任何其他维度，可显示维系率根据这些维度值的不同有何变化。

![](assets/cohort-customizable-cohort-row.png)

有关如何设置和运行同类群组报表的说明，请转至[配置同类群组分析报表](/help/analysis-workspace/visualizations/cohort-table/t-cohort.md)。
