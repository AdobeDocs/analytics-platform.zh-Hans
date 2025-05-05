---
description: 在Analysis Workspace中创建一个同类群组表并运行同类群组分析。
keywords: Analysis Workspace
title: 配置同类群组表
feature: Visualizations
exl-id: c3fd9fbf-b2c8-4703-92de-e6fdc141ebc6
role: User
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '943'
ht-degree: 86%

---

# 配置同类群组表

要创建并配置[!UICONTROL 同类群组表]：

1. 添加 ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL 同类群组表]**&#x200B;可视化图表。请参阅[将可视化图表添加到面板](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel)。

1. 按照下表所示，定义&#x200B;**[!UICONTROL 包含标准]**、**[!UICONTROL 回访标准]**、**[!UICONTROL 同类群组类型]**&#x200B;和&#x200B;**[!UICONTROL 设置]**。

   ![配置同类群组表](assets/cohort-configure.png)

   | 元素 | 描述 |
   |--- |--- |
   | **[!UICONTROL 包含标准]** | 您最多可以应用 10 个包含区段和 3 个包含量度。量度指定用户属于哪个同类群组。例如，假设包含量度是“订单”，那么只有在同类群组分析的时间范围内下达了订单的用户才会包含在初始同类群组中。<br>这些量度之间的默认运算符是 AND，但您可以将其更改为 OR。此外，您还可以向这些量度添加数值分段。 例如：`Sessions >= 1`。</br> |
   | **[!UICONTROL 回访标准]** | 您最多可以应用 10 个回访区段和 3 个回访量度。回访量度指示用户是已维系还是流失。例如，假设回访量度是“视频查看”，那么只有在后续时间范围（即，当用户添加到同类群组后的时间期限）内查看了视频的用户才会显示为已维系。另一个符合维系要求的量度是“会话”。 |
   | [!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}<br/>**[!UICONTROL 容器&#x200B;]** | 默认情况下，同类群组分析会绑定到人员容器。 如果从支持Workspace项目的基于帐户的连接中获得更多人员以外的容器，则可以从&#x200B;**[!UICONTROL 容器]**&#x200B;下拉菜单中选择另一个容器进行同类群组分析。 |
   | **[!UICONTROL 粒度]** | 由“天”、“周”、“月”、“季度”或“年”组成的时间粒度。 |
   | **[!UICONTROL 类型]** | **[!UICONTROL 维系率]**（默认）：**[!UICONTROL 维系率]**&#x200B;同类群组衡量一段时间内同类人员回访您的属性的程度。维系率同类群组是标准同类群组，该同类群组指示用户的回访和重复行为。在表格中，绿色表示[!UICONTROL 维系率]同类群组。<br>**[!UICONTROL 流失率&#x200B;]**：**[!UICONTROL &#x200B;流失率&#x200B;]**（也称为减少或流失）同类群组衡量一段时间内同类人员如何从您的属性中流失。流失率与维系率相反：`Churn = 1 - Retention`。[!UICONTROL 流失率]会显示客户有多久没有回访，从而可以很好地衡量吸引力和商机。您可以使用流失率来分析和识别焦点区域：哪些同类群组区段可能会被吸引过来？ 在表格中，红色表示[!UICONTROL 流失率]同类群组（类似于&#x200B;**[!UICONTROL &#x200B;流量&#x200B;]**&#x200B;可视化图表中的流失）。</br> |
   | **[!UICONTROL 设置]** | **[!UICONTROL 滚动计算]**：根据上一列而不是包含的列（默认）计算维系率或流失率。[!UICONTROL 滚动计算]会更改“回访”时间段的计算方法。正常计算会找到符合回访标准且属于包含时段的用户。无论他们是否属于上一时段的同类群组。相反，[!UICONTROL 滚动计算]会查找符合“回访”标准且包含在上一时间段的用户。因此，[!UICONTROL 滚动计算]将分段并筛分出一段时间内持续满足“回访”标准的用户。 [!UICONTROL 回访]标准将应用于选定时段之前的每个时段。</br><br>**[!UICONTROL 延迟表&#x200B;]**：[!UICONTROL 事件表]衡量包含事件发生之前和之后经过的时间。[!UICONTROL 延迟表]非常适合事件发生之前/之后的分析。例如，您即将推出一款产品或发布营销活动，并且想要跟踪活动发布前后的行为。[!UICONTROL 延迟表]并排显示事件发生之前和之后的行为，以查看直接影响。[!UICONTROL 延迟表]中的预包含单元格计算在包含时段内符合[!UICONTROL 包含]标准，然后在包含时间之前的时段内符合[!UICONTROL 回访]标准的用户。请注意，[!UICONTROL 延迟表]和[!UICONTROL 自定义维度同类群组]不能一起使用。</br><br>**[!UICONTROL 自定义维度同类群组]**：创建基于所选维度的同类群组，而不是基于时间的同类群组（默认）。许多客户想要按时间以外的其他方式分析他们的同类群组，现在，通过新的自定义维度同类群组功能，可以灵活地根据他们所选的维度生成同类群组。使用营销渠道、营销活动、产品、页面、区域或任何其他维度，可显示维系率根据这些维度值的不同有何变化。[!UICONTROL 自定义维度]同类群组区段定义仅将维度项目作用作包含时段的一部分，而不是回访定义的一部分。</br><br>选择[!UICONTROL 自定义维度同类群组]选项后，您可以将所需的任何维度拖放到拖放区域中。通过添加维度，您可以比较同一时间段内的类似维度项。例如，您可以并排比较城市、产品、营销活动等的性能。同类群组表返回您的前 14 项维度。但是，您可以使用![区段](/help/assets/icons/Filter.svg)区段来仅显示所需的维度项。 [!UICONTROL 自定义维度同类群组]不能与[!UICONTROL 延迟表]功能一起使用。</br> |

1. 单击&#x200B;**[!UICONTROL 生成]**。
1. 要重新配置[!UICONTROL 同类群组表]，请选择![编辑](/help/assets/icons/Edit.svg)。

1. （可选）根据选定的内容创建区段或受众。

   选择单元格（连续的或不连续的），然后右键单击鼠标并选择&#x200B;**[!UICONTROL 根据选定的内容创建区段]**。

   ![创建区段或受众](assets/retention-createfilter.png)

1. 在[区段生成器](/help/components/filters/filter-builder.md)中，进一步编辑该区段，然后单击&#x200B;**[!UICONTROL 保存]**。

   保存后的区段可用于 [!UICONTROL Analysis Workspace] 的[!UICONTROL 区段]面板中。

## 设置

您可以为[!UICONTROL 同类群组表]定义特定设置。

1. 选择![设置](/help/assets/icons/Setting.svg)以调整[!UICONTROL 同类群组表]设置。

   | 设置 | 描述 |
   |---|---|
   | **仅显示百分比** | 删除数值，仅显示百分比。 |
   | **将百分比四舍五入到最接近的整数** | 将百分比值四舍五入到最接近的整数，而不是显示十进制值。 |
   | **显示平均百分比行** | 在表顶部插入新行，然后添加每列中值的平均值。 |


>[!MORELIKETHIS]
>
>[将可视化图表添加到面板](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[可视化图表设置](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[可视化图表上下文菜单](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

