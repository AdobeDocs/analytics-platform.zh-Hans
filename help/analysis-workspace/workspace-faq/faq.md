---
description: 工作区常见问题解答和疑难解答提示。
title: 常见问题解答
feature: FAQ
exl-id: d7233b26-9887-4b71-ad46-3c6ffe27d904
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 96%

---

# 常见问题解答

| 问题 | 回答 |
|--- |--- |
| **使用 Analysis Workspace 的先决条件是什么？** | 在Customer Journey Analytics中使用Analysis Workspace需要有效的Customer Journey Analytics实施。 在使用这款工具之前，请确保您的组织正在向 Adobe Experience Platform 发送数据。 |
| **Analysis Workspace 的管理和访问要求有哪些？** | 请参阅[管理要求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| **使用 Analysis Workspace 是否会影响数据收集？** | 由于 Analysis Workspace 是一款报告工具，因此不会对数据收集产生任何影响。您可以不加选择地将组件拖到项目中来查看具体效果，这不会产生任何影响。将不同的维度和指标组合拖动到工作区项目中，可查看相应的效果。如果意外地将无效组件拖动到工作区项目，或者希望返回到上一个步骤，请按 Ctrl + Z (Windows) 或 cmd + Z (Mac) 以撤消上一个操作。此外，您还可以通过单击左上角菜单中的&#x200B;*[!UICONTROL 项目] > [!UICONTROL 新建]*&#x200B;来重头开始创建。 |
| **如何实施 Analysis Workspace？** | 不要求执行任何特殊的实施操作。Analysis Workspace 适用于所有公司 Customer Journey Analytics。但是，内容（如项目组件）的标准权限在此适用，并可用于组织和共享项目。请参阅[管理和访问要求](/help/analysis-workspace/workspace-faq/frequently-asked-questions-analysis-workspace.md)。 |
| **如何优化 Analysis Workspace 的性能？** | 请参阅[优化性能](/help/admin/optimizing-performance.md)。 |

## 疑难解答

**当我将指标拖动到上面时，显示“数据无效”。**

无效数据意味着 Adobe 无法通过报表中使用的维度和指标组合返回数据。例如，两个彼此堆叠的指标不能作为数据返回，因为无法以这种堆叠方式显示这两个指标。相反，应将两个指标并排放置。

**当我将指标拖动到上面时，看不到任何实际数据 - 只有零。**

如果您成功创建了工作区报表，但报表中没有数据，则可以检查以下几项内容：

* 如果在报表中应用了过滤器，过滤器标准可能与所有数据不匹配。请尝试移除过滤器或调整过滤器定义。
* 检查右上角的日期范围，并确保它已设置为预期的值。
* 导航到您的网站，然后使用 [Debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html) 验证正在收集的数据。
