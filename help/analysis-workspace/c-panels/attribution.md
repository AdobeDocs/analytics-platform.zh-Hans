---
title: 归因面板
description: 了解如何使用和解读Analysis Workspace中的归因面板。
feature: Panels
exl-id: 7fdec05b-5d99-48d1-ac1b-c243cb64e487
role: User
source-git-commit: 8054aab28c405f6a9dd24306a086c78069032999
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 97%

---

# 归因面板 {#attribution-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_attribution_button"
>title="归因"
>abstract="使用成功量度、渠道和回顾窗口，快速比较和可视化任意数量的归因模型。"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ 面板"

>[!CONTEXTUALHELP]
>id="workspace_attribution_panel"
>title="归因面板"
>abstract="为成功量度快速比较和可视化任意数量的归因模型。选择渠道（维度）、要包含的模型和回顾窗口。"
>additional-url="https://www.youtube.com/watch?v=Yu0hy2klzA0" text="Attribution IQ 面板"

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_本文记录了_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**&#x200B;_&#x200B;中的归因面板。<br/>_请参阅本文中_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics** 版本的[归因面板](https://experienceleague.adobe.com/zh-hans/docs/analytics/analyze/analysis-workspace/panels/attribution)。_

>[!ENDSHADEBOX]

**[!UICONTROL 归因]**&#x200B;面板是一种简单的方式，用于构建分析来比较各种归因模型。该面板为您提供了一个专用的工作区来使用和比较归因模型。

Customer Journey Analytics 通过让您能够执行以下操作来增强归因：

* 定义付费媒体之外的归因：可将任何维度、量度、渠道或事件应用于模型（例如内部搜索），而不仅仅是营销活动。
* 使用无限制的归因模型比较：动态比较任意所需数量的模型。
* 避免实施更改：使用报告时间处理和上下文感知会话，可在运行时构建并应用客户历程上下文。
* 构建与您的归因方案最匹配的会话。
* 按区段细分归因：轻松比较所有重要区段的营销渠道效果（例如新客户与老客户、产品 X 与产品 Y、忠诚度级别或 CLV）。
* 检查渠道交叉和多接触点分析：使用维恩图和直方图，以及趋势归因结果。
* 直观地分析关键营销序列：通过多节点流量和流失可视化图表，以可视方式探索导致转化的路径。
* 生成计算量度：使用任意数量的归因分配方法。

## 使用

要使用&#x200B;**[!UICONTROL 归因]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 归因]**&#x200B;面板。有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 指定面板的[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。

### 面板输入

可以使用以下输入设置配置归因面板：

1. 添加&#x200B;**[!UICONTROL 成功量度]**&#x200B;以及您想要归因的&#x200B;**[!UICONTROL 渠道]**&#x200B;维度。例如“营销渠道”或自定义维度，如内部促销。

   ![归因面板窗口显示几个选定的维度和量度。](assets/attribution-panel.png)

1. 从&#x200B;**[!UICONTROL 包含的模型]**&#x200B;中选择一个或多个[归因模型](#attribution-models)，并从要用于比较的&#x200B;**[!UICONTROL 回顾窗口]**&#x200B;中选择一个[回顾窗口](#lookback-window)。

1. 选择&#x200B;**[!UICONTROL 生成]**&#x200B;以在面板中生成可视化图表。

### 面板输出

**[!UICONTROL 归因]**&#x200B;面板会返回一组丰富的数据和可视化图表，其中对选定维度和度量进行了归因比较。

![比较选定量度和维度的归因面板可视化图表。](assets/attr_panel_vizs.png)

### 归因可视化图表

以下可视化图表是面板输出的一部分。

* **总量度**：报告时间窗口发生的总转化次数，归因于选定维度。
* **归因比较条形图**：以可视方式，比较所选维度中各个维度项的归因转化。每种条形颜色代表一个不同的归因模型。
* **归因比较表**：将相同的数据显示为条形图，以表格的形式表示。选择此表中不同的列或行，可将条形图以及面板中的其他一些可视化图表分段。此表的作用与 Workspace 中任何其他自由格式表的作用相似，允许您添加量度、区段或细分等组件。
* **重叠图**：一种维恩图可视化图表，显示前三个维度项以及它们共同参与某个转化的频率。例如，气泡重叠的大小表示当人员出现在两个维度项中时发生转化的频率。选择相邻自由格式表中的其他行，会更新可视化图表以反映所选内容。
* **性能详细信息**：散点图可视化图表可直观地比较最多三个归因模型。
* **趋势化性能**：显示排名最前的维度项的归因转化趋势。选择相邻自由格式表中的其他行，会更新可视化图表以反映所选内容。
* **流量**：让您可以查看在人员的历程中与哪个渠道交互得最多，以及按照什么顺序。

## 归因模型

{{attribution-models-details}}

## 容器

{{attribution-container}}

## 回顾时间范围

{{attribution-lookback-window}}

## 示例

{{attribution-example}}

>[!MORELIKETHIS]
>
> [创建面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>
