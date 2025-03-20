---
description: 了解如何创建计算量度。
title: 创建计算量度
feature: Calculated Metrics
exl-id: 55ed36c1-99ca-400a-bc2b-661994cbf720
source-git-commit: 261d4b5e18531f7971a894bc4cd571b764c625f1
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 2%

---

# 创建计算量度

默认情况下，只有管理员才能创建计算指标。 用户有权查看计算量度，这类似于用户查看其他组件的方式（例如过滤器、注释等）。

但是，管理员可以通过[Admin Console](/help/technotes/access-control.md#user-level-access)向用户授予&#x200B;**[!UICONTROL 编辑CJA Workspace访问权限]**&#x200B;中&#x200B;**[!UICONTROL 报告工具]**&#x200B;的&#x200B;**[!UICONTROL 计算度量创建]**&#x200B;权限。


您可以通过以下方式创建计算量度：

![创建筛选器的方式](assets/create-metric.png)

* **A**。 在主界面中，选择&#x200B;**[!UICONTROL 组件]**&#x200B;并选择&#x200B;**[!UICONTROL 计算量度]**。 从[[!UICONTROL 计算量度]管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)中选择![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**]。
* **B**。 在Workspace项目中，从“组件”左侧面板中选择![添加](/help/assets/icons/Add.svg) （位于![事件](/help/assets/icons/Event.svg) **量度**）。
* **C**。 在Workspace项目中，从指标列标题的上下文菜单中，选择&#x200B;**[!UICONTROL 从所选内容创建指标]**。 从子菜单中，您可以选择函数，或者选择&#x200B;**[!UICONTROL 在计算指标生成器中打开]**。 <br/>如果选择函数，则计算量度定义为仅用于项目的量度。 当您稍后通过[组件信息](/help/components/use-components-in-workspace.md#component-info)弹出窗口编辑此量度时，会在[计算量度生成器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)中看到通知。
* **D**。 在Workspace项目中，从菜单中选择&#x200B;**[!UICONTROL 组件]**，然后选择&#x200B;**[!UICONTROL 创建指标]**。
* **E**。 在Workspace项目中，使用快捷键&#x200B;**[!UICONTROL shift+cmd+c]** (macOS)或&#x200B;**[!UICONTROL shift+ctrl+c]** (Windows)。

要定义新的计算量度，请使用[计算量度生成器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md)。

<!--

Learn about the steps to take for creating calculated metrics.

| Workflow Task | Description |
| --- | --- |
| Plan Calculated Metrics | Especially for metrics that are going to be officially "approved", it makes sense to outline which calculated metrics will be widely used and how they will be defined. |
| [Build](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) Calculated Metrics | Build and edit calculated and advanced calculated metrics for use in [!DNL Customer Journey Analytics] components. |
| [Tag](cm-tagging.md) Calculated Metrics | Tag calculated metrics for ease of organization and sharing. See how to plan and assign tags for simple and advanced searches and organization. |
| [Approve](cm-approving.md) Calculated Metrics | Approve calculated metrics to make them canonical. |
| Apply Calculated Metrics | You can apply metrics directly from a report, from the Metric Selector (to access it, click [!UICONTROL Show Metrics]). |
| Filter Calculated Metrics | In the Metric Selector, click [!UICONTROL Advanced Selection] and filter by tags, owners, and other filters (Show All, Mine, Shared With me, Favorites, and Approved.) |
| Mark Calculated Metrics as [Favorites](cm-finding.md) | Marking metrics as favorites is another way to organize them for ease of use.|

-->
