---
title: 时间线 分析
description: 观察一段时间内的用户级会话事件以找到体验模式。
feature: Adobe Product Analytics, Guided Analysis
keywords: 产品分析
role: User
exl-id: d3da9257-a133-46c8-8fac-1a33d3372bb7
source-git-commit: bd8c9951386608572d84006bd5465e57214c56d4
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 100%

---

# [!UICONTROL 时间线]分析 {#timeline}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_guidedanalysis_timeline_button"
>title="时间表"
>abstract="观察一段时间内的用户级会话事件。"

<!-- markdownlint-enable MD034 -->

通过 ![时间线](/help/assets/icons/Timeline.svg) **[!UICONTROL 时间线]**&#x200B;分析，您可以随时间的推移观察用户级会话事件，以找到相关的体验模式并讲述更好的用户故事。左侧边栏可让您按属性值和区段来过滤流。右侧边栏可让您从符合过滤器的随机用户列表中进行选择。中心区域会按照会话显示选定用户的流，其中包括时间戳、属性值和持续时间。无法获得给定会话中最后一个事件的持续时间。


>[!NOTE]
>
>[!UICONTROL 时间线]分析要求&#x200B;**[!UICONTROL 人员 ID]** 标准组件在[数据视图](/help/data-views/component-reference.md#optional)中可用。您的 Customer Journey Analytics 管理员负责管理数据视图中包含人员 ID 的情况，从而使您的组织能够完全控制哪些人可以访问这些数据，从而保护隐私。
>><br/>如果数据视图没有添加[!UICONTROL 人员 ID] 组件，则会显示以下消息：
>
>* **管理员**：*此分析需要 PersonID 属性。请将人员 ID 添加到数据视图。*
>* **非管理员**：*此分析需要 PersonID 属性。请与您的 Customer Journey Analytics 管理员合作，将人员 ID 添加到数据视图。*

>[!VIDEO](https://video.tv.adobe.com/v/3435777/?quality=12&learn=on&captions=chi_hans)



## 用例

该分析的用例包括：

* **阻力探索**：如果您在[漏斗分析](funnel.md)中发现急剧下降的情况，则可以创建一个这些用户的区段，并在本次分析中应用该区段来调查潜在原因。
* **错误行为**：如果用户遇到产品错误，您可以探索用户在看到该错误之前或之后做了什么。
* **数据收集验证**：数据管理员可以根据自己的人员 ID 对此分析进行过滤，以验证其组织的实施是否按预期进行。

## 界面

请参阅[界面](../overview.md#interface)，了解引导分析界面的概述。以下设置专用于此分析：

### 查询边栏

查询边栏允许您配置以下组件：

* **[!UICONTROL 维度]**：您想要查看流式值所在的维度。中间的数据流显示了所选维度的值。您还可以应用过滤器来缩小数据流的范围，以便获取更相关的数据。过滤器的有效运算符包括[!UICONTROL 等于]、[!UICONTROL 不等于]、[!UICONTROL 开头为]、[!UICONTROL 结尾为]、[!UICONTROL 包含]、[!UICONTROL 不包含]、[!UICONTROL 存在]和[!UICONTROL 不存在]。
* **[!UICONTROL 区段]**：您要分析的区段。选定的区段会过滤您的数据，以便仅关注符合您的区段标准的个人。如果您想将分析范围缩小到特定的人员 ID，您可以在右侧面板中筛选该人员 ID。此分析支持一个区段。

### 图表设置

[!UICONTROL 时间线]分析提供以下图表设置，这些设置可在图表上方的菜单中进行调整：

* **[!UICONTROL 显示为]**：显示所需的属性值。
   * [!UICONTROL 显示全部]：显示会话中的所有属性值。
   * [!UICONTROL 突显]：以视觉方式突出显示会话中与查询过滤器匹配的属性值。
   * [!UICONTROL 仅查看]：仅显示会话中与查询过滤器匹配的属性值。

### 日期范围

您需要分析的日期范围。此设置包含两个部分：

* **[!UICONTROL 间隔]**：您想要查看趋势数据的日期粒度。此设置不会影响时间线等非趋势分析。
* **[!UICONTROL 日期]**：开始和结束日期。为方便您使用，我们提供滚动日期范围预设以及之前保存的自定义范围，或者您可以使用日程表选择器选择固定的日期范围。


<!--

## Example

See below for an example of the analysis.

![Timeline](../assets/timeline-new.png)

-->
