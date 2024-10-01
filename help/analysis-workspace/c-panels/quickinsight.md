---
description: 快速洞察是一款面向新工作区用户的工具，可指导用户构建数据表和可视化图表
title: 快速洞察面板
feature: Panels
exl-id: 09ebc3af-34ac-4f1f-8a5d-90da008f8697
role: User
source-git-commit: 5b441472a21db99728d012c19f12d98f984086f5
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 24%

---

# “快速洞察”面板 {#quick-insights-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_quickinsights_button"
>title="快速洞察"
>abstract="创建一个面板以快速构建自由格式表和随附的可视化图表，从而更快地分析和发现见解。"

<!-- markdownlint-enable MD034 -->


[!UICONTROL 快速洞察]可为 [!UICONTROL Analysis Workspace] 的非分析师和新用户了解如何快速轻松地回答业务问题提供指导。此外，对于希望快速回答简单问题的高级用户来说，它也是一个不错的工具，无需自己制表。

当您首次开始使用此[!UICONTROL Analysis Workspace]时，您可能会想知道：

* 哪些可视化图表最有用，
* 哪些维度和量度有助于洞察，
* 拖放项目的位置，
* 创建过滤器的位置，
* 等等。

为了帮助您解答这些问题，[!UICONTROL 快速分析]利用算法来向您介绍您的公司最常使用的维度、量度、过滤器和日期范围。 此算法基于贵公司在[!UICONTROL Analysis Workspace]中的数据组件使用情况。 实际上，您会在下拉列表中看到标记为[!UICONTROL POPULAR]的维度、量度和过滤器，如下所示：

![“快速洞察”面板。](assets/popular-tag.png)

[!UICONTROL 快速洞察]会帮助您

* 在 [!UICONTROL Analysis Workspace] 中妥善构建数据表以及随附的可视化图表。
* 了解 [!UICONTROL Analysis Workspace] 中基本组件和要素的术语和词汇。
* 在[!UICONTROL 自由格式表]中轻松进行维度的简单划分、添加多个量度或比较过滤器。
* 更改或尝试各种可视化图表类型，快速直观地找到用于分析的查找工具。

## 基本关键术语

以下是您需要熟悉的一些基本术语。 每个数据表都包含2个或多个用于讲述数据故事的构建块（组件）。

| 构成要素（组件） | 定义 |
|---|---|
| **[!UICONTROL 维度]** | 维度是可以在项目中查看、划分和比较的量度数据的说明或特性。它们是非数字值和日期，可划分为不同维度项。例如，*浏览器*&#x200B;或&#x200B;*页面*&#x200B;是一个维度。 |
| **[!UICONTROL 维度项]** | 维度项是维度的单个值。例如，浏览器维度的维度项目应为&#x200B;*Chrome*、*Firefox*、*Edge*&#x200B;或其他。 |
| [!UICONTROL 量度] | 指标是关于查看次数、点进次数、重新加载次数、平均逗留时间、件数、订单数、收入等人员活动的量化信息。 |
| **[!UICONTROL 可视化图表]** | Workspace提供了[大量可视化图表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)来构建数据的可视化表示形式。 如条形图、圆环图、直方图、折线图、地图、散点图等。 |
| **[!UICONTROL 维度划分]** | 维度划分是一种按其他维度划分维度的方法。 例如，您可以按移动设备划分美国各州，以获取每个州的移动设备访问次数。 或者，您也可以按移动设备类型、区域、内部促销活动等划分移动设备。 |
| **[!UICONTROL 过滤器]** | 过滤器让您可以根据用户特征或网站交互情况来识别用户子集。 例如，您可以根据以下条件生成[!UICONTROL 人员]筛选器 <li>属性：浏览器类型、设备、访问次数、国家/地区、性别或</li><li>交互：促销活动、关键词搜索、搜索引擎或</li><li>退出和登录：来自Facebook、定义的登陆页面、反向链接域或</li><li> 自定义变量：表单字段、定义的类别、客户ID。 |

## 使用

要使用&#x200B;**[!UICONTROL 快速分析]**&#x200B;面板：

1. 创建&#x200B;**[!UICONTROL 快速分析]**&#x200B;面板。 有关如何创建面板的信息，请参阅[创建面板](panels.md#create-a-panel)。

1. 当您首次使用&#x200B;**[!UICONTROL 快速分析]**&#x200B;面板时，您可能需要完成简短的[!UICONTROL 介绍教程]，该教程将向您讲授一些基础知识。 选择“快速分析”面板标题旁边的![HelpOutline](/help/assets/icons/HelpOutline.svg)，然后从弹出窗口中选择&#x200B;**[!UICONTROL 介绍教程]**。

