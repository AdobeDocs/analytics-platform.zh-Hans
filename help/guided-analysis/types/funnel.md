---
title: 漏斗分析
description: 比较步骤之间的转化率。
exl-id: c8b0b71f-8ed3-4aad-a0f8-4d5ad8d7a7bd
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
role: User
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 100%

---

# [!UICONTROL 漏斗]分析 {#funnel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_funnel_button"
>title="漏斗"
>abstract="比较步骤之间的转化率。"

<!-- markdownlint-enable MD034 -->

![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg)**[!UICONTROL 漏斗&#x200B;]**分析可以直观地呈现您的产品中关键的用户历程。横轴代表用户必须经历的每个步骤。纵轴表示每个步骤的用户或会话的百分比。所有步骤必须按最终顺序执行，但可在报告窗口内的任何时间进行。

>[!VIDEO](https://video.tv.adobe.com/v/3431280/?quality=12&learn=on&captions=chi_hans){width="90%"}

## 用例

该分析的用例包括：

* **转化分析**：您可以分析漏斗内每个阶段的转化情况，例如零售结账、帐户注册、订阅流程或产品体验中的其他关键历程。通过跟踪从一个步骤进展到下一个步骤的用户数量，您可以识别具有异常或不理想的转化率的瓶颈。这些信息对于了解您可以在哪些方面改善产品历程，以获得立竿见影的效果方面非常有价值。
* **实验分析**：您可以比较具有可选步骤或正在进行 A/B 试验的步骤的漏斗中的转化率。该信息可以帮助您确定漏斗中的哪种变化可带来最高的转化率，以便您可以鼓励更多的用户选择这种方式。
* **引导流程优化**：通过观察用户在关键事件上的行为，优化产品的引导流程。您可以确定用户难以完成或无法完成的步骤。
* **功能采用和参与度**：了解用户如何与产品中的特定功能进行互动。通过分析用户在使用与功能相关的步骤时的进展，您可以了解采用率，并确定用户可能未充分利用某些功能的领域。然后，您可以使用这些信息专注于功能改进，以提高采用率。
* **营销渠道有效性**：衡量营销渠道的有效性。您可以创建一个区段，重点关注与不同营销渠道（例如付费搜索、展示广告、免费搜索或直接营销）进行互动的用户。然后，您可以比较他们的历程，看看哪个渠道可以带来最佳的产品结果。

## 界面

请参阅[界面](../overview.md#interface)，了解引导分析界面的概述。以下设置专用于此分析：

### 查询边栏

查询边栏允许您配置以下组件：

* **[!UICONTROL 视图]**：在此分析和[转化趋势](conversion-trends.md)之间切换。
* **[!UICONTROL 步骤]**：您想要追踪的事件接触点。图表中的每个条形代表一个步骤。您最多可以包含 10 个步骤。
   * [!UICONTROL 比较]：每个步骤都提供了一个选项，用于比较单个漏斗步骤中的多个事件，从而创建一个“分叉漏斗”此功能可让您并排比较两次历程的摩擦，而无需创建两个单独的分析。当漏斗中有步骤选项或正在进行 A/B 试验时，这很有用。请参阅 Customer Journey Analytics 教程中的[漏斗](https://experienceleague.adobe.com/zh-hans/docs/customer-journey-analytics-learn/tutorials/guided-analysis/funnel)，观看介绍了如何比较漏斗的视频。
* **[!UICONTROL 计为]**：您希望应用于漏斗的范围。选项包括[!UICONTROL 会话]和[!UICONTROL 用户]。
   * [!UICONTROL 会话]：所有步骤必须发生在同一会话内才可计算。
   * [!UICONTROL 用户]：所有步骤都必须在选定的报告时间范围内发生才可计算。
* **[!UICONTROL 区段]**：您想要比较漏斗的区段。每个选定的区段会将每个步骤分成多个条形。每种颜色代表不同的区段。最多可以包括三个区段。

### 图表设置

[!UICONTROL 漏斗]分析提供以下图表设置，这些设置可在图表上方的菜单中进行调整：

* **[!UICONTROL 图表类型]**：您想要使用的可视化类型。选项包括[!UICONTROL 步骤]。
* **[!UICONTROL 转换依据]**：确定各步骤之间的百分比计算方式。相关选项包括从[!UICONTROL 第一步]或[!UICONTROL 上一步]计算转化率。

### 时间比较

{{apply-time-comparison}}



### 日期范围

您需要分析的日期范围。此设置包含两个部分：

* **[!UICONTROL 间隔]**：您想要查看趋势数据的日期粒度。此设置不会影响非趋势分析，例如[漏斗](funnel.md)。
* **[!UICONTROL 日期]**：开始和结束日期。为方便您使用，我们提供滚动日期范围预设以及之前保存的自定义范围，或者您可以使用日程表选择器选择固定的日期范围。

<!--
## Example

See below for an example of the analysis.

![Funnel time compare](../assets/funnel-compare.png)

-->
