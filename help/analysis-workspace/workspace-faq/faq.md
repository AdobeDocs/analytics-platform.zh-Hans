---
description: 工作区常见问题解答
title: 常见问题和工作区疑难解答
translation-type: tm+mt
source-git-commit: 1fb46acc9c7c70e64058d2c6a8fdcde119910fec
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 56%

---


# 常见问题解答

>[!NOTE]
>
>您正在查看Customer Journey Analytics中的Analysis Workspace文档。 其功能集与传统Adobe [Analytics的Analysis Workspace略有不同](https://docs.adobe.com/content/help/zh-Hans/analytics/analyze/analysis-workspace/home.html)。 [了解更多...](/help/getting-started/cja-aa.md)

| 问题 | 回答 |
|--- |--- |
| 使用Analysis Workspace的先决条件是什么？ | 使用Analysis Workspace需要一个工作Customer Journey Analytics实现。 在使用该工具之前，请确保您的组织向Adobe Experience Platform发送数据。 |
| Analysis Workspace 的管理和访问要求有哪些？ | 请参阅[管理要求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| 使用Analysis Workspace是否会影响数据收集？ | 由于 Analysis Workspace 是一款报表工具，因此不会对数据收集产生任何影响。您可以不加选择地将组件拖到项目中来查看具体效果，这不会产生任何影响。将不同的维度和量度组合拖动到工作区项目中，可查看相应的效果。如果意外地将无效组件拖动到工作区项目，或者希望返回到上一个步骤，请按 Ctrl + Z (Windows) 或 cmd + Z (Mac) 以撤消上一个操作。此外，您还可以通过单击左上角菜单中的&#x200B;*[!UICONTROL 项目]>[!UICONTROL 新建]*&#x200B;来重头开始创建。 |
| 如何实施 Analysis Workspace？ | 不要求执行任何特殊的实施操作。Analysis Workspace适用于所有公司Customer Journey Analytics。 但是，对内容（如项目组件）的标准权限会应用，并且会用于创建和共享项目。 请参阅[管理和访问要求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| 如何优化 Analysis Workspace 的性能？ | 请参阅[优化性能](/help/analysis-workspace/workspace-faq/optimizing-performance.md)。 |

## 故障诊断

**当我将量度拖动到上面时，显示“数据无效”。**

无效数据意味着 Adobe 无法通过报表中使用的维度和量度组合返回数据。例如，两个彼此堆叠的量度不能作为数据返回，因为无法以这种堆叠方式显示这两个量度。相反，应将指标并排放置。

**当我将量度拖动到上面时，看不到任何实际数据 - 只有零。**

如果您成功创建了工作区报告但没有数据，您可以检查以下几项：

* 多次检查报表包，并确保它已填充数据。
* 如果您在报表中应用了区段，则区段标准可能与任何数据不匹配。 请尝试移除区段或调整区段定义。
* 检查右上角的日期范围，并确保它已设置为您期望的值。
* Navigate to your website and use the [Debugger](https://docs.adobe.com/content/help/zh-Hans/debugger/using/experience-cloud-debugger.html) to validate that data is being collected.