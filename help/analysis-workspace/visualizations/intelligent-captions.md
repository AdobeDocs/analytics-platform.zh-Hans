---
description: 使用智能字幕生成自然语言洞察力以在可视化图表中快速呈现趋势。
title: 智能题注
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 9d94d52b14a4f119193696c1e5fc6df9538f77cb
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 5%

---

# 智能题注

智能题注使用先进的机器学习和生成式 AI 为工作区可视化提供有价值的自然语言见解。初始版本为[折线图](line.md)可视化图表提供了自动生成的见解。 随后将提供其他可视化图表。

智能字幕面向：

* 需要与其他用户共享叙述的分析师。 分析师需要这些见解才能为其用户提供上下文。
* 希望快速发现高级外卖的业务用户。

## 启动智能字幕 {#launch}

要为折线图可视化启动自动生成的字幕，请单击可视化右上角的&#x200B;**[!UICONTROL 智能字幕]**&#x200B;图标。

![显示产品查看趋势智能字幕的“启动分析”窗口。](assets/intell-caps-1.png)

自然语言洞察正在生成。

请记住以下事项

* 至少需要3个数据点才能成功生成字幕。 否则，您可能会收到诸如&#x200B;**[!UICONTROL 数据不足]**&#x200B;之类的错误。

* 每次在支持可视化的表格中更改基础选定数据时，都会生成字幕。

* 如果表中有多个量度，则仅为第一个量度或用户当前选择的量度生成字幕。

* 如果在特定点保存项目并在以后重新加载，则字幕将自动更新为新数据。 这同样适用于从项目导出的计划项目和PDF文件。

下面是智能字幕的外观示例：

![折线图可视化图表的智能字幕，包括季节性、最小值、最大值、尖峰和下降。](assets/captions.png)

## 操作

您可以对智能字幕执行以下操作：

### 复制到剪贴板 {#copy}

您可以将字幕复制到剪贴板并将它们粘贴到PowerPoint或其他工具中。 选择字幕对话框右上角的![将字幕复制到剪贴板](/help/assets/icons/Copy.svg)。

### 编辑显示区 {#edit}

您可以编辑字幕的显示，如隐藏或取消隐藏特定类别的洞察。

1. 在“智能字幕”对话框中选择![编辑智能字幕显示](/help/assets/icons/EditInLight.svg)。

1. 在![可见性](/help/assets/icons/Visibility.svg)之间切换可显示特定见解（如&#x200B;**[!UICONTROL 分钟]**），或在![可见性关闭](/help/assets/icons/VisibilityOff.svg)之间切换可隐藏特定见解（如&#x200B;**[!UICONTROL 尖峰]**）。

   ![编辑智能字幕](assets/edit-intelligent-captions.png)

1. 选择&#x200B;**[!UICONTROL 应用]**。


### 提供反馈

您可以对生成的智能字幕提供反馈。

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

* **合同访问权限**：如果您无法使用智能字幕，请联系贵组织的管理员或Adobe客户代表。 在组织中使用智能字幕之前，您必须同意某些与GenAI相关的法律条款。

* **权限**：在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 报告工具] **[!UICONTROL 智能字幕]**&#x200B;权限决定了访问权限。 [产品配置文件管理员](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)需要在[!UICONTROL Admin Console]中执行这些步骤：
   1. 导航到&#x200B;**[!UICONTROL Admin Console]** > **[!UICONTROL 产品和服务]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 产品配置文件]**。
   1. 选择要为其提供智能字幕访问权限的产品配置文件的标题。
   1. 在特定产品配置文件中，选择&#x200B;**[!UICONTROL 权限]**。
   1. 选择![编辑](/help/assets/icons/Edit.svg)以编辑&#x200B;**[!UICONTROL 报告工具]**。
   1. 选择![AddCircle](/help/assets/icons/AddCircle.svg)以将&#x200B;**智能字幕**&#x200B;添加到&#x200B;**[!UICONTROL 包含的权限项]**。

      ![添加权限](./assets/intelligent-captions-permissions.png)

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存权限。

有关详细信息，请参阅[访问控制](/help/technotes/access-control.md#access-control)。
