---
description: 您可以通过复制数据或以 PDF 和 CSV 格式从 Analysis Workspace 下载数据。
title: 下载 Customer Journey Analytics 数据
feature: Curate and Share
exl-id: 1d8384ca-888c-482c-ab3e-d1b579217560
role: User
source-git-commit: 0101986bb86c49776a044f754d912dc1bcb9422c
workflow-type: tm+mt
source-wordcount: '1194'
ht-degree: 98%

---

# 下载 Customer Journey Analytics 数据

您可以将 Customer Journey Analytics 数据下载到您的个人工作站。这可以采用复制的数据、CSV 或 PDF 形式。如果要在下载的文件中包括可视化视图，则一般首选 PDF。如果只想要文本数据，则首选 CSV 和复制的数据。

如[导出概述](/help/analysis-workspace/export/export-project-overview.md)中所述，还有其他导出 Customer Journey Analytics 数据的方法。

##  下载为 CSV 或 PDF 格式 {#download-project}

下载项目时请考虑以下事项：

* 当将项目下载为 CSV 或 PDF 时，则当您请求下载项目时可以保存或取消保存该项目。但是，只有已保存的项目才能被[计划](/help/analysis-workspace/export/t-schedule-report.md)。

* 将项目下载为 PDF 时：
   * 下载内容可能需要几分钟时间才能导出，因为该项目在以 PDF 格式呈现之前会在 Adobe 服务器上重新运行。我们建议在浏览器中下载 PDF 之前不要离开项目。但是，在等待过程中，您仍可以继续对项目进行更改。如果 PDF 的呈现时间超过 5 分钟，则系统将提示您改为通过电子邮件发送。
   * 下载内容会以单个页面呈现，并且不会应用分页功能。
   * PDF 渲染包含工作区中页面的内容。如果项目具有自定义大小的可视化图表和面板，则需要将它们更改为自动调整大小（右上角的按钮），以便内容不会被截断。
   * 自由格式表格中存在的任何[超链接](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)在下载的 PDF 中不起作用。

要将项目下载为 CSV 或 PDF 文件：

1. 根据您希望下载文件的格式，请执行以下任一操作：

   * **PDF：**&#x200B;选择&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 下载 PDF]**。

     如果想让下载的文件包含项目中所有显示（可见）的表和可视化，请选择此选项。

   * **CSV：**&#x200B;选择&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 下载 CSV]**。

     如果您希望下载的文件是纯文本，请选择此选项。

   ![项目下拉菜单，其中突出显示了下载 CSV 和下载 PDF 选项。](assets/download-project.png)

1. （视情况而定）如果您选择下载 PDF，则在准备好下载项目后会显示一条消息。选择&#x200B;[!UICONTROL **下载**]。

## 复制到剪贴板（热键：Ctrl+C） {#copy-data}

通过右键单击选项&#x200B;**[!UICONTROL 复制到剪贴板]**，可从工作区快速地复制 Customer Journey Analytics 数据并将其粘贴到第三方工具中。

* 如果要复制所显示的表，请右键单击表标题并选择&#x200B;**将数据复制到剪贴板**。
* 如果要复制数据的子集，请在表中作出选择，然后单击右键并选择&#x200B;**将所选内容复制到剪贴板**。

>[!TIP]
>
>可使用热键 `Ctrl+C` 将您选择的内容复制到剪贴板，然后使用 `Ctrl+V` 将它粘贴到第三方工具中。


![将选择内容复制到剪贴板的选项。](assets/copy-selection.png)

## 下载为 CSV 格式 {#download-data}

通过右键单击选项&#x200B;**[!UICONTROL 以 CSV 格式下载数据]**，可以 CSV 格式下载 Customer Journey Analytics 数据表或任何可视化图表的数据源。

* 从任何表格或可视化图表的标题中，单击右键并选择&#x200B;**[!UICONTROL 以 CSV 格式下载数据]**。这样可将表中显示的 Customer Journey Analytics 数据或可视化图表的基础数据源下载为 CSV 格式。

  >[!NOTE]
  >
  >  注意：“地图”可视化不支持此选项。


* 在表中单击右键并选择&#x200B;**[!UICONTROL 将所选内容下载为 CSV]**。通过此选项仅下载所选内容，而非整个显示的表。

