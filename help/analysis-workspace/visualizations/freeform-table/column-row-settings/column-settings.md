---
description: 了解如何编辑列设置以配置列格式，其中一些可以是条件格式。
title: 列设置
feature: Visualizations
exl-id: b41d8a12-e8d9-405c-ac71-6567397aec6b
role: User
source-git-commit: 6a279ac39e6b94200ff93ac1a3796d202e6349c7
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 21%

---

# [!UICONTROL 列设置]

[!UICONTROL 列设置]允许您配置列格式，其中一些可以是条件格式。

+++ 观看此功能的视频演示。

>[!VIDEO](https://video.tv.adobe.com/v/40382/?quality=12)

{{videoaa}}

+++

要访问[!UICONTROL 列设置]，请在列标题中选择![列设置](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Settings_18_N.svg)。

![列设置](assets/column-settings.png)


您可以同时编辑多个列的设置。 选择多个列，然后在任意一个选定的列中选择![设置](/help/assets/icons/Setting.svg)。 您所做的任何更改都将应用到所有列中，并在这些列中选择单元格。

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 显示总计]** | 显示列的客户端总和。 此总计&#x200B;**未**&#x200B;删除重复的量度，如会话或人员。 |
| **[!UICONTROL 显示总计]** | 显示列的服务器端总和。 总计会去除重复的量度，如会话或人员。 |
| **[!UICONTROL 显示迷你图]** | 在列标题中显示折线图。 |
| **[!UICONTROL 数值]** | 确定单元格是否显示/隐藏量度的数值。 例如，如果量度是“页面查看次数”，则数值是行项目的页面查看次数。 |
| **[!UICONTROL 百分比]** | 确定单元格是否显示/隐藏量度的百分比值。 例如，如果量度是“页面查看次数”，则百分比值是行项目的页面查看次数除以列的页面查看总数。  注意：百分比大于100%是可能的，以确保准确无误。 上限上限可以移动到1,000%，以防止列宽变得过大。 |
| **[!UICONTROL 显示异常]** | 确定是否对此列中的值运行异常检测。 |
| **[!UICONTROL 显示预测]** | 确定此列中是否显示预测值。 |
| **[!UICONTROL 标题文本换行]** | 自由格式表中的标头文本换行，以使标头更加易读，表格更易共享。 包装对于PDF渲染和名称较长的量度非常有用。 默认处于启用状态。 |
| **[!UICONTROL 将零解释为没有值]** | 对于具有0值的单元格，确定是显示0还是显示空白单元格。 当您查看一个月中每一天的数据，并且某些天是未来时，这种解释非常有用。  对于未来的日期，不会显示0，而是显示空白单元格。 图表也遵循此设置（即，图表不显示值为0的线形或条形图）。 |
| **[!UICONTROL 背景]** | 确定单元格是否显示/隐藏所有单元格格式，包括条形图和条件格式。 |
| **[!UICONTROL 条形图]** | 显示一个水平条形图，表示单元格相对于列总数的值。 |
| **[!UICONTROL 条件格式]** | 使用条件格式。 请参阅下面的[部分](#conditional-formatting)。 |
| **[!UICONTROL 表单元格预览]** | 预览应用当前所选格式选项时每个单元格的显示方式。 |
| **[!UICONTROL 使用非默认的属性模型]** | 使用非默认归因模型。 请参阅下面的[部分](#use-non-default-attribution-model)。 |

## 条件格式 {#conditional-formatting}

条件格式将格式应用于由您定义的上限、中点和下限。除非选择了[!UICONTROL 自定义]限制，否则对于各种划分，还将在自由格式表中自动应用条件格式。

![条件格式](./assets/conditional-formatting.png)

| 条件格式选项 | 描述 |
| --- | --- |
| **[!UICONTROL 使用百分比限制]** | 将限制范围更改为基于百分比而不是绝对值。百分比限制范围适用于完全基于百分比的量度（如跳出率）以及具有计数和百分比的量度（如页面查看次数）。 |
| **[!UICONTROL 自动生成]** | 根据数据自动计算上限/中值/下限。上限为此列中的最大值。下限为最小值，中点为上限和下限的平均值。 |
| **[!UICONTROL 自定义]** | 手动分配&#x200B;**[!UICONTROL 上限]**、**[!UICONTROL 中点]**&#x200B;和&#x200B;**[!UICONTROL 下限]**。 限制提供了灵活性，可用于确定列值何时为好、中或差。 |
| **[!UICONTROL 条件格式调色板]** | 将预配置的颜色集应用到单元格。 根据您选择的四种可用配色方案中的哪一种，不同的颜色将分配给高值、中点值和低值。 <br>替换表中的维度会重置条件格式限制。替换量度会重新计算此列的限制（其中，量度在 X 轴上，维度在 Y 轴上）。 |

## 使用非默认的属性模型 {#use-non-default-attribution-model}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_column_usenondefaultattributionmodel"
>title="使用非默认的属性模型"
>abstract="为所选列启用非默认的归因模型。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_workspace_freeformtable_column_usenondefaultattributionmodel_disabled"
>title="使用非默认的属性模型"
>abstract="非默认归因模式不可用于此量度。"

<!-- markdownlint-enable MD034 -->



您可以覆盖在[数据视图](/help/data-views/component-settings/attribution.md)中配置的默认归因模型。

>[!NOTE]
>
>将组件的归因更新为非默认归因模型时，请考虑以下事项：
>
>* **在具有&#x200B;*单个维度*：**&#x200B;的报表中使用组件时，如果使用非默认归因模型，组件的归因将忽略分配模型。
>
>* **在具有&#x200B;*多个维度*：**&#x200B;的报表中使用组件时，如果使用了非默认归因模型，则组件的归因将保留分配模型。
>
>   仅当[将数据导出到云](/help/analysis-workspace/export/export-cloud.md)时，多个维度才可用。
>
> 有关分配的更多信息，请参阅[持久性组件设置](/help/data-views/component-settings/persistence.md)。

要对Analysis Workspace中的量度使用非默认归因模型，请执行以下操作：

1. 选择&#x200B;**[!UICONTROL 使用非默认归因模型]**。 如果已选择，请使用&#x200B;**[!UICONTROL 编辑]**&#x200B;来编辑归因模型。 或取消选择以返回到默认归因模型。

   ![列设置选项突出显示“数据设置”选项：使用非默认归因模式。](assets/attribution-checkbox.png)

2. 在&#x200B;**[!UICONTROL 列归因模型]**&#x200B;中，选择&#x200B;**[!UICONTROL 模型]**&#x200B;和&#x200B;**[!UICONTROL 回顾时间范围]**。 回顾窗口确定应用于每次转换的数据归因窗口。

   ![显示线性选择的列归因模型选项。](assets/attribution-select.png)


### 归因模型

{{attribution-models-details}}

### 回顾时间范围

{{attribution-lookback-window}}



>[!MORELIKETHIS]
>
>* [管理数据源](/help/analysis-workspace/visualizations/t-sync-visualization.md)
