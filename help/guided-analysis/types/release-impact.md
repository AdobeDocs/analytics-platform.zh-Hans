---
title: 发布影响分析
description: 比较发布前和发布后相同时期的性能。
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: 023808a13ba9e438b33b1183b92d3aa8ac339230
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 99%

---

# [!UICONTROL 发布影响]分析 {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_releaseimpact_button"
>title="发布影响"
>abstract="比较发布前和发布后相同时期的性能。"

<!-- markdownlint-enable MD034 -->

![发布](/help/assets/icons/Release.svg) **[!UICONTROL 发布影响]**&#x200B;分析显示了关键量度在特定日期之前和之后的表现的比较。该报告的横轴是时间间隔，而纵轴衡量的是您所期望的关键指标。图表中间的垂直条代表要在其前后进行比较的日期。此日期通常代表您想要衡量的产品的显著变化，例如产品更新或营销活动启动。

>[!VIDEO](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/guided-analysis/release-impact)

## 用例

该分析的用例包括：

* **整体性能评估：**&#x200B;比较整体关键指标（例如参与度指标）可以帮助您确定特定版本总体上是否取得成功。
* **监控**：跟踪您希望在发生变化时保持不变的重要量度，例如加载时间或登录次数。使用此分析来比较发布前后的情况，以确保不会产生任何意外后果。
* **功能采用**：如果产品更新的重点是改进某个功能，则可以使用此分析直接比较产品更新前后该功能的使用情况。
* **错误检测**：跟踪发布前后的错误数量可以及早发现客户遇到的问题。如果您发现发布后立即出现错误增加的情况，您可以与工程或开发团队合作来识别和纠正相关问题，防止对客户造成进一步影响。

## 界面

请参阅[界面](../overview.md#interface)，了解引导分析界面的概述。以下设置专用于此分析：

### 查询边栏

查询边栏允许您配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[首次使用影响](first-use-impact.md)之间切换。
* **[!UICONTROL 关键指标]**：您想要按用户衡量的事件。每个选定的关键指标都以一条彩色线表示。代表该事件的行会被添加到表中。您最多可以包含三个事件。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。选项包括[!UICONTROL 每个用户的事件数]、[!UICONTROL 用户百分比]、[!UICONTROL 事件]、[!UICONTROL 会话]和[!UICONTROL 用户]。
* **[!UICONTROL 因素]**：您想要比较其前后的情况的日期。
* **[!UICONTROL 区段]**：您要测量的区段。选定的区段会过滤您的数据，以便仅关注符合您的区段标准的个人。

### 图表设置

[!UICONTROL 版本影响]分析提供以下图表设置，这些设置可在图表上方的菜单中进行调整：

* **[!UICONTROL 图表类型]**：您想要使用的可视化类型。相关选项包括[!UICONTROL 线形图]和[!UICONTROL 条形图]。

### 日期范围

影响分析中的日期选择与其他分析不同，因为该报告是围绕查询边栏中指定的日期展开的。可以使用以下选项：

* **[!UICONTROL 间隔]**：您想要查看趋势数据的日期粒度。有效选项包括[!UICONTROL 每日]、[!UICONTROL 每周]、[!UICONTROL 每月]和[!UICONTROL 每季度]。更改间隔会影响对于“之前”和“之后”时间段可用的选项。
* **[!UICONTROL 前后时期]**：查询边栏中指定的日期之前和之后要分析的时间量。可用选项取决于对[!UICONTROL 间隔]的选择。


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
