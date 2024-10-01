---
description: 了解如何指定接触点以创建多维度流失序列。
title: 配置流失可视化
feature: Visualizations
exl-id: 3d888673-d7b1-45ef-bd3a-97b98466fb0e
role: User
source-git-commit: 664756b796e8915a701ccabfb5f250e777701b60
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 36%

---

# 配置流失可视化

您可以指定接触点以创建多维度流失序列。通常，接触点就是网站中的某个页面。但是，接触点并不仅限于页面。例如，您可以添加事件（如件数），以及独特人员和回访。 也可以添加维度，如类别、浏览器类型或内部搜索词。

甚至可以在接触点内添加过滤器。例如，您可能希望比较iOS和Android等过滤器™用户。 请将所需过滤器拖动到流失顶部，并将与这些过滤器有关的信息添加到流失报告中。如果只想显示这些过滤器，可以删除“所有访问”基线。

可添加的步骤数或使用的维度数没有限制。

您可以对维度、量度和过滤器进行路径分析。 例如，假设某个用户在一个页面上查看鞋子和衬衫，而在另一个页面上查看衬衫和袜子。 鞋的下一个产品流量报表将是衬衫和袜子，而不是衬衫。

## 使用

1. 添加![ConversionFunnel](/help/assets/icons/ConversionFunnel.svg) **[!UICONTROL 流失]**&#x200B;可视化图表。 请参阅[将可视化图表添加到面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。
1. 将页面（例如home）从“页面”维度拖动到&#x200B;*添加接触点*&#x200B;下拉菜单中。

   ![主页维度中的主页被拖到“添加接触点”字段。](assets/fallout-drag.png)

   将鼠标悬停在接触点上可查看流失以及有关该级别的其他信息，例如接触点的名称和该点的人员数。 并查看该接触点的成功率（并将成功率与其他接触点进行比较。）

   条形图灰色部分中的带圆圈数字显示接触点之间的流失（而不是到该点的整体流失）。**[!UICONTROL 接触点%]**&#x200B;显示流失报表中从上一步到当前步骤的成功流失。

   您还可以向流失报表中添加一个页面而不是整个维度。在页面维度上单击向右箭头![V形向右](/help/assets/icons/ChevronRight.svg)以选取要添加到流失报表的特定页面。

1. 继续添加接触点，直到您的序列完成。

   您可以&#x200B;**通过将一个或多个附加组件拖到接触点上，合并多个接触点**。

   >[!NOTE]
   >
   >多个过滤器通过 AND 相连，而多个项（如维度项）和量度通过 OR 相连。

   ![Page：CamerRoll或Page：摄像头接触点已突出显示。](assets/fallout-or.png)

1. 您还可以&#x200B;**将路径中的各个接触点限制为下一个事件** （而不是&#x200B;*最终*）。 在每个接触点下方，有一个选择器，带有选项&#x200B;**[!UICONTROL 最终路径]**&#x200B;和&#x200B;**[!UICONTROL 下一个事件]**，如下所示：

   ![显示“最终路径”选项的“所有访问”视图突出显示。](assets/fallout-nexthit.png)

   | 选项 | 描述 |
   |---|---|
   | **[!UICONTROL 最终路径]** （默认） | 计入的人数最终&#x200B;*将*&#x200B;登陆路径中的下一页，但不一定登陆下一个事件。 |
   | **[!UICONTROL 下一个事件]** | 重新计算后将在下一个事件的路径中到达下一页。 |


## 设置

作为可视化的一部分，特定设置可用。

| 流失容器 | 描述 |
|--- |--- |
| **[!UICONTROL 会话]**&#x200B;或&#x200B;**[!UICONTROL 人员]** | 在[!UICONTROL 会话]和[!UICONTROL 人员]之间切换以分析人员路径。 默认值为[!UICONTROL 人员]。 这些设置可帮助您在人员级别（跨会话）了解人员参与程度，或将分析限定于单次会话。 |


## 上下文菜单

作为可视化图表的一部分，可以使用特定的上下文菜单选项。

![流失选项](assets/fallout-options.png)

| 选项 | 描述 |
|--- |--- |
| **[!UICONTROL 趋势接触点]** | 在预先生成了一些异常检测数据的折线图中查看接触点的趋势数据。 |
| **[!UICONTROL 趋势接触点(%)]** | 显示总流失百分比趋势。 |
| **[!UICONTROL 显示所有接触点的趋势(%)]** | 在同一图表上显示流失中所有接触点百分比的趋势(除&#x200B;**[!UICONTROL 所有人员]**（如果包含）)。 |
| **[!UICONTROL 在此接触点划分流过]** | 查看人员在两个接触点（此接触点和下一个接触点）之间的行为（如果他们继续到下一个接触点）。 这会创建一个自由格式表来显示您的维度。您可以替换表的维度和其他元素。 |
| **[!UICONTROL 在此接触点划分流失]** | 查看未通过漏斗的人员在选定步骤后立即做了些什么。 |
| **[!UICONTROL 从接触点创建过滤器]** | 从选定的接触点创建新过滤器。 |

>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

