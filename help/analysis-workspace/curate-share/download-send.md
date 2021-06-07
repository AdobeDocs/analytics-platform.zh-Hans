---
description: 您可以通过复制Analysis Workspace或以PDF和CSV格式从Adobe下载数据。
title: 下载 PDF 或 CSV 文件
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
source-git-commit: f74b5e79b6713050869301adb95e2a73705330da
workflow-type: tm+mt
source-wordcount: '1016'
ht-degree: 10%

---

# 下载 PDF 或 CSV 文件

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html?lang=zh-Hans) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

您可以从Analysis Workspace中导出数据的方法有多种不同，具体取决于要在工具外分析的数据集以及需要接收信息的人员。 导出的数据可以采用复制的数据、CSV或PDF文件的形式。 如果您希望将可视化图表包含在文件中，通常首选使用PDF；而如果您只想要纯文本数据，则首选使用CSV（或复制的数据）。

## 将项目下载为CSV或PDF {#download-project}

您可以通过转到&#x200B;**[!UICONTROL 项目>下载为PDF（或为CSV）]**&#x200B;来下载完整项目。 下载的文件包含项目中显示的所有（可见）表格和可视化图表。 如果您希望将可视化图表包含在文件中，通常首选使用PDF；而如果您只想使用纯文本数据，则首选使用CSV。

![](assets/download-project.png)

对于项目下载，请记住：

* 当您请求项目下载时，可以保存或保存项目。 但是，只有保存的项目才能为[scheduled](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html)。
* 在浏览器中下载的PDF可能需要几分钟时间才能导出，因为项目在以PDF格式呈现之前会在Adobe服务器上重新运行。 我们建议在浏览器中下载 PDF 之前不要离开项目。但是，在等待过程中，您仍可以继续对项目进行更改。如果PDF渲染时间超过5分钟，系统会提示您通过电子邮件发送该PDF。
* PDF下载将呈现为单个页面，且不应用分页。
* 在将项目渲染为PDF时，我们会渲染页面上的内容。 如果项目具有自定义大小的可视化和面板，则需要将它们更改为自动调整大小（右上角的按钮），以便内容将不会被截断。

## 将数据复制到剪贴板(热键：Ctrl+C){#copy-data}

右键单击选项&#x200B;**[!UICONTROL 复制到剪贴板]**&#x200B;可让您快速从工作区复制数据并将其粘贴到其他位置。

* 如果希望复制显示的表，请右键单击表标题并选择&#x200B;**将数据复制到剪贴板**。
* 如果要复制数据的子集，请在表中进行选择，然后右键单击> **将选定内容复制到剪贴板**。

此外，热键`Ctrl+C`会将您的选择复制到剪贴板。 复制后，您可以转到其他工具并粘贴信息（或点击`Ctrl+V`）。

![](assets/copy-selection.png)

## 将数据下载为 CSV {#download-data}

右键单击选项&#x200B;**[!UICONTROL 将数据下载为CSV]**&#x200B;允许您将任何可视化的数据表或数据源下载为CSV。

* 在任何表或可视化图表的标题中，右键单击&#x200B;**[!UICONTROL 将数据下载为CSV]**。 这会将表格或基础数据源中显示的数据下载为CSV形式的可视化。 注意：地图可视化图表不支持此选项。
* 如果在表中进行了选择，则选项将显示为&#x200B;**[!UICONTROL 将选定内容下载为CSV]**。 与显示的完整表格相比，仅使用此选项下载所选内容。

![](assets/download-data-viz.png)

## 以 CSV 格式下载项目 {#download-items}

如果要分析表中400行以上可见的数据，请右键单击表标题或任何行，然后选择&#x200B;**将项目下载为CSV(Dimension名称)**。 此选项将针对所选维度导出最多50,000个维度项目（基于表排序），并应用过滤器和过滤器。 如果从表顶部选择此选项，则将导出表中的第一个维度。 虽然自由格式表中未强制实施任何限制，但建议在列数少于20的表中使用下载项目选项，以确保获得最佳性能。

>[!TIP]
>
> 如果您的维度超过50,000个项目，请下载应用了不同排序量度的文件或应用过滤器。 例如，在一次下载中按访问次数降序排序，在第二次下载中按访问次数升序排序。 此提示可帮助您检索较长尾项。

您可以在项目中执行多任务，甚至在下载进行中在同一选项卡中导航到新的工作区项目。 如果您打开新的浏览器选项卡，则下载将会暂停。 如果您完全离开工作区或关闭浏览器选项卡，则下载将取消。

![](assets/download-items.png)

### 下载的项目文件

该表的功能将按如下方式应用于下载的文件：

* 所有面板过滤器都作为过滤器应用。
* 划分&#x200B;**在**&#x200B;上方的表中选定的维度将作为过滤器应用于每列上方。
* 将删除&#x200B;**下面的划分**&#x200B;表中的选定维度。

在以上示例中，页面项目是通过面板过滤器（新访客客户）和作为过滤器应用的上述组件（营销渠道=电子邮件）来下载的，以下组件（移动设备类型）是从下载的CSV中删除的。

![](assets/downloaded-file.png)

### 下载通知

在文件下载时，您将看到一则包含进度的信息性通知。 您可以随时通过单击&#x200B;**[!UICONTROL 取消下载]**&#x200B;来取消下载。 关闭toast **将不会**&#x200B;取消下载。

文件完成后，您将看到一则完成通知，该文件将下载到您的浏览器。

如果您一次请求多次下载，您将收到一则通知，告知每次额外下载都将排入队列，直到上次下载完成为止。

![](assets/toast.png)

## 常见问题解答 {#faq}

| 问题 | 回答 |
| --- | --- |
| 为什么我下载的PDF为1页？ | 工作区当前不会为下载的PDF分页。 |
| 我能否通过“以CSV格式下载项目”选项导出50,000多个项目？ | 虽然每次下载最多可包含50,000个维度项目，但您可以更改表的排序以检索较长的尾项目，或应用过滤器以下载更多特定项目。 |
| **[!UICONTROL 复制可视化图表]**&#x200B;有何用途？ | **[!UICONTROL 复制]** 可视化不是导出选项。它允许您将可视化图表或面板从工作区中的一个位置复制到另一个位置。 例如，在同一项目中从一个面板到另一个面板，或从一个项目到另一个项目。 [内部链接视频](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |
