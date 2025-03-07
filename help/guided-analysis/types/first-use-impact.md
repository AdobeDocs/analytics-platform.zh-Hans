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
ht-degree: 9%

---

# [!UICONTROL 首次使用影响]分析 {#first-use-impact}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_firstuseimpact_button"
>title="首次使用影响"
>abstract="衡量功能首次使用对关键量度的影响。"

<!-- markdownlint-enable MD034 -->

![FirstUse](/help/assets/icons/FirstUse.svg) **[!UICONTROL 首次使用影响]**&#x200B;分析显示了用户首次使用产品功能之前和之后关键指示器执行的比较。 此报告的水平轴是事件之前和之后的相对时间间隔，而垂直轴测量所需的关键指示器。 图表中央的垂直条形表示给定用户首次使用功能时的第0天。 由于用户并不总是在同一天采用功能，并且您的转出可能会持续数天，因此第0天对于每位用户都意味着不同的内容。


>[!VIDEO](https://video.tv.adobe.com/v/3421661/?quality=12&learn=on)


## 用例

此分析的用例包括：

* **新功能分析**：如果您正在产品中启动新功能，您可以比较在用户首次使用该新功能之前和之后关键指示器的执行情况。
* **分阶段推出**：由于分析会查找功能的首次使用而不是固定日期，因此如果您在一段时间内分阶段推出功能，此分析将会很有帮助。
* **新产品版本分析**：如果您要启动产品的新版本，您可以比较用户首次使用该新版本之前和之后关键指示器的执行情况。 选择“any event”作为您的首次使用事件，并将其筛选到您的Version number属性。
* **现有功能改进**：如果您对产品中的现有功能进行改进，则可以比较在用户首次看到这些新改进之前和之后关键指示器的执行情况。 根据特征分析，可以用一种或多种方式完成此分析。
   * 选择一个将改进表示为首次使用事件的事件
   * 选择更改开始转出的日期
   * 将分析分给面临改进的人群
* **促销活动有效性**：当用户从给定促销活动点击进来时，您可以比较关键指标在用户与该促销活动交互之前和之后执行情况。

## 界面

有关引导式分析界面的概述，请参阅[界面](../overview.md#interface)。 以下设置特定于此分析：

### 查询边栏

利用查询边栏，可配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[版本](release-impact.md)之间切换。
* **[!UICONTROL 关键指示器]**：每个用户要测量的事件。 每个所选关键指示符用彩色线条表示。 表示该事件的行将添加到表中。 您最多可以包含三个事件。
* **[!UICONTROL 计为]**：要应用于所选事件的计数方法。选项包括每个用户的[!UICONTROL 事件]、[!UICONTROL 事件]、[!UICONTROL 会话]和[!UICONTROL 用户]。
* **[!UICONTROL 因素]**：此分析有两个因素：
   * **[!UICONTROL 日期]**：您希望回溯多远，以便开始查找已发生的首次使用事件。
   * **[!UICONTROL 事件]**：要查找的首次使用事件，以集中分析。
* **[!UICONTROL 区段]**：要测量的区段。 所选区段会过滤您的数据，以仅关注符合您的区段标准的个人。 此分析支持单个区段。

### 图表设置

[!UICONTROL 首次使用影响]分析提供了以下图表设置，可在图表上方的菜单中调整这些设置：

* **[!UICONTROL 图表类型]**：要使用的可视化图表类型。 选项包括Line。

### 日期范围

[!UICONTROL 首次使用影响]分析中的日期选择与其他分析的工作方式不同，因为分析围绕查询边栏中指定的日期进行。 可以使用以下选项：

* **[!UICONTROL 时间间隔]**：要查看趋势数据的日期粒度。 有效选项包括[!UICONTROL Daily]、[!UICONTROL Weekly]、[!UICONTROL Monthly]和[!UICONTROL Quarterly]。 更改间隔将影响“之前”和“之后”时段可用的选项。
* **[!UICONTROL 时段之前和之后]**：在查询边栏中指定的第一个使用事件之前和之后要分析的时间量。 可用选项取决于[!UICONTROL 间隔]选择。

<!--
## Example

See below for an example of the analysis.

![First use impact](../assets/first-use-impact.png)

-->
