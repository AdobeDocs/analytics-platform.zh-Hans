---
description: 了解如何使用行设置，以及行设置如何因您拖入Analysis Workspace中自由格式表的组件而异。
title: 行设置
feature: Visualizations
exl-id: a9438d83-498d-4b22-9e5e-c357bd3a2680
role: User
TQID: https://experienceleague.adobe.com/qQKmobJ4J1RPezRG-hk38l7JNioIshzjMaKXWVoUWsM
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: c73c4213-d623-4126-81f4-80b42e5e2656id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: bc7a5a86-1a70-451f-985c-037b65f091d1id: cb6c7d24-631f-46e5-9e39-3a2705f73962id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: b988d8cee94e40c6bed62f7ef22f209b7e38f46c
workflow-type: tm+mt
source-wordcount: 1630
ht-degree: 53%

---

# 行设置

行设置因您拖入到表格中的组件而异。 要访问表格行设置，请选择每个对象中的维度、区段、量度、时间段或划分旁边的![设置](/help/assets/icons/Setting.svg) **[!UICONTROL 设置]**。

![自由格式表突出显示量度的设置图标](assets/row-settings.png)

| 设置 | 描述 |
| --- | --- |
| **[!UICONTROL 按位置细分]** | 默认情况下，此设置处于禁用状态，并且细分固定在静态行项目。 例如，假设您按营销渠道细分排名前 3 的“页面”维度项（主页、搜索结果、结账）。 然后，您离开项目，两周后返回。 再次打开项目时，排名前 3 的页面已更改，此时“主页”、“搜索结果”和“结账”页面成为排名第 4-6 的页面。 默认情况下，营销渠道划分仍将显示在“主页”、“搜索结果”和“结账”下方，即使三者现在分别位于第4-6行中。<br> 相反，**按位置**&#x200B;划分始终划分排名前3的项目，而不管它们具体是什么。 回顾该示例，当您重新打开项目时，营销渠道细分与表中排名前 3 的页面相关联。 而不是与“主页”、“搜索结果”和“结帐”相关联，这三项现在分别位于第 4-6 行中。 |
| **[!UICONTROL 百分比]** | **按列计算百分比**（默认）：单元格中显示的百分比是根据列总数计算的。 <br>**按行计算百分比**：单元格中的百分比是按行计算的，而不是沿列向下计算，以全部总计作为分母。 该计算方式对显示百分比趋势特别有用。 |
| **[!UICONTROL 列总计]** | 这些设置仅可用于[静态行](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md)。<br> **显示为当前行的总和**&#x200B;将显示表中行的客户端总和，这意味着总计&#x200B;*不会*&#x200B;去除重复量度，如访问次数或人员。<br> **显示全部总计**&#x200B;将显示服务器端总和，这意味着去除重复量度的总计。 |

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [自由格式表中的行和列设置](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/row-and-column-settings-in-freeform-tables){target="_blank"}以获取演示视频。

{{videoaa}}

>[!ENDSHADEBOX]

## 更改行计数

要更改显示的行数，请执行以下步骤：

1. 单击表格第一列顶部&#x200B;**[!UICONTROL 行数]**&#x200B;旁边的数字。

   ![自由格式表，显示所显示行数的下拉菜单。 选择了 400 行。](assets/change-row-count.gif)

1. 从下拉菜单中，选择您希望表显示的行数。


## Context-menu

选择维度标题时，以下上下文菜单选项可用。

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 将选择复制到剪贴板]** | 将可视化图表中的选择复制到剪贴板上。 |
| **[!UICONTROL 将项目下载为 CSV（*维度名称*）]** | 将可视化图表的维度项（最多 50,000 个）立即下载到本地设备。 所选维度最多可有 50,000 个维度项。 |
| **[!UICONTROL 将选择下载为 CSV]** | 立即将可视化图表的维度项下载到您的本地设备。 |
| **[!UICONTROL 为所有维度项创建超链接]** | 为所有维度项创建超链接。 请参阅[为自由格式表中的维度对超链接进行操作](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 为所有维度项编辑超链接]** | 为所有维度项编辑超链接。 请参阅[为自由格式表中的维度对超链接进行操作](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 为所有维度项移除超链接]** | 为所有维度项移除超链接。 请参阅[为自由格式表中的维度对超链接进行操作](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 删除]** | 从表中删除维度。 |
| **[!UICONTROL 可视化]** | 使用任何可用的可视化图表将维度可视化。 |
| **[!UICONTROL 仅显示选定的行]** | 仅显示可视化图表中选定的项目。 |
| **[!UICONTROL 从选择创建注释]** | 打开&#x200B;**[!UICONTROL 注释详细信息]**&#x200B;以添加注释。 |


在自由格式表中选择一个或多个维度项目（第一列）或一个或多个单个单元格时，可以使用以下其他上下文菜单选项。

| 选项 | 描述 |
| --- | --- |
| **[!UICONTROL 将选择复制到剪贴板]** | 复制自由格式表选定单元格中的信息。 |
| **[!UICONTROL 将项目下载为 CSV（*维度名称*）]** | 将可视化图表的维度项（最多 50,000 个）立即下载到本地设备。 所选维度最多可有 50,000 个维度项。 |
| **[!UICONTROL 创建超链接]** | 为项目创建超链接。 请参阅[为自由格式表中的维度对超链接进行操作](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 编辑超链接]** | 为项目编辑超链接。 请参阅[为自由格式表中的维度对超链接进行操作](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 移除超链接]** | 为项目移除超链接。 请参阅[为自由格式表中的维度对超链接进行操作](../freeform-table-hyperlinks.md) |
| **[!UICONTROL 将选择下载为 CSV]** | 立即将可视化图表的维度项下载到您的本地设备。 |
| **[!UICONTROL 删除选定项]** | 删除所选行。 |
| **[!UICONTROL 从选定范围中创建警报]** | 打开[警报生成器](/help/components/c-intelligent-alerts/alert-builder.md)以从所选内容生成警报。 |
| **[!UICONTROL 细分]** | 划分维度项。 从&#x200B;**[!UICONTROL 维度]**、**[!UICONTROL 量度]**、**[!UICONTROL 区段]**&#x200B;或&#x200B;**[!UICONTROL 日期范围]**&#x200B;的列表中进行选择。 使用&#x200B;*搜索*&#x200B;来替代搜索组件。 |
| **[!UICONTROL 可视化]** | 使用任何可用的可视化图表显示所选内容。 |
| **[!UICONTROL 趋势选择]** | 为选择创建趋势线形图可视化图表。 |
| **[!UICONTROL 仅显示选定的行]** | 仅显示可视化图表中选定的行。 |
| **[!UICONTROL 显示所有行]** | 显示可视化图表中的所有行。 |
| **[!UICONTROL 重命名所选行]** | 重命名所选行。 在&#x200B;**[!UICONTROL 重命名所选行]**&#x200B;对话框中输入&#x200B;**[!UICONTROL 名称]**。 选择&#x200B;**[!UICONTROL 确定]**&#x200B;以确认，或选择&#x200B;**[!UICONTROL 取消]**&#x200B;以取消。 重命名自由格式表中的行后，标题列中的维度名称将附加&#x200B;**[!UICONTROL （已修改）]**，并且有![齿轮](/help/assets/icons/Gear.svg)图标可用于重置维度标题列中的已修改行。 请参阅[内联分类](#inline-classifications)。 |
| **[!UICONTROL 合并所选行]** | 合并所选行。 在&#x200B;**[!UICONTROL 合并所选行]**&#x200B;对话框中输入&#x200B;**[!UICONTROL 名称]**。 选择&#x200B;**[!UICONTROL 确定]**&#x200B;以确认，或选择&#x200B;**[!UICONTROL 取消]**&#x200B;以取消。 组合自由格式表中的行后，标题列中的维度名称将附加&#x200B;**[!UICONTROL （已修改）]**，并且有![齿轮](/help/assets/icons/Gear.svg)图标可用于重置维度标题列中的已修改行。 请参阅[内联分类](#inline-classifications)。 |
| **[!UICONTROL 将修改的行创建为派生字段]** | *您必须是Customer Journey Analytics产品管理员才能看到此上下文菜单选项。*<br/>&#x200B;在自由格式表的任何选定行上可用，该表因重命名或组合行而被修改。 选中后，[派生字段界面](/help/data-views/derived-fields/derived-fields.md#create-a-derived-field)将打开，其中包含您已预填充的对自由格式表所做的修改。 请参阅[内联分类](#inline-classifications)。 |
| **[!UICONTROL 从选择创建注释]** | 打开[Annotation Builder](/help/components/annotations/create-annotations.md#annotation-builder)以生成所选内容的注释。 |
| **[!UICONTROL 从选定范围中创建区段]** | 打开[区段生成器](/help/components/segments/seg-builder.md)以从所选内容生成区段。 |
| **[!UICONTROL 从选择创建受众]** | 打开[受众生成器](/help/components/audiences/publish.md#audience-builder)以从所选内容生成受众。 |

选择量度列标题时，可以使用以下附加上下文菜单选项。

| 选项 | 描述 |
|---|---|
| **[!UICONTROL 从选择创建量度]** | 从选定量度创建新的量度。 度量可以是平均值、中间值、列最大值、列最小值、列总和。 您还可以在计算量度生成器中选择“打开”来创建计算量度。 |
| **[!UICONTROL 添加时间段列]** | 添加时间段列。 您有多个选项可供选择，其中面板的日程表范围决定了&#x200B;*日期范围*： <ul><li>从&#x200B;**[!UICONTROL 以前的&#x200B;*日期范围*到此日期范围]**</li><li>从&#x200B;**[!UICONTROL 这些&#x200B;*日期范围*到此日期范围]**。</li><li>**[!UICONTROL 将日期范围自定义为此日期范围]**。 打开&#x200B;**[!UICONTROL 日期范围生成器]**，指定日期范围。</li></ul>有关更多信息，请参阅[日期比较](/help/components/date-ranges/time-comparison.md)。 |
| **[!UICONTROL 比较时间段]** | 添加比较时间段的列。 仅当维度不是基于时间时才可用。 您可以通过多个选项来确定&#x200B;*日期范围*： <ul><li>从&#x200B;**[!UICONTROL 以前的&#x200B;*日期范围*到此日期范围]**</li><li>**[!UICONTROL 将日期范围自定义为此日期范围]**。 打开&#x200B;**[!UICONTROL 日期范围生成器]**，指定日期范围。</li></ul>有关更多信息，请参阅[日期比较](/help/components/date-ranges/time-comparison.md)。 |
| **[!UICONTROL 修改归因模型]** | 修改该列的归因模型。 |
| **[!UICONTROL 比较归因模型]** | 指定一个新的归因模型并将其与所选列的归因模型进行比较。 添加了包含新归因模型量度的新列。 此外，还添加了百分比变化列以便进行比较。 |
| **[!UICONTROL 重置列宽]** | 将列宽重置为默认宽度。 |
| **[!UICONTROL 从选择创建注释]** | 打开[Annotation Builder](/help/components/annotations/create-annotations.md#annotation-builder)以生成所选内容的注释。 |
| **[!UICONTROL 从选定范围中创建区段]** | 打开[区段生成器](/help/components/segments/seg-builder.md)以从所选内容生成区段。 |
| **[!UICONTROL 从选择创建受众]** | 打开[受众生成器](/help/components/audiences/publish.md#audience-builder)以从所选内容生成受众。 |


## 更改行高

您可以将项目的[视图密度](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/build-workspace-project/view-density)设置为&#x200B;**[!UICONTROL 紧凑]**、**[!UICONTROL 舒适]**&#x200B;和&#x200B;**[!UICONTROL 展开]**。


## 内联分类 {#inline-classifications-example}

{{release-limited-testing-section}}

使用内联分类，您可以重命名或组合自由格式表中的行。 以及从表中修改的行创建派生字段。

以下示例说明如何使用&#x200B;**[!UICONTROL 重命名选定行]**、**[!UICONTROL 合并选定行]**&#x200B;和&#x200B;**[!UICONTROL 将修改的行创建为派生字段]**&#x200B;上下文菜单选项。 以及如何重置修改后的自由格式表。

* 将&#x200B;**[!UICONTROL 无值]**&#x200B;行重命名为&#x200B;**[!UICONTROL Other]**。

  1. 从所选&#x200B;**[!UICONTROL 无值]**&#x200B;行的上下文菜单中选择&#x200B;**[!UICONTROL 重命名所选行]**。

     ![选择“重命名所选行上下文”菜单选项](assets/context-rename.png)

  1. 在&#x200B;**[!UICONTROL 重命名所选行]**&#x200B;对话框中：

     ![重命名选定的行对话框](assets/dialog-rename.png)

     1. 输入<code>其他</code> 用于&#x200B;**[!UICONTROL 名称]**。
     1. 选择&#x200B;**[!UICONTROL 确定]**。

* 将&#x200B;**[!UICONTROL 男性]**&#x200B;和&#x200B;**[!UICONTROL 女性]**&#x200B;行合并为一个&#x200B;**[!UICONTROL 成年人]**&#x200B;行。

  1. 选择&#x200B;**[!UICONTROL 男性]**&#x200B;和&#x200B;**[!UICONTROL 女性]**&#x200B;行。
  1. 从上下文菜单中选择&#x200B;**[!UICONTROL 合并所选行]**。

     ![选择“合并所选行”菜单选项](assets/context-combine.png)

  1. 在&#x200B;**[!UICONTROL 合并所选行]**&#x200B;对话框中：

     ![合并所选行对话框](assets/dialog-combine.png)

     1. 输入<code>成年人</code> 用于&#x200B;**[!UICONTROL 名称]**。
     1. 选择&#x200B;**[!UICONTROL 确定]**。

* 根据自由格式表中的修改创建派生字段。

  1. 从上下文菜单中，为修改后的表格中的任何选定行选择&#x200B;**[!UICONTROL 将修改的行创建为派生字段]**。

     ![选择“将修改的行创建为派生字段菜单”选项](assets/context-derived.png)

  1. 根据在表中进行的所有修改，检查、修改和保存派生字段的定义（可选）。

     ![创建派生字段对话框](assets/dialog-derived.png)

* 将自由格式表重置为修改前的状态。

  1. 选择&#x200B;**[!UICONTROL _维度名称&#x200B;_（已修改）]**旁边的![齿轮](/help/assets/icons/Gear.svg)。
  1. 从&#x200B;**[!UICONTROL 已修改行]**&#x200B;弹出窗口中选择&#x200B;**[!UICONTROL 重置已修改行]**。

     ![重置自由格式表](assets/popup-reset.png)