1. 为面板指定[输入](#panel-input)。

1. 观察面板的[输出](#panel-output)。


### 面板输入

选择构建基块：

* **[!UICONTROL 分析]** — 指定维度（橙色）
* **[!UICONTROL by]** — 指定指标（绿色）
* **[!UICONTROL 筛选依据]** — 指定筛选条件（蓝色）
* **[!UICONTROL on]** — 指定数据范围（紫色）。

要使可视化图表正常运行，您必须至少选择一个维度和一个量度。



您可以通过三种方式指定构建块：

* 从左侧面板中拖放组件。
* 开始键入构建基块字段之一。 找到输入后，构建基块字段会自动填充可能的值。
* 指定构建基块下拉列表（例如&#x200B;**[!UICONTROL Analyze]**&#x200B;中的`Country`），并在可能的值列表（使用![ChevronRight](/help/assets/icons/ChevronRight.svg)）中搜索要使用的值（例如&#x200B;**[!UICONTROL 国家/地区代码]**）。

选择&#x200B;**[!UICONTROL 清除]**&#x200B;以清除所有输入字段。


### 面板输出

1. 添加至少一个维度和一个量度后，即可看到结果。

   ![垂直显示维度、水平显示量度的自由格式表。](assets/quick-insights-output.png)

   * 一个自由格式表，其中包含维度（国家/地区代码）和量度（会话），并按过去12个月的Web会话进行过滤。

   * 随附的可视化图表，在这个示例中是[条形图](/help/analysis-workspace/visualizations/bar.md)。生成的可视化图表以您添加到表中的数据类型为基础。任何基于时间的数据（例如，每日/月的[!UICONTROL 会话]）均默认显示为[!UICONTROL 折线]图表。 任何非基于时间的数据（例如[!UICONTROL 设备]的[!UICONTROL 会话]）均默认使用[!UICONTROL 条形图]图表。 您可以通过单击可视化图表类型旁边的下拉箭头，来更改可视化图表类型。

1. 尝试添加更多细化，如下所述[更多提示](#more-tips)

1. 您可能希望使用&#x200B;**[!UICONTROL 项目>保存]**&#x200B;来保存项目。

## 更多提示

[!UICONTROL 快速分析生成器]中会弹出其他有用提示，其中一些提示取决于您的上一个操作。

* 首先，您可能需要完成&#x200B;**[!UICONTROL 更多提示]**&#x200B;教程。 在创建至少包含一个维度和一个量度的项目后24小时内会显示本教程。 选择“快速分析”面板标题旁边的![HelpOutline](/help/assets/icons/HelpOutline.svg)，然后从弹出窗口中选择&#x200B;**[!UICONTROL 更多提示]**。

  ![选择“帮助”图标后显示的“快速分析”面板通知。](assets/qibuilder4.png)

* 您可以分析多个维度和量度，组合或比较过滤器，以及指定数据范围：

  ![快速分析生成器结果](assets/qibuilder-result.png)

   * **[!UICONTROL 分析]**&#x200B;维度&#x200B;**[!UICONTROL 划分依据]**：您最多可以使用3个级别对维度进行划分，以挖掘您真正需要的数据。 请参阅➊、➋和➌。

   * 通过&#x200B;]**添加更多量度**[!UICONTROL ：您最多可以再添加2个量度。 请参阅➍和➎。

   * **[!UICONTROL 筛选依据]**：您最多可以再添加2个筛选器。 例如，将Bookings添加为过滤器，并将该过滤器与您比较的“频繁预订者”和“首次发送者”过滤器相结合。 请参阅➏、➐和➑。

   * on：您可以指定数据范围。 参见➒。

## 已知限制

如果尝试直接在表中编辑，则[!UICONTROL 快速分析]面板可能会不同步。 选择面板右上角的&#x200B;**[!UICONTROL 重新同步生成器]**&#x200B;以将其还原为以前的[!UICONTROL 快速分析]设置。

在将任何内容直接添加到表之前，您会收到一则警告：

![重新同步生成器选项警告。](assets/qibuilder-outofsync.png)

否则，直接构建会导致此表像传统的自由格式表那样运行，而不具有适用于新用户的有用功能。


>[!MORELIKETHIS]
>
>[创建面板](/help/analysis-workspace/c-panels/panels.md#create-a-panel)
>