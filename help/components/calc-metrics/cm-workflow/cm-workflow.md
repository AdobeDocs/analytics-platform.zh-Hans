---
description: 了解如何创建计算量度。
title: 创建计算指标
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: c209341400bf4e0c00719075f0fc82f81ca9dbb4
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 18%

---

# 创建计算量度

默认情况下，只有管理员才能创建计算指标。 用户有权查看计算量度，这与用户查看其他组件（如区段、注释等）的方式类似。

但是，管理员可以通过&#x200B;**[!UICONTROL Admin Console]**&#x200B;向用户授予&#x200B;**[!UICONTROL 编辑CJA Workspace访问权限]**&#x200B;中&#x200B;**[!UICONTROL 报表工具]**&#x200B;的[计算度量创建](/help/technotes/access-control.md#user-level-access)权限。


您可以通过以下方式创建计算量度：

![创建量度的方式](assets/create-metric.png)

* **A**。在主界面中，选择&#x200B;**[!UICONTROL 组件]**&#x200B;并选择&#x200B;**[!UICONTROL 计算量度]**。 从![计算量度](/help/assets/icons/AddCircle.svg)管理器[!UICONTROL **[!UICONTROL 中选择]**]AddCircle[Add](/help/components/calc-metrics/cm-workflow/cm-manager.md)。
* **B**。在Workspace项目中，从“组件”左侧面板中选择![添加](/help/assets/icons/Add.svg) （位于![事件](/help/assets/icons/Event.svg) **量度**）。
* **C**。在Workspace项目中，从指标列标题的上下文菜单中，选择&#x200B;**[!UICONTROL 从所选内容创建指标]**。 从子菜单中，您可以选择函数，或者选择&#x200B;**[!UICONTROL 在计算指标生成器中打开]**。 <br/>如果选择函数，则计算量度定义为仅用于项目的量度。 当您稍后通过[组件信息](/help/components/use-components-in-workspace.md#component-info)弹出窗口编辑此量度时，会在[计算量度生成器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中看到通知。
* **D**。在Workspace项目中，从菜单中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 创建指标]**。
* **E**。 在Workspace项目中，使用快捷键&#x200B;**[!UICONTROL shift+cmd+c]** (macOS)或&#x200B;**[!UICONTROL shift+ctrl+c]** (Windows)。

要定义新的计算量度，请使用[计算量度生成器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)。


## 工作流

在创建计算量度之前，请仔细考虑以下工作流程：

| 工作流程任务 | 描述 |
| --- | --- |
| 计划计算指标 | 特别是对于即将正式批准的指标，规划可以概述哪些计算量度将会广泛使用以及它们的定义方式。 |
| [生成](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)计算量度 | 生成并编辑计算量度和高级计算量度，以在 [!DNL Customer Journey Analytics] 组件中使用。 |
| [标记](cm-tagging.md)计算量度 | 标记计算量度以便进行组织和共享。请参阅如何规划和分配标记以进行简单和高级搜索和组织。 |
| [批准](cm-approving.md)计算量度 | 批准计算量度以将其作为规范。 |
| 使用计算量度 | 在项目中使用计算量度。 |
| [共享](cm-sharing.md)计算量度 | 与其他个人、组或组织共享您的计算指标。 |
| [筛选器](cm-filter.md)计算量度 | 按标记、所有者和其他过滤器（“全部显示”、“我的”、“已与我共享”、“收藏”和“已批准”）过滤计算量度。 |
| 将计算量度标记为[收藏夹](cm-finding.md) | 将量度标记为收藏是另一种组织量度以便进行使用的方式。 |

