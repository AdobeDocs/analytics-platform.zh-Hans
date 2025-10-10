---
title: 首次使用影响分析
description: 衡量功能首次使用对关键量度的影响。
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
exl-id: 2c512184-2d79-4c41-8229-a09e440179ea
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 100%

---

# [!UICONTROL 首次使用影响]分析 {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="首次使用影响"
>abstract="衡量功能首次使用对关键量度的影响。"

<!-- markdownlint-enable MD034 -->

![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL 首次使用影响]**&#x200B;分析显示了用户首次使用产品功能前后关键指标表现的对比。本报告的横轴是事件前后的相对时间间隔，纵轴则会衡量所需的关键指标。图表中间的垂直条表示特定用户首次使用某项功能的第 0 天。由于用户并非总是在同一天采用功能，且功能的推出可能会持续数天，因此对于每位用户而言，“第 0 天”可能具有不同的含义。


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?quality=12&learn=on)


## 用例

该分析的用例包括：

* **新功能分析**：如果您在产品中推出了一项新功能，您可以比较用户首次接触该新功能前后关键指标的表现。
* **分阶段推出**：由于该分析寻找的是功能的首次使用情况而非固定的日期，因此如果您分阶段逐步推出功能，则使用此分析会很有帮助。
* **新产品版本分析**：如果您要推出产品的新版本，您可以比较用户首次接触新版本前后关键指标的表现。选择“任何事件”作为您的首次使用事件，并将其过滤到您的“版本号”属性。
* **现有功能改进**：如果您正在对产品中的现有功能进行改进，则可以比较用户首次接触这些新改进前后关键指标的表现。您可以根据功能检测情况采用一种或多种方式完成此分析。
   * 选择一个代表改进的事件作为首次使用事件
   * 选择开始推出变更的日期
   * 将分析细分至接触到改进的人群
* **营销活动效果**：当用户点击某个营销活动时，您可以比较用户与该营销活动互动前后关键指标的表现。

## 界面

请参阅[界面](../overview.md#interface)，了解引导分析界面的概述。以下设置专用于此分析：

### 查询边栏

查询边栏允许您配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[版本](release-impact.md)之间切换。
* **[!UICONTROL 关键指标]**：您想要按用户衡量的事件。每个选定的关键指标都以一条彩色线表示。代表该事件的行会被添加到表中。您最多可以包含三个事件。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。相关选项包括[!UICONTROL 每位用户的事件数]、[!UICONTROL 事件数]、[!UICONTROL 会话数]和[!UICONTROL 用户数]。
* **[!UICONTROL 因素]**：本次分析有两个因素：
   * **[!UICONTROL 日期]**：您想要从多久以前开始查找首次使用事件的发生时间。
   * **[!UICONTROL 事件]**：您想要查找的首次使用事件，以便将分析集中于此。
* **[!UICONTROL 区段]**：您要测量的区段。选定的区段会过滤您的数据，以便仅关注符合您的区段标准的个人。此分析支持单个区段。

### 图表设置

[!UICONTROL 首次使用影响]分析提供以下图表设置，这些设置可在图表上方的菜单中进行调整：

* **[!UICONTROL 图表类型]**：您想要使用的可视化类型。相关选项包括线形图。

### 日期范围

 [!UICONTROL 首次使用影响]分析中的日期选择与其他分析不同，因为该分析是围绕查询边栏中指定的日期展开的。可以使用以下选项：

* **[!UICONTROL 间隔]**：您想要查看趋势数据的日期粒度。有效选项包括[!UICONTROL 每日]、[!UICONTROL 每周]、[!UICONTROL 每月]和[!UICONTROL 每季度]。更改间隔会影响对于“之前”和“之后”时间段可用的选项。
* **[!UICONTROL “之前”和“之后”时间段]**：查询边栏中指定的首次使用事件前后要分析的时间长度。可用选项取决于对[!UICONTROL 间隔]的选择。

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
