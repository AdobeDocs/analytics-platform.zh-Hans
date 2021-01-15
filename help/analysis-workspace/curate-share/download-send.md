---
description: 您可以通过复制数据或以PDF和CSV格式从Analysis Workspace下载数据。
title: 下载 PDF 或 CSV 文件
translation-type: tm+mt
source-git-commit: d14817f28e757e94435c3b1059765fabe7cec54b
workflow-type: tm+mt
source-wordcount: '1022'
ht-degree: 12%

---


# 下载 PDF 或 CSV 文件

>[!NOTE]
>
>您正在查看有关 Customer Journey Analytics 中 Analysis Workspace 的文档。其功能集与[传统 Adobe Analytics 中的 Analysis Workspace](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html) 略有不同。[了解更多...](/help/getting-started/cja-aa.md)

您可以通过多种不同的方式从Analysis Workspace导出数据，具体取决于要在工具外分析的数据集以及哪些人需要接收信息。 导出的数据可以采用复制的数据、CSV或PDF文件的形式。 如果您希望将可视化包含在文件中，则通常首选PDF；而如果您只想要纯文本数据，则首选CSV（或复制的数据）。

## 将项目下载为CSV或PDF {#download-project}

要下载完整项目，请转到&#x200B;**[!UICONTROL 项目>下载为PDF（或CSV）]**。 下载的文件包含项目中显示的所有（可见）表和可视化。 如果您希望将可视化包含在文件中，则通常首选PDF；而如果您只希望纯文本数据，则首选CSV。

![](assets/download-project.png)

对于项目下载，请牢记：

* 当您请求项目下载时，可以保存或保存项目。 但是，只有已保存的项目可以是[scheduled](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html)。
* 在浏览器中下载的PDF可能需要几分钟时间才能导出，因为项目在以PDF格式呈现之前在Adobe服务器上重新运行。 我们建议在浏览器中下载 PDF 之前不要离开项目。但是，在等待过程中，您仍可以继续对项目进行更改。如果PDF渲染时间超过5分钟，则会提示您通过电子邮件发送。
* PDF下载以单个页面呈现，不应用分页。
* 将项目渲染为PDF后，我们渲染页面上的内容。 如果项目具有自定义大小的可视化和面板，则需要将它们更改为自动调整大小（右上角的按钮），以便内容将不会被截断。

## 将数据复制到剪贴板(热键：Ctrl+C){#copy-data}

右键单击选项&#x200B;**[!UICONTROL 复制到剪贴板]**&#x200B;可让您快速从Workspace复制数据并将其粘贴到其他位置。

* 如果要复制显示的表，请右键单击表标题，然后选择&#x200B;**将数据复制到剪贴板**。
* 如果要复制数据子集，请在表中进行选择，然后右键单击> **将选择复制到剪贴板**。

此外，热键`Ctrl+C`将您的选择复制到剪贴板。 复制后，您可以进入另一个工具并粘贴信息（或点击`Ctrl+V`）。

![](assets/copy-selection.png)

## 将数据下载为 CSV {#download-data}

右键单击选项&#x200B;**[!UICONTROL 以CSV形式下载数据]**&#x200B;允许您以CSV形式下载数据表或任何可视化的数据源。

* 在任何表或可视化的标题中，右键单击&#x200B;**[!UICONTROL 以CSV]**&#x200B;形式下载数据。 这将下载表格或基础数据源中显示的数据，以便以CSV形式显示可视化。 注意：地图可视化不支持此选项。
* 如果在表中做出选择，则该选项将显示&#x200B;**[!UICONTROL 将选择内容下载为CSV]**。 与显示的完整表格相比，只有使用此选项下载选择内容。

![](assets/download-data-viz.png)

## 以 CSV 格式下载项目 {#download-items}

如果要分析表中超过可见的400行数据，请右键单击表标题或任何行，然后选择&#x200B;**以CSV(Dimension名)**&#x200B;形式下载项目。 此选项最多可导出所选维的50,000个维项目（基于表排序），并应用过滤器和段。 如果从表顶部选择此选项，则将导出表中的第一个维。 尽管自由形式表中不强制实施任何限制，但建议在少于20列的表中使用“下载项目”选项以确保最佳性能。

>[!TIP]
>
> 如果您的维度超过50,000个项目，请下载应用了不同排序度量的文件或应用筛选器。 例如，在一次下载中按访问降序排序，在第二次下载中按访问升序排序。 此提示可帮助您检索长尾项目。

您可以在项目中进行多任务，甚至在下载过程中在同一选项卡中导航到新的Workspace项目。 如果打开新的浏览器选项卡，下载将暂停。 如果您完全离开Workspace或关闭浏览器选项卡，下载将取消。

![](assets/download-items.png)

### 下载的项目文件

表的功能将应用于下载的文件，如下所示：

* 所有面板段都作为过滤器应用。
* 表中所选维的上方&#x200B;**的细分将作为每列上方的过滤器应用。**
* 将删除表中所选维的&#x200B;**下面的细分。**

在上面的示例中，页面项目随应用为过滤器的面板区段(新访客客户)和上面的组件(营销渠道=电子邮件)一起下载，下面的组件（移动设备类型）从下载的CSV中删除。

![](assets/downloaded-file.png)

### 下载通知

当文件下载时，您将看到包含进度的信息通知。 您可以随时单击&#x200B;**[!UICONTROL 取消下载]**&#x200B;取消下载。 关闭toast **不会**&#x200B;取消下载。

文件完成后，您将看到完成通知，文件将下载到您的浏览器。

如果一次请求多个下载，您将收到通知，通知每次额外下载都将排队等待，直到上次下载完成。

![](assets/toast.png)

## 常见问题解答 {#faq}

| 问题 | 回答 |
| --- | --- |
| 为什么下载的PDF只有一页？ | Workspace此时不会将下载的PDF分页。 |
| 我是否可以使用“以CSV形式下载项目”选项导出50,000多个项目？ | 虽然每次下载最多可包含50,000个维度项目，但您可以更改表的排序以检索较长的尾项目，或应用过滤器以下载更多特定项目。 |
| **[!UICONTROL 复制可视化]**&#x200B;有哪些功能？ | **[!UICONTROL 复]** 制可视化不是导出选项。它允许您将可视化或面板从Workspace中的一个位置复制到另一个位置。 例如，从一个面板到同一项目中的另一个面板，或者从一个项目到另一个项目。 [内链接视频](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html) |

