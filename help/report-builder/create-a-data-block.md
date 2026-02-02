---
title: 在Report Builder中创建数据块
description: 了解如何创建数据块。
role: User
feature: Report Builder
type: Documentation
exl-id: 46382621-d5e1-41d6-865c-782ec28a21fa
solution: Customer Journey Analytics
source-git-commit: 31d3b40ad7a081aefa4297d7f4a3b986711ead03
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 23%

---

# 创建一个数据块

*数据块*&#x200B;是由单个数据请求创建的数据的表。Report Builder 工作簿可以包含多个数据块。创建数据块时，首先配置数据块，然后构建数据块。

## 配置数据块

为数据块位置、数据视图和日期范围配置初始数据块参数。

1. 选择![AddCircle](/help/assets/icons/AddCircle.svg) **[!UICONTROL 创建]**。

   ![显示“创建数据块”选项的屏幕快照](./assets/create-data-block.png){zoomable="yes"}


1. 设置&#x200B;**[!UICONTROL 数据块位置]**。

   数据块位置选项定义Report Builder将数据添加到工作表的工作表位置。

   要指定数据块位置，请在工作表中选择单个单元格或输入单元格地址，如`a3`、`\\\$a3`、`a\\\$3`或`sheet1!a2`。 在检索数据时，指定的单元格将出现在数据块的左上角。

   使用![DataBlockSelector](/help/assets/icons/DataBlockSelector.svg)从工作表中当前选定的单元格中选取数据块位置。

1. 选择&#x200B;**[!UICONTROL 数据视图]**。

   使用数据视图选项，您可以从下拉菜单中选择数据视图，或者从单元格位置引用数据视图。

   选择![DataViewSelector](/help/assets/icons/DataViewSelector.svg)以从单元格创建数据视图。

1. 设置&#x200B;**[!UICONTROL 日期范围]**。

   **[!UICONTROL 日期范围]**&#x200B;选项允许您选择日期范围。 日期范围可以是固定的，也可以是滚动的。

   选择&#x200B;**[!UICONTROL 日历]**&#x200B;以使用![日历](/help/assets/icons/Calendar.svg)选择数据范围，或手动输入日期范围。 或者，您可以从&#x200B;**[!UICONTROL _搜索预设_]**&#x200B;下拉菜单中选择预设。

   选择&#x200B;**[!UICONTROL 从单元格]**&#x200B;以根据当前工作表中的单元格定义开始和结束数据。

   有关日期范围选项的信息，请参阅[选择日期范围](select-date-range.md)。

1. 选择&#x200B;**[!UICONTROL 下一步]**。

   ![显示日期范围选项和活动“下一步”按钮的屏幕截图。](./assets/choose_date_data_view3.png)

   配置数据块后，您可以选择维度、量度和区段来构建数据块。 **[!UICONTROL 维度]**、**[!UICONTROL 量度]**&#x200B;和&#x200B;**[!UICONTROL 区段]**&#x200B;选项卡显示在&#x200B;**[!UICONTROL 表]**&#x200B;窗格的上方。

## 构建数据块

要构建数据块，请选择报表组件，然后自定义版面。

1. 添加&#x200B;**[!UICONTROL 维度]**、**[!UICONTROL 量度]**&#x200B;和&#x200B;**[!UICONTROL 区段]**&#x200B;组件。

   滚动组件列表或使用![搜索](/help/assets/icons/Search.svg) **[!UICONTROL _搜索组件_]**&#x200B;字段来查找组件。 将组件拖放到[!UICONTROL 表]窗格或双击列表中的组件名称以将该组件添加到[!UICONTROL 表]窗格。

   双击组件以将该组件添加到表的默认部分。

   - Dimension组件已添加到![TableSelectRow](/help/assets/icons/TableSelectRow.svg) **[!UICONTROL Row]**&#x200B;部分或![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**&#x200B;部分（如果列中已有维度）。
   - 日期组件已添加到![TableSelectColumn](/help/assets/icons/TableSelectColumn.svg) **[!UICONTROL Column]**&#x200B;部分。
   - 区段组件已添加到![分段](/help/assets/icons/Segmentation.svg) **[!UICONTROL 区段]**&#x200B;部分。
   - 已将量度组件添加到![事件](/help/assets/icons/Event.svg) **[!UICONTROL 值]**&#x200B;部分。

1. 在“表”窗格中排列项目以自定义数据块的版面。

   拖放“表”窗格中每个列表中的组件以重新排列组件，或者选择![MoreSmall](/help/assets/icons/MoreSmall.svg)并选择![向上箭头](/help/assets/icons/ArrowUp.svg)上移、![向下箭头](/help/assets/icons/ArrowDown.svg)下移等等，以在列表中移动组件。

   将组件添加到表时，数据块的预览显示在工作表中的“数据块”位置。在表中添加、移动或删除项目时，数据块版面的预览自动更新。

   ![显示已添加组件和已更新工作表的屏幕截图。](./assets/image10.png)


1. （可选）将&#x200B;**[!UICONTROL 开始日期]**&#x200B;设置为维度，以标识数据块的开始日期。 如果您有一个具有滚动日期范围的定期计划报表，则将开始数据添加为维度会很有帮助。 或者，如果您有非常规的日期范围，并且需要明确说明开始日期。

   ![显示维度列表中开始日期的屏幕截图。](./assets/start-date-dimension.png)

1. （可选）显示或隐藏行和列标题。 操作方法：

   1. 选择&#x200B;**[!UICONTROL 表]** ![设置](/help/assets/icons/Setting.svg)设置图标。

      ![显示“表设置”选项的屏幕截图。](./assets/table-settings.png)

   1. 选中或取消选中&#x200B;**[!UICONTROL 显示行和列标题]**&#x200B;的选项。 默认显示标题。

1. 或者，您也可以隐藏或显示维度标签和量度标题。 操作方法：

   1. 在维度标签或列标题上选择![MoreSmall](/help/assets/icons/MoreSmall.svg)以显示上下文菜单。

      ![行节中的省略号图标。](./assets/row-heading.png)

   1. 选择![VisibilityOff](/help/assets/icons/VisibilityOff.svg) **[!UICONTROL Hide]**&#x200B;或![Visibility](/help/assets/icons/Visibility.svg) **[!UICONTROL Show]**&#x200B;切换维度标签或列标题。 默认显示所有标签。

1. 选择&#x200B;**[!UICONTROL 完成]**&#x200B;以完成数据块的配置。

1. 检索分析数据时显示处理消息&#x200B;**[!UICONTROL #BUSY]**。

   ![正在处理邮件。](./assets/image11.png)

1. Report Builder 检索数据并在工作表中显示已完成的数据块。

   ![已完成的数据块。](./assets/image12.png)


>[!MORELIKETHIS]
>
>[选择数据视图](select-data-view.md)
>[选择日期范围](select-date-range.md)
>[筛选维度](filter-dimensions.md)
>[使用区段](work-with-filters.md)
>