![将数据下载为 CSV 选项。](assets/download-data-viz.png)

## 以 CSV 格式下载项目 {#download-items}

如果要分析的数据不止在表中可见的 400 行数据，请右键单击该表标题或任意行，然后选择&#x200B;**以 CSV 格式下载项（_维度名称_）**。此选项会导出所选维度的最多 50,000 个维度项（根据表格排序方式），并会应用排序选项和过滤器。如果从表格顶部选择此选项，将导出表格中的第一个维度。虽然在自由格式表中没有强制执行任何限制，但建议在少于 20 列的表中使用“下载项目”选项以确保达到最佳性能。

>[!TIP]
>
> 如果您的维度超过50,000个项目，请下载应用了不同排序量度的文件或应用区段。 例如，在一次下载中按访问量降序排序，然后在第二次下载中按访问量升序排序。此提示可以帮助您检索较长尾项。

您可以在项目中执行多项任务，甚至可以在下载过程中导航到同一选项卡中的新工作区项目。如果打开新的浏览器标签页，则下载暂停。如果完全离开工作区或关闭浏览器标签页，则取消下载。

![将项目下载为 CSV（页面）的选项。](assets/download-items.png)

### 下载的项目文件 {#items-file}

表格功能将按如下方式应用于下载的文件：

* 以过滤器形式应用所有区段。
* 在每列上方以过滤器形式应用表格中所选维度&#x200B;**上面**&#x200B;的细分。
* 删除表格中所选维度&#x200B;**下面**&#x200B;的细分。

在上面的示例中，以过滤器形式应用了面板过滤器（新访客客户）及其上面的组件（营销渠道 = 电子邮件），从而下载了页面项目，并从下载的 CSV 中删除了下面的组件（移动设备类型）。

![下载的 .csv 文件在 Excel 中打开。](assets/downloaded-file.png)

### 下载通知 {#notifications}

下载文件时，您将看到带有进度的信息通知。您可以随时单击&#x200B;**[!UICONTROL 取消下载]**&#x200B;来取消下载。关闭 toast **将不**&#x200B;会取消下载。

文件完成后，您将看到完成通知，文件将下载到您的浏览器。

如果您同时请求多个下载，您将收到一条通知，说明每个额外的下载都将排队等待，直到前面的下载完成为止。

![下载状态通知，其中显示完成百分比和取消下载链接。](assets/toast.png)

## 下载敏感数据 {#sensitive}

如果在您所报告的数据视图中启用了&#x200B;**[!UICONTROL 强制下载]**[数据治理策略](/help/data-views/data-governance.md)，则任何下载（如通过电子邮件发送或共享 PDF 文件）的工作区项目都会对标记为敏感的数据字段进行哈希处理。您仍然可以在工作区中对这些字段进行分析，但如果您尝试发送电子邮件或以其他方式共享项目，被阻止的字段将在 .pdf 或 .csv 文件中显示为空。

如果[!UICONTROL 数据视图]中包含任何标记为敏感的数据字段，则从屏幕上选择和复制数据的选项对于[!UICONTROL 数据视图]中的所有数据都会受到限制。

## 常见问题解答 {#faq}

| 问题 | 回答 |
| --- | --- |
| 为什么我下载的 PDF 是一页？ | 工作区目前不会对下载的 PDF 进行分页。 |
| 能否使用“以 CSV 格式下载项”选项导出超过 50,000 项？ | 虽然每次下载最多可包含 50,000 个维度项，但您可以更改表格排序以检索较长尾项，或应用过滤器以下载更具体的项目。 |
| **[!UICONTROL 复制可视化图表]**&#x200B;有什么用？ | 与&#x200B;[!UICONTROL **将数据复制到剪贴板**]&#x200B;或&#x200B;[!UICONTROL **将所选内容复制到剪贴板**]&#x200B;不同，**[!UICONTROL 复制可视化]**&#x200B;右键单击选项不是导出选项。它允许您将可视化图表或面板从工作区中的一个位置复制到另一个位置。例如，从同一项目中的一个面板复制到另一个面板，或从一个项目复制到另一个项目。[内联视频](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/visualizations/intra-linking-in-analysis-workspace.html?lang=zh-Hans) |
