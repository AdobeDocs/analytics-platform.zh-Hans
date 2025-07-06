---
description: 了解从Analysis Workspace项目下载数据的各种可能性。
title: 下载项目和数据
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: ce4a21b1a1e89f14316a92fbdce38281db61e666
workflow-type: tm+mt
source-wordcount: '1184'
ht-degree: 25%

---

# 下载项目和数据

您可以将Analysis Workspace项目和数据下载到本地设备。 此下载内容可以是复制的数据、CSV（逗号分隔值数据）文件或PDF（可移植文档格式）文档。

* 如果您希望在下载的文件中包含可视化图表，请选择PDF选项。
* 如果您只需要纯文本数据，请选择CSV和复制的数据选项。

导出Customer Journey Analytics数据的其他方法在[导出概述](/help/analysis-workspace/export/export-project-overview.md)中进行了说明。

## 下载为 CSV 或 PDF 格式 {#download-project}

![项目下拉菜单，其中突出显示了下载 CSV 和下载 PDF 选项。](assets/download-project.png)

在下载as a PDF项目时，请考虑以下事项：

* 下载可能需要几分钟时间，因为项目会在Adobe服务器上重新运行以呈现PDF格式。 在浏览器中下载项目之前，请勿离开项目。  呈现下载内容时，您可以继续对项目进行更改。 如果PDF的呈现时间超过5分钟，则系统会提示您改为向PDF[发送电子邮件](../curate-share/send-schedule-files.md)。
* 下载内容会以单个页面呈现，并且不会应用分页功能。
* PDF包含在Analysis Workspace的浏览器页面中显示的内容。 您需要自动调整自定义大小的可视化和面板的大小，以避免截断内容。 选择![调整大小](/help/assets/icons/Resize.svg)以自动调整自定义大小的可视化图表或面板的大小。
* 在下载的PDF中，作为超链接自由格式表中的[超链接](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。



要将项目下载为PDF文件，请执行以下操作：

1. 选择&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 下载PDF]**。
绿色条带有消息![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL 已请求您的下载。 请稍候。显示]**。

1. 下载就绪后，绿色条即准备就绪，该条消息为![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) **[!UICONTROL *项目名称&#x200B;*PDF。]**出现。
选择**[!UICONTROL 下载]**以下载PDF。 PDF的显示或下载方式具体取决于您用于处理PDF文档的浏览器配置。


要将项目下载为CSV文件，请执行以下操作：

* 选择&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 下载CSV]**。 项目将直接下载到下载文件夹，该文件夹配置为浏览器配置的一部分。 文件名由&#x200B;*项目名称* - *报表包名称* - *日期*&#x200B;组成，例如`Example Project - Omni-Channel - Luma - Jun 30, 2025.csv`。

## 复制到剪贴板 {#copy-data}

通过上下文菜单中的&#x200B;**[!UICONTROL 复制到剪贴板]**&#x200B;选项，您可以从Analysis Workspace中快速复制数据并将数据粘贴到第三方工具中。

* 如果要复制显示的表数据，请选择表标题，然后从上下文菜单中选择&#x200B;**将数据复制到剪贴板**。
* 如果要复制数据的子集，请在表中进行选择，然后从上下文菜单中选择&#x200B;**将所选内容复制到剪贴板**。

>[!TIP]
>
>您可以使用热键&#x200B;**_cmd + c_** (macOS)或&#x200B;**_ctrl + c_** (Windows)将您的选择复制到剪贴板。 然后使用&#x200B;**_cmd + v_** (macOS)或&#x200B;**_ctrl + v_** (Windows)粘贴数据。


![将选择内容复制到剪贴板的选项。](assets/copy-clipboard.png){zoomable="yes"}

## 下载为 CSV 格式 {#download-data}

通过上下文菜单中的下载为CSV选项，您可以将数据表或任何可视化图表的数据源下载为CSV。

操作方法：

* 从任何表或可视化图表的标题中，从上下文菜单中选择&#x200B;**[!UICONTROL 以CSV格式下载数据]**。 这样可将表中显示的数据或可视化的基础数据源下载为 CSV 格式。

<!-- Only relevant as soon as CJA supports Map visualization 
  >[!NOTE]
  >
  >  Note: the Map visualization does not support this option.
-->

