---
description: 使用智能字幕生成自然语言洞察力以显示可视化图表中的趋势。
title: 智能题注
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 5d391a73fb30ebc8f443f5a88357c866df03ce96
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 19%

---

# 智能题注 {#intelligent-captions}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_area"
>title="智能题注：面积"
>abstract="以自然语言形式生成洞察，帮助您更轻松地理解和解释可视化数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_bar"
>title="智能题注：条形图"
>abstract="以自然语言形式生成洞察，帮助您更轻松地理解和解释可视化数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_donut"
>title="智能题注：圆环图"
>abstract="以自然语言形式生成洞察，帮助您更轻松地理解和解释可视化数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_horizontalbar"
>title="智能题注：水平条形图"
>abstract="以自然语言形式生成洞察，帮助您更轻松地理解和解释可视化数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_line"
>title="智能题注：折线图"
>abstract="以自然语言形式生成洞察，帮助您更轻松地理解和解释可视化数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_fallout"
>title="智能题注：流失"
>abstract="以自然语言形式生成洞察，帮助您更轻松地理解和解释可视化数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_intelligentcaptions_flow"
>title="智能题注：流量"
>abstract="以自然语言形式生成洞察，帮助您更轻松地理解和解释可视化数据。"

<!-- markdownlint-enable MD034 -->

智能字幕功能使用高级创作AI为自然语言中最常用的Workspace可视化图表提供关键见解。

智能字幕面向：

* 分析师，他们需要与其他用户分享叙述。 分析师需要这些见解才能为其用户提供上下文。
* 希望快速发现高级外卖的企业用户。

>[!BEGINSHADEBOX]

观看演示视频的![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [智能字幕](https://video.tv.adobe.com/v/3420131/?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]

## 启动智能字幕 {#launch}

要为可视化启动自动生成的智能字幕，请选择可视化右上角的![智能字幕](/help/assets/icons/AI.svg)。 此选择将生成自然语言见解。

![显示产品查看趋势智能字幕的“启动分析”窗口。](assets/intelligent-captions.gif)


请记住以下事项：

* 至少需要3个数据点才能成功生成字幕。 否则，您可能会收到诸如&#x200B;**[!UICONTROL 数据不足]**&#x200B;之类的错误。

* 每次在支持可视化的表格中更改基础选定数据时，都会生成字幕。

* 如果关联的自由格式表中有多个量度，则仅为第一个量度或用户当前选择的量度生成字幕。 但是，可以为线形图和区域图可视化的多个量度生成标题。

* 如果在特定点保存项目并在以后重新加载，则字幕将自动更新为新数据。 这同样适用于从项目导出的计划项目和PDF文件。


## 可视化内容 {#visualizations}

以下可视化图表支持智能字幕：

* [行](line.md)（包括多行）
* [条形图](bar.md)
* [水平条形图](horizontal-bar.md)
* [区域](area.md)（包括多条区域线）
* [圆环图](donut.md)
* [流失](fallout/fallout-flow.md)
* [流量](c-flow/flow.md)

<!--
Here is an example of what intelligent captions could look like:

![Intelligent captions for Line visualization including Seasonality, Min, Max, Spike, and Decline.](assets/captions.png)
-->

## 操作

您可以对智能字幕执行以下操作：

### 复制到剪贴板 {#copy}

您可以将字幕复制到剪贴板并将它们粘贴到PowerPoint或其他工具中。 可以在逐个视图中复制单个字幕，也可以在扩展字幕视图中一次复制所有字幕。

* 要复制字幕，请选择字幕对话框右上角的![将字幕复制到剪贴板](/help/assets/icons/Copy.svg)。

### 显示全部或单个智能字幕  {#show-all-or-individual}

您可以在扩展视图中一次显示所有智能字幕，也可以在一个视图下逐一显示单个智能字幕。

* 要显示所有智能字幕，请选择![显示所有智能字幕](/help/assets/icons/Maximize.svg)。
* 要逐一显示单个智能字幕，请选择![显示单个智能字幕](/help/assets/icons/Minimize.svg)。

### 编辑显示区 {#edit}

您可以编辑字幕的显示，如隐藏或取消隐藏特定类别的洞察。

1. 在“智能字幕”对话框中选择![编辑智能字幕的可见性](/help/assets/icons/EditInLight.svg)。

1. 在![切换可见性](/help/assets/icons/Visibility.svg)之间切换可显示特定见解（如&#x200B;**[!UICONTROL 分钟]**），或在![切换可见性](/help/assets/icons/VisibilityOff.svg)之间切换可隐藏特定见解（如&#x200B;**[!UICONTROL 尖峰]**）。

   ![编辑智能字幕](assets/edit-intelligent-captions.png)

1. 选择&#x200B;**[!UICONTROL 应用]**。


### 提供反馈

您可以针对生成的智能字幕提供反馈（反馈只能在扩展的字幕视图中提供）。

1. 在“智能字幕”对话框中选择![更多操作](/help/assets/icons/More.svg)。

1. 选择![良好的响应](/help/assets/icons/ThumbUpOutline.svg) **[!UICONTROL 良好的响应]**、![ThumbDownOutline](/help/assets/icons/ThumbDownOutline.svg) **[!UICONTROL 错误的响应]**&#x200B;或![标志](/help/assets/icons/Flag.svg) **[!UICONTROL 报告]**。

1. 在&#x200B;**[!UICONTROL 感谢您提供反馈]**&#x200B;对话框中，提供您的反馈并选择&#x200B;**[!UICONTROL 提交]**&#x200B;以提交反馈。

### 导出 {#export}

您可以将智能字幕导出为PDF的一部分，只要保存项目并生成智能字幕即可。

### 关闭 {#toggle}

如果不希望显示智能字幕，可以关闭该功能。

1. 转到[可视化首选项](/help/analysis-workspace/user-preferences.md#visualizations-preferences)。
1. 取消选中&#x200B;**[!UICONTROL 显示智能字幕]**。

   ![显示取消选中显示智能字幕选项的折线图可视化选项。](assets/toggle-captions.png)

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存首选项。


## 移动记分卡中的智能字幕

智能字幕还在Customer Journey Analytics[移动记分卡](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)中可用。

## 功能访问

以下参数控制对智能字幕的访问：

* **解决方案访问**：智能字幕功能在Customer Journey Analytics中可用，但在Adobe Analytics中不可用。

* **合同访问权限**：如果您无法使用智能字幕，请联系您组织的管理员或Adobe帐户代表（管理员）。 在组织中使用智能字幕之前，您必须同意某些与创作AI相关的法律条款。

* **权限**：在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 报告工具] **[!UICONTROL 智能字幕]**&#x200B;权限决定了访问权限。 [产品配置文件管理员](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)需要在[!UICONTROL Admin Console]中执行这些步骤：
   1. 导航到&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL 产品和服务]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 产品配置文件]**。
   1. 选择要为其提供智能字幕访问权限的产品配置文件的标题。
   1. 在特定产品配置文件中，选择&#x200B;**[!UICONTROL 权限]**。
   1. 选择![编辑](/help/assets/icons/Edit.svg)以编辑&#x200B;**[!UICONTROL 报告工具]**。
   1. 选择![AddCircle](/help/assets/icons/AddCircle.svg)以将&#x200B;**智能字幕**&#x200B;添加到&#x200B;**[!UICONTROL 包含的权限项]**。

      ![添加权限](./assets/intelligent-captions-permissions.png)

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存权限。

有关详细信息，请参阅[访问控制](/help/technotes/access-control.md#access-control)。
