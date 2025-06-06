---
title: 保留分析
description: 衡量有多少用户继续使用您的产品。
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
exl-id: c35a0ee0-e6b7-47b5-a5bc-308cde1585de
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: ht
source-wordcount: '1259'
ht-degree: 100%

---

# 保留分析 {#retention}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_retention_button"
>title="保留"
>abstract="衡量有多少用户继续使用您的产品。"

<!-- markdownlint-enable MD034 -->

![保留](/help/assets/icons/Retention.svg) **[!UICONTROL 保留]**&#x200B;分析衡量的是用户如何随着时间的推移继续使用您的产品，这可以帮助您了解您的产品市场契合度。该分析根据两个重要事件来统计用户数量：

* 开始事件：用于确定用户是否符合纳入您分析的条件的事件。
* 回访事件：用户必须参与的一个或多个事件，才能在分析中算作回访用户。

在此分析中，图表的 x 轴表示自用户首次启动事件以来的时间，y 轴表示参与一个或多个回访事件的用户百分比。您可以查看不同持续时间内的保留率和流失率，并且可以通过查询设置来自定义显示的持续时间。图表下方的表格提供的是汇总数据，并可以选择显示单个同类群组，即在同一日期执行起始事件的一群人。

>[!VIDEO](https://video.tv.adobe.com/v/3435788/?quality=12&learn=on&captions=chi_hans)


## 用例

该分析的用例包括：

* **同类群组分析**：根据用户采取的操作（例如注册或购买）将其分组为同类群组。您可以比较这些组的保留情况，并确定如何改善每个组的用户体验。
* **产品市场契合度**：衡量产品的常规使用情况，并以留存曲线进行可视化。更高的留存率意味着产品的市场契合度更好，而曲线趋于平稳的位置则表明达到契合度所需的时间。您可以选择从整体层面查看此分析，或按单个产品功能进行细分，以获得更深入的洞察。
* **订阅服务分析**：如果您的产品采用订阅或其他类型的经常性收入模式，您可以看到充分利用您的产品的用户百分比。您可以识别出这些用户表现出的某些品质和行为。
* **用户参与度**：评估某些类型的用户如何与您的产品互动，并并排比较他们返回的频率。留存率低于其他区段的特定区段，可以为您提供洞察，以改善他们可能经历的潜在不佳体验。

## 界面

请参阅[界面](../overview.md#interface)，了解引导分析界面的概述。以下设置专用于此分析：

### 查询边栏

查询边栏允许您配置以下组件：

* **[!UICONTROL 开始事件]**：用户必须参与才有资格纳入您的分析的事件标准。参与开始事件的用户将会被计入表格的“用户”列。此事件用作所示保留率的分母。支持一个事件，并且可以根据需要应用属性过滤器。默认情况下，开始事件和回访事件是相互关联的，这意味着用户必须执行一次选定的事件才能被纳入同类群组，然后再次执行才能算作返回用户。在“更多”菜单下，如果您希望返回操作与包含操作不同，则可以取消开始事件和回访事件的链接。
* **[!UICONTROL 回访事件]**：用户必须参与才能在持续时间范围内算作回访用户的事件标准。您最多可以选择三个回访事件来比较保留率。
* **[!UICONTROL 计为]**：要应用于保留用户的计数方法。选项包括：
   * **[!UICONTROL 量度]**：显示保留的[!UICONTROL 用户数量]或[!UICONTROL 用户百分比]。保留用户百分比的分母是同类群组中包含的用户，并且在所有持续时间段内都是相同的。
   * **[!UICONTROL 回访]**：允许您控制如何计算回访的用户。选项包括：
      * **[!UICONTROL 在指定日期或之后]**：通常被称为“无限制”保留，如果用户在指定持续时间或之后返回，则会将其计入用户数。例如，第 7 天或第 7 天之后的任何时间。此选项有助于展示用户如何持续参与，并因此产生更平滑的留存曲线。
      * **[!UICONTROL 精确时间]**：通常被称为“有限制”保留，如果用户精确地在指定的持续时间内返回，则此选项会将其计入用户数。例如，正好在第 7 天。此选项有助于展示用户在特定时间范围内的回访情况，并因此生成波动性更大的保留曲线。注释：Analysis Workspace 中的同类群组分析使用“精确时间”计数作为其分析的基础。
   * **[!UICONTROL 每个]**：您希望每个持续时间段所对应的时间段。选项包括：
      * **[!UICONTROL 日/周/月]**：可用选项取决于所选的日期范围。这些选项与选择日期范围时的&#x200B;**[!UICONTROL 间隔]**&#x200B;设置相同，并会自动更新该设置。
      * **[!UICONTROL 自定义括号]**：此选项仅适用于“每个”设置。它允许您统计更大时间范围内的用户；例如第 7-10 天，而不仅仅是第 7 天。
   * **[!UICONTROL 持续时间设置]**：允许您控制图表和表格上显示的持续时间段。持续时间是指从开始事件到回访事件发生之间的时间段。注释：符合持续时间段资格的用户是基于实际经过的时间，而非日程表天数。例如，如果用户在 9 月 6 日晚上 11:55 符合一个事件的资格，随后在 9 月 7 日凌晨 12:05 符合一个回访事件的资格，那么他们将不会出现在 1 天的持续时间段内。用户必须经过整整 24 小时后，才有资格进入 1 天的持续时间段内。可用的持续时间段取决于您设置的日期范围。
      * **[!UICONTROL 自动持续时间]**&#x200B;根据日期范围长度以及日期范围与当前日期的接近程度自动定义持续时间段。
      * **[!UICONTROL 自定义持续时间]**&#x200B;允许您自定义图表和表格上显示的四个持续时间段。
* **[!UICONTROL 区段]**：您要测量的区段。每个选定的区段都会向同类群组表中添加一行。最多可以包括三个区段。

### 图表设置

[!UICONTROL 保留]分析提供以下图表设置，这些设置可在图表上方的菜单中进行调整：

* **[!UICONTROL 图表类型]**：您想要使用的可视化类型。相关选项包括[!UICONTROL 条形图]和[!UICONTROL 线形图]。

### 日期范围

您需要分析的日期范围。此设置包含两个部分：

* **[!UICONTROL 间隔]**：您想要查看保留数据的日期粒度。有效的选项包括每日、每周和每月。相同的日期范围可以有不同的间隔，这会影响持续时间段选项。
* **[!UICONTROL 日期]**：开始和结束日期。为方便您使用，我们提供滚动日期范围预设以及之前保存的自定义范围，或者您可以使用日程表选择器选择固定的日期范围。

如果您选择的日期范围接近当前日期，那么最初参与时间过于接近当前日期的用户将不会被包括在内。此分析始终确保所有用户都有机会被纳入所有持续时间段内。日程表选择器下方的消息提供了用户参与的日期范围，以及仅为回访用户预留的时间间隔：

* **[!UICONTROL 分析在[日期间隔]]**&#x200B;内执行开始事件的用户：如果用户在此日期范围内参与了该事件，则会将其纳入分析范围。此日期范围可确保所有用户有足够的时间满足所有持续时间段的要求。如果该日期范围接近当前日期，则可能会与您选择的日期范围不同。
* **[!UICONTROL 保留[日期间隔]内的数据以完成分析]**：若用户在此期间首次参与，则其&#x200B;**不会**&#x200B;被纳入分析。对于最近的日期范围，这些用户可能没有机会符合所有持续时间段的要求。对于过去的日期范围，这些用户在选定的日期范围之外处于活跃状态。

<!--
## Example

See below for an example of the analysis.

![Retention](../assets/retention.png)

-->