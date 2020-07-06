---
description: 您可以下载 PDF 和 CSV 格式的已保存和未保存项目。
title: 下载 PDF 或 CSV 文件
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 68%

---


# 下载 PDF 或 CSV 文件

>[!NOTE]
>
>您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

您可以下载 PDF 和 CSV 格式的已保存和未保存项目。

PDF 或 CSV 文件的名称与项目的当前名称匹配。对于未保存的项目，已下载的文件包含项目中未保存的更改。请注意，无法计划 PDF 或 CSV 格式的未保存项目。

请牢记这一点：

*  我们还支持 CSV 格式的“流失”可视化图表。
*  在将项目渲染为 PDF 时，我们仅渲染页面上的内容。如果项目具有自定义大小的可视化和面板，则需要将它们更改为自动调整大小（右上角的按钮），以便内容将不会被截断。
* 在浏览器中下载的PDF可能需要几分钟才能导出。 这是因为，在以PDF格式呈现整个项目之前，我们必须在我们的服务器上重新运行它。 我们建议在浏览器中下载PDF之前不要离开项目。 但是，您可以在等待时继续对项目进行更改。
* 我们知道，如果您有很长的Workspace项目，PDF当前将作为一个大页面而不是分页文档导出。 我们正在改进Workspace PDF导出，以便进行分页。

1. 创建或打开一个项目。
1. 单击&#x200B;**[!UICONTROL 项目]** > **[!UICONTROL 下载 CSV（或下载 PDF）]**。

从 2019 年 4 月 11 日开始，已对 Analysis Workspace 中的&#x200B;**[!CSV 下载]**&#x200B;功能（和&#x200B;**[!C复制到剪贴板]**）进行了一些更改，目的在于从导出的数据中删除格式。
* 千位分隔符将不再包含在内。（小数分隔符将继续包含在内，并将遵循&#x200B;**[!UICONTROL 组件 > 报表格式 > 千位分隔符]**&#x200B;下定义的格式。）
* 未显示货币符号。
* 未显示百分比符号。
* 百分比以小数形式表示，例如，75% 表示为 0.75。
* 时间以秒为单位显示。
* 同类群组表仅显示原始值，百分比将被移除。
* 如果数字无效，将显示空白单元格。

>[!N注意：]
>
> 使用逗号作为小数分隔符的数值将会继续在导出的 CSV 中引用。
