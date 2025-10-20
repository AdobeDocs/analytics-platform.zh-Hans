---
description: 了解如何从Workspace报表以pptx格式生成演示文稿。
keywords: Analysis Workspace
title: 从Workspace报表生成演示
feature: Curate and Share
role: User
hide: true
hidefromtoc: true
source-git-commit: 9e23382800326440ed2a583e80029c9f27bb2494
workflow-type: tm+mt
source-wordcount: '1134'
ht-degree: 4%

---

# 数据storytelling：从Workspace报表生成幻灯片演示 {#generate-powerpoint}

具有[必要权限](#permission-requirements-to-generate-slides)的用户可以从Analysis Workspace项目自动生成.pptx演示文稿。 在生成这些幻灯片演示文稿时，Customer Journey Analytics通过识别关键见解并将其转换为可供利益相关者使用的幻灯片，自动根据您的数据创建故事。

此功能可减少从您的Workspace项目揭示发现结果所需的时间和精力，并且允许您快速构建管理层叙述并将业务影响传达给利益相关者。

这个自动生成的数据故事允许分析人员专注于数据探索，而Customer Journey Analytics会编排分析人员的调查结果并将其格式化，以供利益相关者使用。

## 了解幻灯片演示文稿中的数据故事

Analysis Workspace使用创新型人工智能在幻灯片演示文稿中创建数据故事。 这些数据故事通过提供其他上下文、呈现重要亮点并提供后续步骤的想法，对给定Workspace项目的分析进行了补充。 指出隐藏的趋势、异常、影响因素、关键驱动因素

### 数据故事提供的附加值

数据故事通过以下方式补充给定Workspace项目的分析：

* 提供其他上下文

* 突出显示重要见解

* 揭示隐藏的趋势、异常和其他促成因素

* 确定关键驱动因素

* 提出后续步骤的想法

### 塑造数据故事的项目元素

Analysis Workspace通过考虑以下项目元素来创建数据故事：

* 维度间和量度间关系

* 构成分析基础的单个元素：维度、量度、过滤器、自由格式表结构、可视化图表和面板

* 为面板、表格和可视化图表指定的名称

* 自由格式表中的量度排序（用于确定优先级）

* 摘要数字和摘要文本（用于确定在数据故事中需要突出显示的量度）

### 数据故事的呈现元素

数据故事由执行摘要幻灯片、详细信息幻灯片和分区符组成。

**执行摘要：**&#x200B;排定最高价值洞察内容的优先级，并制作长度介于1到5个句子之间的总体故事。

**详细信息幻灯片：**&#x200B;生成与Workspace项目中的任何表、面板或可视化图表相关的洞察。 洞察由趋势、季节性、异常和关联性组成。

**分区分隔符：**&#x200B;使用适当放置和命名的分区分隔符来划分见解。

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

1. 转到包含要用作幻灯片演示文稿基础的数据的Workspace项目。

1. 选择页面右上角的&#x200B;**[!UICONTROL 生成幻灯片]**。

   此时将显示“生成幻灯片”对话框。

   ![生成幻灯片对话框](assets/generate-slides.png)

1. 指定以下信息：

   | 选项 | 描述 |
   |---------|----------|
   | **[!UICONTROL 封面标题]** | 指定演示文稿的标题。 此标题显示在演示文稿的标题幻灯片上。 |
   | **[!UICONTROL 包括演示者姓名]** | 指定演示者的名称。 此名称显示在演示文稿的标题幻灯片上，位于封面标题的下方。 |
   | **[!UICONTROL 要包括的面板和可视化图表]** | 选择要包含在演示文稿中的面板和可视化图表。 您最多可以包含50个可视化图表。<p>大多数面板和可视化图表都受支持。 有关不支持的面板和可视化的信息，请参阅[不支持的项目元素和功能](#unsupported-project-elements-and-features)。</p> |
   | **[!UICONTROL 面板和可视化图表描述]** | |
   | **[!UICONTROL 注释]** | |
   | **[!UICONTROL 强调组件]** | 从可视化图表中最多选择5个要在演示文稿中强调的量度和5个维度。<p>未强调时，组件在演示文稿中显示如下：<ul><li>**量度和维度：**&#x200B;斜体</li><li>**Dimension项：**&#x200B;引号</li></ul></p><p>当应用强调时，组件在演示文稿中显示如下：</p><ul><li>**量度和维度：**&#x200B;斜体和粗体</li><li>**Dimension项目：**&#x200B;当强调相应的维度时为粗体<p>在图表中突出显示维度项时，也会对维度项应用颜色。</p></li></ul> |

1. （视情况而定）如果您希望以较少的步骤快速生成幻灯片，并且幻灯片演示不需要公司主题，请选择&#x200B;**[!UICONTROL 默认主题]**。

   只需通过选择所需颜色来选择演示文稿的颜色主题即可。

   ![使用默认主题生成幻灯片](assets/generate-slides-default-theme.png)

1. （视情况而定）如果您的幻灯片演示文稿需要匹配公司主题，请选择&#x200B;**[!UICONTROL 上传模板]**。 此选项要求您上传自定义模板并应用自定义样式。

   ![使用自定义模板生成幻灯片](assets/generate-slides-upload-template.png)

   要上传自定义模板，请执行以下任一操作：

   * （推荐）下载并修改空白模板。

      1. 下载此空白模板。<!--add link-->

      1. 将自定义样式应用于空白模板。

      1. 重新上传模板而不更改任何主布局名称。

   * 直接上传自定义模板。

      1. 将自定义模板从文件系统拖到放置区域。

         或

         选择&#x200B;**[!UICONTROL 浏览]**，然后浏览并从文件系统中选择您的自定义模板。

         确保上传的文件具有具有以下名称的主布局：“Title_Slide”、“Section_Divider”、“Title_Text”、“Title_Chart”、“Title_Two_Content_Mixed”、“Title_Three_Content_Mixed”

         支持大小最大为25MB的.pptx和.potx文件。

1. 选择&#x200B;**[!UICONTROL 导出PPT]**。

1. （推荐）查看和编辑.ppt演示文稿，并进行任何所需的更改，如下一节[从之前生成的演示文稿中编辑幻灯片](#edit-slides-from-a-previously-generated-presentation)中所述。

## 从之前生成的演示文稿中编辑幻灯片


## 下载生成的.pptx演示



## 生成幻灯片的权限要求

>[!AVAILABILITY]
>
>如果贵组织无权从Workspace项目生成幻灯片演示，请联系您的Adobe客户代表以了解有关许可的更多信息。
>
>默认情况下，组织中拥有所需许可的所有用户都启用此功能。

如果需要，组织有权生成幻灯片的产品配置文件管理员可以禁用访问权限。

在[!UICONTROL Adobe Admin Console]中，[!UICONTROL 报表工具] **[!UICONTROL Data storytelling]**&#x200B;权限决定了对此功能的访问权限。 如果[产品配置文件管理员](https://helpx.adobe.com/cn/enterprise/using/manage-product-profiles.html)想要禁用访问权限，则需要在[!UICONTROL Admin Console]中执行这些步骤：
1. 导航至 **[!UICONTROL Admin Console]** > **[!UICONTROL 产品和服务]** > **[!UICONTROL Customer Journey Analytics]** > **[!UICONTROL 产品配置文件]**。
1. 选择您要为其提供[!UICONTROL 数据storytelling]访问权限的产品配置文件的标题。
1. 在具体的产品配置文件中，选择&#x200B;**[!UICONTROL 权限]**。
1. 选择![编辑](/help/assets/icons/Edit.svg)来编辑&#x200B;**[!UICONTROL 报告工具]**。
1. 选择![AddCircle](/help/assets/icons/RemoveCircle.svg)以从&#x200B;**包含的权限项**&#x200B;中删除&#x200B;**[!UICONTROL Data storytelling]**。

   <!--add screenshot of permission in the admin console-->

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;来保存权限。

有关详细信息，请参阅[访问控制](/help/technotes/access-control.md#user-level-access)中的[用户级访问](/help/technotes/access-control.md#access-control)。

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


