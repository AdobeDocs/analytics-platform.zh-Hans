---
description: 使用智能字幕生成自然语言洞察力以快速在可视化图表中显示趋势。
title: 智能题注
feature: Visualizations
exl-id: d32d3cda-ecbf-4ee7-a8b7-7c3c71b5df75
role: User
source-git-commit: 542cbb35d3870b8eef6fe252d1ac20962a1b2b8f
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 6%

---

# 智能题注

智能题注使用先进的机器学习和生成式 AI 为工作区可视化提供有价值的自然语言见解。初始版本为[折线图](line.md)可视化图表提供了自动生成的见解。 （随后将提供其他可视化图表。）

智能字幕面向：

* 需要与其他用户共享叙述的分析师。 分析师需要这些见解才能为其用户提供上下文。
* 希望快速发现高级外卖的业务用户。

字幕可供所有Customer Journey Analytics用户使用，并且不需要特殊权限。

## 启动智能字幕 {#launch}

要为折线图可视化启动自动生成的字幕，请单击可视化右上角的&#x200B;**[!UICONTROL 智能字幕]**&#x200B;图标。

![显示产品查看趋势智能字幕的“启动分析”窗口。](assets/intell-caps-1.png)

自然语言洞察正在生成。

请记住以下事项

* 要成功生成字幕，至少需要3个数据点。 否则，您可能会收到显示“数据不足，无法分析”的错误。

* 每次在支持可视化的表格中更改基础选定数据时，都会生成字幕。

* 如果表中有多个量度，则仅为第一个量度或用户当前选择的量度生成字幕。

* 如果此时保存项目并稍后重新加载，则字幕将自动更新为新数据。 这同样适用于从此项目导出的计划项目和PDF文件。

## 查看和解读字幕 {#view}

以下是字幕的示例：

![折线图可视化图表的智能字幕，包括季节性、最小值、最大值、尖峰和下降。](assets/captions.png)

## 复制到剪贴板 {#copy}

您可以将字幕复制到剪贴板并将它们粘贴到Powerpoint或其他工具中。 在字幕对话框的右上角找到&#x200B;**[!UICONTROL 将字幕复制到剪贴板]**&#x200B;图标。

## 编辑字幕 {#edit}

您可以编辑字幕，如隐藏或取消隐藏特定类别的洞察。 例如，如果您不想了解有关最小订单的分析，则只需隐藏该信息，然后单击应用，它就不会再次显示。

1. 单击剪贴板图标旁边的&#x200B;**[!UICONTROL 编辑智能字幕显示]**&#x200B;图标。

1. 在“编辑”对话框中，单击要隐藏的洞察旁边的眼睛图标。

1. 单击&#x200B;**[!UICONTROL 应用]**。

使用相同的流程取消隐藏字幕。

## 导出字幕 {#export}

您可以&#x200B;**通过PDF**&#x200B;导出字幕，但前提是项目是在生成的字幕下保存的。

## 关闭字幕 {#toggle}

如果不希望生成智能字幕，可以转到可视化首选项并取消选中&#x200B;**[!UICONTROL 显示智能字幕]**&#x200B;来关闭此功能。

![显示取消选中显示智能字幕选项的折线图可视化选项。](assets/toggle-captions.png)

## 移动记分卡中的智能字幕

智能字幕还在Customer Journey Analytics[移动记分卡](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dashboards/manage-scorecard#captions)中可用。