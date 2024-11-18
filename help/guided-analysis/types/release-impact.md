---
title: 发布影响分析
description: 比较发布前和发布后相同时期的性能。
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
exl-id: 93e6e4f1-bbe4-4a6c-8ec3-54d1f9a8b847
role: User
source-git-commit: d492220eaf12242a870f3826b31edd3d1ea99a3b
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 10%

---

# [!UICONTROL 发布影响]分析 {#release-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_guidedanalysis_releaseimpact_button"
>title="发布影响"
>abstract="比较发布前和发布后相同时期的性能。"

<!-- markdownlint-enable MD034 -->

![版本](/help/assets/icons/Release.svg) **[!UICONTROL 版本影响]**&#x200B;分析显示了给定日期之前和之后关键指标执行情况的比较。 此报告的水平轴是一个时间间隔，而垂直轴测量所需的关键指标。 图表中间有一个垂直条形图，表示要在前后比较的日期。 此日期通常表示要衡量的产品发生了显着更改，例如产品更新或促销活动启动。

>[!VIDEO](https://video.tv.adobe.com/v/3421665/?learn=on)

## 用例

此分析的用例包括：

* **总体绩效评估：**&#x200B;比较总体关键指标（如参与度量）可以帮助您确定给定的版本是否总体成功。
* **监控**：跟踪您希望在更改时保持不变的重要指标，如加载时间或登录次数。 使用此分析在发布之前和之后进行比较，以确保不会产生任何意外结果。
* **功能采用**：如果产品更新侧重于改进某个功能，您可以使用此分析直接比较该功能在产品更新前后的使用情况。
* **错误检测**：跟踪发布之前和之后的错误数可以提供客户问题的早期指示器。 如果您在发布后立即发现错误增加，则可以与工程或开发团队合作，以确定和更正问题，防止对客户造成进一步影响。

## 界面

有关引导式分析界面的概述，请参阅[界面](../overview.md#interface)。 以下设置特定于此分析：

### 查询边栏

利用查询边栏，可配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[首次使用影响](first-use-impact.md)之间切换。
* **[!UICONTROL 关键指示器]**：每个用户要测量的事件。 每个所选关键指示符用彩色线条表示。 表示该事件的行将添加到表中。 您最多可以包含三个事件。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。选项包括每个用户的[!UICONTROL 事件]、[!UICONTROL 用户百分比]、[!UICONTROL 事件]、[!UICONTROL 会话]和[!UICONTROL 用户]。
* **[!UICONTROL 因素]**：您要在前后比较的日期。
* **[!UICONTROL 区段]**：要测量的区段。 所选区段会过滤您的数据，以仅关注符合您的区段标准的个人。

### 图表设置

[!UICONTROL 版本影响]分析提供了以下图表设置，可以在图表上方的菜单中调整这些设置：

* **[!UICONTROL 图表类型]**：要使用的可视化图表类型。 选项包括[!UICONTROL 行]和[!UICONTROL 栏]。

### 日期范围

影响分析中的日期选择与其他分析的工作方式不同，因为报告围绕查询边栏中指定的日期进行。 可以使用以下选项：

* **[!UICONTROL 时间间隔]**：要查看趋势数据的日期粒度。 有效选项包括[!UICONTROL Daily]、[!UICONTROL Weekly]、[!UICONTROL Monthly]和[!UICONTROL Quarterly]。 更改间隔将影响“之前”和“之后”时段可用的选项。
* **[!UICONTROL 时段之前和之后]**：在查询边栏中指定的日期之前和之后要分析的时间量。 可用选项取决于[!UICONTROL 间隔]选择。


<!--
## Example

See below for an example of the analysis.

![Release impact](../assets/release-impact.png)

-->
