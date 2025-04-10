---
description: 了解如何指定接触点以创建多维度流失序列。
title: 配置流失可视化
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 392ba2b9cfe090901c3dac12459f9bd8d51fdca7
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 91%

---

# 配置流失可视化图表 {#configure-fallout-visualization}


您可以指定接触点以创建多维度流失序列。通常，接触点就是网站中的某个页面。但是，接触点并不仅限于页面。例如，您可以添加事件，如单位及独特人员和回访。也可以添加维度，如类别、浏览器类型或内部搜索词。

甚至可以在接触点内添加过滤器。例如，您可能希望比较iOS和Android等过滤器™用户。 请将所需过滤器拖动到流失顶部，并将与这些过滤器有关的信息添加到流失报告中。如果只想显示这些过滤器，可以删除“所有访问”基线。

对于可添加的步骤数量或可以使用的维度数量，没有任何限制。

您可以对维度、量度和过滤器进行路径分析。 例如，假设某个用户在一个页面上查看鞋和衬衫，而在另一个页面上查看衬衫和袜子。鞋的下一个产品流量报告将是衬衫和袜子，而不是衬衫。

## 使用

1. 添加 ![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL 流失]**&#x200B;可视化图表。请参阅[将可视化图表添加到面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。
1. 将页面（例如主页）从页面维度拖到&#x200B;*添加接触点*&#x200B;下拉菜单。

   ![将主页从主页维度拖到添加接触点字段。](assets/fallout-drag.png)

   将光标悬停在接触点上，查看流失以及有关该级别的其他信息，例如接触点名称以及接触点人数。并查看该接触点的成功率（以及将成功率与其他接触点进行比较。）

   条形图灰色部分中的带圆圈数字显示接触点之间的流失（而不是到接触点的整体流失）。在流失报告中，**[!UICONTROL 接触点 %]** 显示从前一步骤到当前步骤的成功流过。

   您还可以向流失报告中添加一个页面而不是整个维度。单击页面维度上的向右箭头 ![ChevronRight](/help/assets/icons/ChevronRight.svg) 可选取要添加到流失报告中的特定页面。

1. 继续添加接触点，直到您的序列完成。

   您可以通过将一个或多个其他组件拖到某个接触点来&#x200B;**合并多个接触点**。

   >[!NOTE]
   >
   >多个过滤器通过 AND 相连，而多个项（如维度项）和量度通过 OR 相连。

   ![页面：CamerRoll 或页面：相机接触点突出显示。](assets/fallout-or.png)

1. 您还可以将各个接触点&#x200B;**限制为路径中的下一个事件**（而不是&#x200B;*最终*）。每个接触点下方都有一个选择器，其中包含&#x200B;**[!UICONTROL 最终路径]**&#x200B;和&#x200B;**[!UICONTROL 下一个事件]**&#x200B;选项，如下所示：

   ![“所有访问”视图突出显示了“最终路径”选项。](assets/fallout-nexthit.png)

   | 选项 | 描述 |
   |---|---|
   | **[!UICONTROL 最终路径]**（默认） | 对&#x200B;*最终*&#x200B;在路径中登陆下一页，但不一定发生下一个事件的人员进行计数。 |
   | **[!UICONTROL 下一个事件]** | 将登陆下一个事件路径下一页的人员将被计数。 |


## 设置 {#settings}

>[!CONTEXTUALHELP]
>id="workspace_fallout_container"
>title="流失容器"
>abstract="选择一个容器来分析路径。此选择有助于您了解参与度并将分析限制在所选容器内。"

作为可视化图表的一部分，可以使用特定设置。

| 流失容器 | 描述 |
|--- |--- |
| **[!UICONTROL 会话]**&#x200B;或者&#x200B;**[!UICONTROL 人员]** | 在[!UICONTROL 会话]和[!UICONTROL 人员]之间进行切换，以分析人员路径。默认为[!UICONTROL 人员]。这些设置可帮助您在人员级别（跨会话）了解人员参与程度，或将分析限定于单次会话。 |


## 上下文菜单

作为可视化图表的一部分，可以使用特定上下文菜单选项。

![流失选项](assets/fallout-options.png)

| 选项 | 描述 |
|--- |--- |
| **[!UICONTROL 显示接触点趋势]** | 在预先生成了一些异常检测数据的线形图中查看接触点的趋势数据。 |
| **[!UICONTROL 显示接触点趋势（%）]** | 显示总流失百分比趋势。 |
| **[!UICONTROL 显示所有接触点趋势（%）]** | 在同一个图表中显示流失中的所有接触点百分比趋势（如果包括&#x200B;**[!UICONTROL 所有人员]**，则将其排除）。 |
| **[!UICONTROL 划分此接触点的流过]** | 查看人员在两个接触点（此接触点和下一个接触点）之间的行为（如果他们继续到下一个接触点）。这会创建一个自由格式表来显示您的维度。您可以替换表的维度和其他元素。 |
| **[!UICONTROL 划分此接触点的流失]** | 查看未通过漏斗的人员在选定步骤后立即做了些什么。 |
| **[!UICONTROL 从接触点创建过滤器]** | 从选定的接触点创建新过滤器。 |

>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化图表设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化图表上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

