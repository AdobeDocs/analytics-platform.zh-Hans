---
description: 了解如何使用智能字幕生成自然语言洞察，以揭示可视化中的趋势。
title: 智能题注
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: c4c8c0ff5d46ec455ca5333f79d6d8529f4cb87d
workflow-type: tm+mt
source-wordcount: '757'
ht-degree: 100%

---

# 智能标题 {#intelligent-captions}

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions"
>title="智能标题"
>abstract="以自然语言形式生成洞察，帮助您更轻松地理解和解释可视化图表的数据。"


智能标题功能使用先进的生成式 AI，为自然语言中最常用的工作区可视化内容提供关键洞察。

智能标题适用于：

* 需要与其他用户分享叙述内容的分析师。分析师需要这些洞察才能向用户提供背景信息。
* 希望快速发现高级要点的商业用户。

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [智能标题](https://video.tv.adobe.com/v/3443148/?quality=12&learn=on&captions=chi_hans){target="_blank"}以观看演示视频。

>[!ENDSHADEBOX]


## 启动智能标题 {#launch}

要为可视化内容启动自动生成的智能标题，请选择可视化内容右上角的![智能标题](/help/assets/icons/AI.svg)。进行该选择会产生自然语言洞察。

![启动 Analysis 窗口，其中显示产品浏览量趋势的智能标题。](assets/intelligent-captions.gif)


请记住以下事项：

* 您至少需要 3 个数据点才能成功生成标题。否则，您可能会收到类似于&#x200B;**[!UICONTROL 数据不足，无法分析]**&#x200B;的错误。

* 每当表格中用于生成可视化内容的选定基础数据发生变化时，就会生成相应的标题。

* 如果所关联的自由格式表中有多个量度，则仅会为第一个量度或用户当前选择的量度生成标题。但是，可以为折线和面积可视化图表的多个量度生成标题。

* 如果您在特定的时间点上保存项目，并在稍后重新加载，则标题会自动使用新数据进行更新。这同样适用于计划的项目，以及从项目中导出的 PDF 文件。


## 可视化内容 {#visualizations}

以下可视化内容支持使用智能标题功能：

* [线形图](line.md)（包括多行）
* [条形图](bar.md)
* [水平条形图](horizontal-bar.md)
* [面积图](area.md)（包含多条面积线）
* [环形图](donut.md)
* [流失](fallout/fallout-flow.md)
* [流量](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## 操作

您可以对智能标题执行以下操作：

### 复制到剪贴板 {#copy}

您可以将标题复制到剪贴板，然后将其粘贴到 PowerPoint 或其他工具中。您可以在逐个视图中复制单个标题，也可以在扩展标题视图中一次复制所有标题。

* 要复制标题，请选择标题对话框右上角的![将标题复制到剪贴板](/help/assets/icons/Copy.svg)。

### 显示全部或个别智能标题  {#show-all-or-individual}

您可以在扩展视图中一次显示所有智能标题，也可以在逐个视图中显示单个智能标题。

* 要显示所有智能标题，请选择![显示所有智能标题](/help/assets/icons/Maximize.svg)。
* 要逐个显示单个智能标题，请选择![显示单个智能标题](/help/assets/icons/Minimize.svg)。

### 编辑显示内容 {#edit}

您可以编辑标题的显示内容，例如隐藏或取消隐藏特定类别的洞察。

1. 在智能标题对话框中选择![编辑智能标题的可见性](/help/assets/icons/EditInLight.svg)。

1. 在![切换可见性](/help/assets/icons/Visibility.svg)以显示特定洞察（如 **[!UICONTROL Min]**）或![切换可见性](/help/assets/icons/VisibilityOff.svg)以隐藏特定洞察（如 **[!UICONTROL Spike]**）之间进行选择。

   ![编辑智能标题](assets/edit-intelligent-captions.png)

1. 选择&#x200B;**[!UICONTROL 应用]**。


### 提供反馈

您可以对生成的智能标题提供反馈（仅可在扩展的标题视图中提供反馈）。

1. 在智能标题对话框中选择![更多操作](/help/assets/icons/More.svg)。

1. 选择 ![好评](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL 好评]**、![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL 差评]**&#x200B;或 ![举报](/help/assets/icons/Flag.svg) **[!UICONTROL 报告]**。

1. 在&#x200B;**[!UICONTROL 感谢您的反馈]**&#x200B;对话框中，提供您的反馈并选择&#x200B;**[!UICONTROL 提交]**&#x200B;来提交反馈。

### 导出 {#export}

只要项目保存时已生成智能标题，您就可以将智能标题作为 PDF 的一部分导出。

### 关闭 {#toggle}

如果您不想显示智能标题，则可以关闭该功能。

1. 前往[可视化图表偏好设置](/help/analysis-workspace/user-preferences.md#visualizations-preferences)。
1. 取消勾选&#x200B;**[!UICONTROL 显示智能标题]**。

   ![线条可视化图表选项，其中显示取消选中“显示智能字幕”的选项。](assets/toggle-captions.png)

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;来保存偏好设置。


## 移动记分卡中的智能标题

Customer Journey Analytics [移动记分卡](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)中也提供智能标题功能。

## 功能访问权限

以下参数控制对智能标题的访问权限：

* **解决方案访问权限**：Customer Journey Analytics 中提供智能标题功能，但 Adobe Analytics 中不提供该功能。

* **合同访问权限**：如果您无法使用智能标题，请联系您所在组织的管理员或 Adobe 客户代表（管理员）。在您的组织中使用智能标题之前，您必须同意某些与生成式 AI 相关的法律条款。

* **权限**：在 [!UICONTROL Adobe Admin Console] 中，[!UICONTROL 报告工具] **[!UICONTROL 智能标题]**&#x200B;权限决定访问权限。[产品轮廓管理员](https://helpx.adobe.com/cn/enterprise/using/manage-product-profiles.html)需要在 [!UICONTROL Admin Console] 中执行以下步骤：
   1. 导航至 **[!UICONTROL Admin Console]** > **[!UICONTROL 产品和服务]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 产品轮廓]**。
   1. 选择您想要提供智能标题访问权限的产品轮廓的标题。
   1. 在具体的产品轮廓中，选择&#x200B;**[!UICONTROL 权限]**。
   1. 选择![编辑](/help/assets/icons/Edit.svg)来编辑&#x200B;**[!UICONTROL 报告工具]**。
   1. 选择 ![AddCircle](/help/assets/icons/AddCircle.svg) 以将&#x200B;**智能标题**&#x200B;添加到&#x200B;**[!UICONTROL 包含的权限项目]**。

      ![添加权限](./assets/intelligent-captions-permissions.png)

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;来保存权限。

请参阅 [访问权限控制](/help/technotes/access-control.md#access-control)，以了解更多信息。
