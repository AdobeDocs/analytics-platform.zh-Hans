---
description: 在 Analysis Workspace 中创建一个同类群组并运行同类群组分析报表。
keywords: Analysis Workspace
title: 运行同类群组分析报表
topic: Reports and analytics
uuid: 5574230f-8f35-43ea-88d6-cb4960ff0bf4
translation-type: tm+mt
source-git-commit: 7862233892e56d1faafed6c14bd527db89ff1a3b
workflow-type: tm+mt
source-wordcount: '995'
ht-degree: 98%

---


# 配置[!UICONTROL 同类群组分析]报表

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

在 Analysis Workspace 中创建一个同类群组并运行[!UICONTROL 同类群组分析]报表。

1. 在 Analysis Workspace 中，单击左边栏中的&#x200B;**[!UICONTROL 可视化图表]**&#x200B;图标，然后将一个&#x200B;**[!UICONTROL 同类群组表]**&#x200B;拖到画布上。

   ![](assets/cohort-table.png)

1. 按照下表所示，定义&#x200B;**[!UICONTROL 包含标准]**、**[!UICONTROL 回访标准]**、**[!UICONTROL 同类群组类型]**&#x200B;和&#x200B;**[!UICONTROL 设置]**。

| 元素 | 描述 |
| --- | --- |
| **[!UICONTROL 包含标准]** | 您最多可以应用 10 个包含区段和 3 个包含量度。这个量度会指定将用户置于同类群组中的量度。例如，假设包含量度是“订单”，那么只有在同类群组分析的时间范围内下达了订单的用户才会包含在初始同类群组中。<br>这些量度之间的默认运算符是 AND，但您可以将其更改为 OR。此外，您还可以为这些量度添加数字过滤。例如：“访问次数 >= 1”。 |
| **[!UICONTROL 回访标准]** | 您最多可以应用 10 个回访区段和 3 个回访量度。回访量度指示用户是已维系还是流失。例如，假设回访量度是“视频查看”，那么只有在后续时间范围（即，当用户添加到同类群组后的时间期限）内查看了视频的用户才会显示为已维系。另一个符合维系要求的量度是“访问”。 |
| **[!UICONTROL 粒度]** | 由“天”、“周”、“月”、“季度”或“年”组成的时间粒度。 |
| **[!UICONTROL 类型]** | **[!UICONTROL 维系率]**（默认）：维系率同类群组衡量一段时间内同类访客回访您的资产的程度。这是我们一直拥有的标准同类群组，该同类群组指示用户的回访和重复行为。[!UICONTROL 维系率]同类群组在表中以绿色指示。 <br> **[!UICONTROL 流失率]**：流失率（也称为“减少”或“流失”）同类群组衡量一段时间内同类访客如何从您的资产中流失。流失率 = 1 - 维系率。[!UICONTROL 流失率]会显示客户有多久没有回访，从而可以很好地衡量吸引力和商机。您可以使用流失率来分析和识别焦点区域：哪些同类群组区段可能会被吸引过来。[!UICONTROL 流失率]同类群组在表中以红色指示（类似于&#x200B;**[!UICONTROL 流量]**&#x200B;可视化图表中的流失）。 |
| **[!UICONTROL 设置]** | **[!UICONTROL 滚动计算]**：根据前一列而不是“已包括”列（默认）计算维系率或流失率。[!UICONTROL 滚动计算]会更改“回访”时段的计算方法。常规计算会单独查找符合“回访”标准且包含在包含时段的用户，而不论他们是否在上一时段的同类群组中。相反，[!UICONTROL 滚动计算]会查找符合“回访”标准且包含在上一时段的用户。因此，[!UICONTROL 滚动计算]会过滤并筛分出一段时间内持续满足“回访”标准的用户。[!UICONTROL 回访]标准将应用于选定时段之前的每个时段。<br> **[!UICONTROL 延时表]**：[!UICONTROL 延时表]衡量包含事件发生之前和之后经过的时间。[!UICONTROL 延时表]非常适用于进行事件之前/之后分析。例如，如果您即将推出某个产品或某项促销活动，并且您想跟踪在推出之前的行为，并查看在推出之后的效果，[!UICONTROL 延时表]可并排显示推出前后的行为，以供查看直接影响。[!UICONTROL 延时]表中的预包含单元格是按以下方式计算的用户：在包含时段内符合[!UICONTROL 包含]标准，然后在包含时间之前的时段内符合[!UICONTROL 回访]标准。请注意，[!UICONTROL 延时]表和[!UICONTROL 自定义维度]同类群组不能一起使用。 <br> **[!UICONTROL 自定义维度同类群组]**：创建基于所选维度的同类群组，而不是基于时间的同类群组（默认）。许多客户想要按时间以外的其他方式分析他们的同类群组，现在，通过新的自定义维度同类群组功能，可以灵活地根据他们所选的维度构建同类群组。在 Adobe Analytics 中使用营销渠道、促销活动、产品、页面、区域或任何其他维度，可显示维系率根据这些维度值的不同有何变化。[!UICONTROL 自定义维度]同类群组区段定义仅将维度项目作用作包含时段的一部分，而不是回访定义的一部分。<br>选择[!UICONTROL 自定义维度]同类群组选项后，您可以将所需的任何维度拖放到拖放区域中。这允许您比较同一时段内的类似维度项目。例如，您可以并排比较城市、产品、促销活动等的性能。这会返回您的前 14 个维度项目。但是，您可以使用过滤器（通过悬停在拖动的维度右侧即可访问）仅显示所需的维度项目。[!UICONTROL 自定义维度]同类群组不能与[!UICONTROL 延时]表功能一起使用。 |

1. 通过单击齿轮图标可调整&#x200B;**[!UICONTROL 同类群组表设置]**。

| 设置 | 说明 |
| 仅显示百分比 | 删除数字值，并仅显示百分比。|
| 将百分比近似到最接近的整数 | 将百分比值近似到最接近的整数，而不是显示小数值。|
| 显示平均百分比行 | 在表顶部插入新行，然后添加每列中值的平均值。|

## 构建[!UICONTROL 同类群组分析]报表

1. 单击&#x200B;**[!UICONTROL 生成]**。

   ![步骤结果](assets/cohort-report.png)

   报表会显示下订单的访客（*`Included`* 列）以及在后续访问中回访您网站的访客。随着时间的推移，当出现访问次数减少时，该报表可帮助您查明问题并采取相应的措施。
1. （可选）根据选定的内容创建区段。

   选择单元格（连续的或不连续的），然后右键单击鼠标并选择&#x200B;**[!UICONTROL 根据选定的内容创建区段]**。

1. 在 [Filter Builder](https://docs.adobe.com/content/help/zh-Hans/analytics/components/segmentation/segmentation-workflow/seg-build.html)，进一步编辑区段，然后单击 **[!UICONTROL 保存]**.

   保存后的区段可用于 [!UICONTROL Analysis Workspace] 的[!UICONTROL 区段]面板中。
1. 命名并保存同类群组项目。
1. （可选）[策划并共享](/help/analysis-workspace/curate-share/curate.md)项目组件。

   >[!NOTE]
   >
   >在组织项目之前，必须先保存项目。

