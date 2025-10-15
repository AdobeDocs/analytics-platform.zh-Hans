---
description: 了解如何从Workspace报表以pptx格式生成演示文稿。
keywords: Analysis Workspace
title: 从Workspace报表生成演示
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 680799fdf18703acbd0569e25b41e6ecbc154d62
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 3%

---

# 数据storytelling：从Workspace报表生成幻灯片演示 {#generate-powerpoint}

您可以从Analysis Workspace项目自动生成.pptx演示文稿。 在生成演示文稿时，Customer Journey Analytics会自动识别关键见解，并将其转换为适用于利益相关者的幻灯片。

此功能可减少从您的Workspace项目揭示发现结果所需的时间和精力，并且允许您快速构建管理层叙述并传达业务影响。

## 基于Workspace项目生成.pptx演示文稿

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-powerpoint-include-visualizations"
>title="包含的面板和可视化图表"
>abstract="选择要包含在演示文稿中的面板和可视化图表。 您最多可以包含50个可视化图表。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-presentation-emphasized-components"
>title="强调的组件"
>abstract="从可视化图表中最多选择5个要在演示文稿中强调的量度和5个维度。 您选择的量度以斜体显示，维度以粗体显示，维度项目以对比颜色显示。"

<!-- markdownlint-enable MD034 -->

1. 转到包含要用作演示文稿基础的数据的Workspace项目。

1. 选择页面右上角的&#x200B;**[!UICONTROL 生成幻灯片]**。

1. 指定以下信息：

   | 选项 | 描述 |
   |---------|----------|
   | **[!UICONTROL 封面标题]** | 指定演示文稿的标题。 此标题显示在演示文稿的标题幻灯片上。 |
   | **[!UICONTROL 包括演示者姓名]** | 指定演示者的名称。 此名称显示在演示文稿的标题幻灯片上，位于封面标题的下方。 |
   | **[!UICONTROL 要包括的面板和可视化图表]** | 选择要包含在演示文稿中的面板和可视化图表。 您最多可以包含50个可视化图表。<p>大多数面板和可视化图表都受支持。 有关不支持的面板和可视化的信息，请参阅[不支持的项目元素和功能](#unsupported-project-elements-and-features)。</p> |
   | **[!UICONTROL 面板和可视化图表描述]** | |
   | **[!UICONTROL 注释]** | |
   | **[!UICONTROL 强调组件]** | 从可视化图表中最多选择5个要在演示文稿中强调的量度和5个维度。<p>未强调时，组件在演示文稿中显示如下：<ul><li>**量度和维度：**&#x200B;斜体</li><li>**Dimension项：**&#x200B;引号</li></ul></p><p>当应用强调时，组件在演示文稿中显示如下：</p><ul><li>**量度和维度：**&#x200B;斜体和粗体</li><li>**Dimension项目：**&#x200B;当强调相应的维度时为粗体<p>在图表中突出显示维度项时，也会对维度项应用颜色。</p></li></ul> |

（视情况而定）如果希望使用默认主题生成幻灯片，请选择&#x200B;**[!UICONTROL 默认主题]**。

1. 选择使用默认主题还是上传自定义模板：

   * **[!UICONTROL 默认主题]**：

   * **[!UICONTROL 上载模板]**：





## 从之前生成的演示文稿中编辑幻灯片


## 下载生成的.pptx演示

## 不支持的项目元素和功能 {#unsupported}

生成幻灯片时，不支持项目中使用的以下Analysis Workspace元素和功能：

* 归因面板

  显示配置选项时，此面板将暗显。

  所有其他面板都可以包含在从Workspace项目生成的幻灯片中。

* 某些可视化图表

  大多数可视化图表都可以包含在从Workspace项目生成的幻灯片中。 但是，在显示配置选项时，以下可视化图表无法包含和显示为灰色：

   * 同类群组表

   * 历程画布

   * 项目符号

   * 组合

   * 散点图

   * 树状图

* 细分

* 引导式分析