* 在表中，从上下文菜单中选择&#x200B;**[!UICONTROL 以CSV格式下载选定内容]**。 通过此选项仅下载所选内容，而非整个显示的表。

![将数据下载为 CSV 选项。](assets/download-data-as-csv.png)

## 以 CSV 格式下载项目 {#download-items}

如果要分析表中的400多行可见数据，请从表标题或任何行的上下文菜单中选择&#x200B;**以CSV格式下载项目(_Dimension名称_)**。 此选项会导出所选维度的最多 50,000 个维度项（根据表格排序方式），并会应用排序选项和过滤器。如果从表的顶部选择此选项，将导出表中的第一个维。

![将项目下载为 CSV（页面）的选项。](assets/download-items-as-csv.png)

在自由格式表中不强制执行任何限制。 为确保获得最佳性能，建议在少于20列的表中使用此选项。

>[!TIP]
>
> 如果您的维度超过 50,000 项，请下载应用了不同排序量度的文件或者应用一个区段。例如，在一次下载中按访问量降序排序，然后在第二次下载中按访问量升序排序。此提示可以帮助您检索较长尾项。

您可以在项目中执行多项任务，甚至可以在下载过程中导航到同一选项卡中的新工作区项目。如果打开新的浏览器标签页，则下载暂停。如果完全离开 Workspace 或关闭浏览器标签页，则取消下载。


### 下载的项目文件 {#items-file}

自由格式表的以下功能适用于下载的文件：

* 以过滤器形式应用所有区段。
* 在每列上方以过滤器形式应用表格中所选维度&#x200B;**上面**&#x200B;的细分。
* 删除表格中所选维度&#x200B;**下面**&#x200B;的细分。

![下载的 .csv 文件在 Excel 中打开。](assets/download-items-file.png)

### 下载通知 {#notifications}

下载文件时，您会看到以下通知：

* 已请求蓝色&#x200B;**[!UICONTROL _表名&#x200B;_-_Dimension _.csv。_x _%完成]**表示进度。 要随时取消下载，请选择&#x200B;**[!UICONTROL 取消下载]**。 如果要关闭消息，请选择![CrossSize100](/help/assets/icons/CrossSize100.svg)，这样不会取消下载。
* 在文件下载完成后，已下载绿色的&#x200B;**[!UICONTROL _表名&#x200B;_-_Dimension _.csv]**完成通知。 该文件将下载到为您的浏览器配置的下载文件夹。

如果您一次请求多个下载，您将收到一条通知，说明每个额外的下载都将排队等待，直到前一个下载完成为止。


## 下载敏感数据 {#sensitive}

想象一下[数据治理策略](/help/data-views/data-governance.md)阻止数据下载。 并且在您报告的数据视图中打开此策略。 因此，项目的任何下载(例如通过电子邮件发送或共享PDF文件时)都会散列标记为敏感的数据字段。 您仍然可以在Analysis Workspace中对这些字段进行分析。 如果您尝试通过电子邮件发送或以其他方式共享项目，则PDF或CSV文件中的敏感数据字段将显示为空。

如果标记为敏感的数据字段包含在数据视图中，则从屏幕中选择和复制数据的选项将限制为数据视图中的所有数据。

## 常见问题解答 {#faq}

| 问题 | 回答 |
| --- | --- |
| 为什么我下载的PDF只包含一个页面？ | [下载PDF](#download-as-csv-or-pdf)功能不会对下载的PDF进行分页。 |
| 我可以使用&#x200B;**[!UICONTROL 以CSV格式下载项目]**&#x200B;选项导出50,000个以上的项目吗？ | 虽然每次下载最多可包含 50,000 个维度项，但您可以更改表格排序以检索较长尾项，或应用过滤器以下载更具体的项目。 |
| **[!UICONTROL 复制可视化图表]**&#x200B;有什么用？ | 与&#x200B;[!UICONTROL **将数据复制到剪贴板**]&#x200B;或&#x200B;[!UICONTROL **将所选内容复制到剪贴板**]&#x200B;不同，**[!UICONTROL 复制可视化图表]**&#x200B;上下文菜单选项不是导出选项。 此选项允许您[将可视化图表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)或[将面板](/help/analysis-workspace/c-panels/panels.md#context-menu)从Workspace中的一个位置复制到另一个位置。 例如，从同一项目中的一个面板复制到另一个面板，或从一个项目复制到另一个项目。 |
