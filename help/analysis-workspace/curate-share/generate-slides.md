---
description: 了解如何从Workspace报表以pptx格式生成演示文稿。
keywords: Analysis Workspace
title: 从Workspace报表生成演示
feature: Curate and Share
role: User
source-git-commit: 82ca99af8f344b713e285980145fa0ee6ae6ae1c
workflow-type: tm+mt
source-wordcount: '1682'
ht-degree: 6%

---

# 数据storytelling：从Workspace报表生成幻灯片演示 {#generate-powerpoint}

>[!AVAILABILITY]
>
>数据Storytelling是[Data Insights Agent](/help/data-analysis-ai.md)下的技能。 此功能处于版本的有限测试阶段，在您的环境中可能尚未可用。 当该功能正式发布时，将删除此说明。有关 Customer Journey Analytics 发布流程的信息，请参阅 [Customer Journey Analytics 功能版本](/help/release-notes/releases.md)。

<!-- also remove lmited testing note from: /help/technotes/access-control.md -->

<!--at GA in January, replace Limited Testing note with this: Data Storytelling is a skill under Data Insights Agent and is available to eligible customers for a limited time. Access to Data Insights Agent will end on 28th February 2026. To continue using Data Insights Agent or other Adobe Experience Platform Agents without interruption, please contact your Adobe account representative to learn more about licensing Adobe Experience Platform Agent Orchestrator. -->

具有[必要权限](#permission-requirements-to-generate-slides)的用户可以基于Analysis Workspace项目自动生成.pptx演示文稿。 在生成这些幻灯片演示文稿时，Customer Journey Analytics通过识别关键见解并将其转换为可供利益相关者使用的幻灯片，自动根据您的数据创建故事。

这个生成的数据故事减少了从Workspace项目揭示调查结果所需的时间、精力和专业知识。 分析人员可以更专注于数据探索，同时允许Customer Journey Analytics构建和格式化执行叙述，并将业务影响传达给利益相关者。

## 了解幻灯片演示文稿中的数据故事

**数据故事**&#x200B;是Customer Journey Analytics根据您的Workspace数据创建的故事。 使用创作AI，Customer Journey Analytics会识别您选择包含在幻灯片演示文稿中的面板和可视化图表中的重要主题。 它生成见解，然后执行重复数据删除和评分过程，以识别用于创建数据故事的见解子集。

以下各节介绍数据故事提供的附加值、项目中有助于塑造故事的必要元素，以及.pptx演示文稿输出中包含的关键元素。

### 数据故事提供的附加值

数据故事通过让数据分析经验较少的用户访问数据，为Workspace项目提供价值和见解。

数据故事通过以下方式补充给定Workspace项目的分析：

* 提供其他上下文

* 突出显示重要见解

* 评估某些变量是低估还是高估

* 揭示隐藏的趋势、异常和其他促成因素

* 提出后续步骤的想法

### 塑造数据故事的项目元素

Analysis Workspace通过考虑以下项目元素来创建数据故事：

* 维度间和量度间关系

* 构成分析基础的单个元素（维度、量度、过滤器、自由格式表结构、可视化图表和面板）

* 为面板、表格和可视化图表指定的名称

* 自由格式表中的量度排序（用于确定优先级）

* 面板中可视化图表的排序（用于确定优先级）

* 摘要数字和摘要文本（用于确定在数据故事中需要突出显示的量度）

### 数据故事的呈现元素

数据故事由标题幻灯片、执行摘要幻灯片、详细信息幻灯片和分区符组成。

**标题幻灯片：**&#x200B;显示您指定的标题和演示者姓名。 演讲人备注中展示的信息描述了主题和叙述的创建过程、产生和使用了多少见解以及使用哪些面板。

**执行摘要：**&#x200B;排定最高价值见解的优先级，并制作长度介于1到5句之间的总体故事。

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
>title="被强调的组件"
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
   | **[!UICONTROL 要包括的面板和可视化图表]** | 选择要包含在演示文稿中的面板和可视化图表。 您最多可以包含50个可视化图表。<p>如果可视化图表灰显，则它后面会跟有文本&#x200B;**[!UICONTROL （不支持）]**&#x200B;或&#x200B;**[!UICONTROL （受限制的数据）]**。</p><ul><li>**不支持**：支持大多数面板和可视化图表。 有关不支持的面板和可视化的信息，请参阅[不支持的项目元素和功能](#unsupported-project-elements-and-features)。</li><li>**受限制的数据**：该可视化图表包含受组织强制实施的数据治理策略限制无法导出的组件。 请联系您的系统管理员以查看哪些组件被限制导出，然后在生成幻灯片之前删除受限制的组件。</li></ul> |
   | **[!UICONTROL 强调组件]** | 从可视化图表中选择要在演示文稿中强调的量度和维度。 在创建数据故事的主题和总体叙述时，您选择的组件排名较高，具有更大的权重。 <p>未强调时，组件在演示文稿中显示如下：<ul><li>**量度和维度：**&#x200B;斜体</li><li>**Dimension项：**&#x200B;引号</li></ul></p><p>当应用强调时，组件在演示文稿中显示如下：</p><ul><li>**量度和维度：**&#x200B;斜体和粗体</li><li>**Dimension项目：**&#x200B;当强调相应的维度时为粗体<p>在图表中突出显示维度项时，也会对维度项应用颜色。</p></li></ul> |

   <!-- add this later: - **[!UICONTROL Panel and visualization descriptions]** - Choose whether to include panel and visualization descriptions in your generated slide presentation. - 
   - **[!UICONTROL Annotations]** - Choose whether annotations are visible in your generated slide presentation. For more information about annotations, see [Annotations overview](/help/components/annotations/overview.md).  -  -->

1. （视情况而定）如果您希望以较少的步骤生成幻灯片，并且幻灯片演示不需要公司主题，请选择&#x200B;**[!UICONTROL 默认主题]**。

   只需通过选择所需颜色来选择演示文稿的颜色主题即可。

   ![使用默认主题生成幻灯片](assets/generate-slides-default-theme.png)

1. （视情况而定）如果您的幻灯片演示文稿需要匹配公司主题，请选择&#x200B;**[!UICONTROL 上传模板]**。 此选项要求您上传自定义模板并应用自定义样式。

   您上传的最新自定义模板存储在本地浏览器缓存中，并在生成将来的幻灯片演示文稿时可用。

   ![使用自定义模板生成幻灯片](assets/generate-slides-upload-template.png)

   要上传自定义模板，请执行以下任一操作：

   +++（推荐）下载并修改空白模板

   1. 下载[此空白模板](https://d30ln29764hddd.cloudfront.net/deploy/builds/data-storytelling.2025-10-20T15:10:19/resources/components/Blank.potx?)。

   1. 将自定义样式应用于空白模板。

   1. 重新上传模板而不更改任何主布局名称：

      从文件系统中，将应用了自定义样式的空白模板拖放到拖放区域。

      或

      选择&#x200B;**[!UICONTROL 浏览]**，然后浏览并选择从文件系统应用了自定义样式的空白模板。

   1. 在&#x200B;**[!UICONTROL 布局映射]**&#x200B;部分中，生成的演示文稿中使用的每个幻灯片布局都会自动映射到上载主题中的幻灯片。 查看所选内容以确保其正确无误。

      ![布局映射](assets/generate-slides-layout-mapping.png)

   1. （视情况而定）如果幻灯片布局映射不正确，请选择从上载的演示文稿中选择的幻灯片上方的&#x200B;**[!UICONTROL 更改选择]**，然后选择与布局匹配的幻灯片。

      对未正确映射的每张幻灯片重复此过程。

   +++

   +++直接上传自定义模板 

   1. 将自定义模板从文件系统拖到放置区域。

      或

      选择&#x200B;**[!UICONTROL 浏览]**，然后浏览并从文件系统中选择您的自定义模板。

      确保上传的文件具有具有以下名称的主布局：“Title_Slide”、“Section_Divider”、“Title_Text”、“Title_Chart”、“Title_Two_Content_Mixed”、“Title_Three_Content_Mixed”。

      最多支持 25 个主布局。

      支持最大 25MB 的 .pptx 和 .potx 文件。

   1. 在&#x200B;**[!UICONTROL 布局映射]**&#x200B;部分中，生成的演示文稿中使用的每个幻灯片布局都会自动映射到上载主题中的幻灯片。 查看所选内容以确保其正确无误。

      ![布局映射自定义模板](assets/generate-slides-layout-mapping-custom-template.png)

   1. （视情况而定）如果幻灯片布局映射不正确，请选择从上载的演示文稿中选择的幻灯片上方的&#x200B;**[!UICONTROL 更改选择]**，然后选择与布局匹配的幻灯片。

      对未正确映射的每张幻灯片重复此过程。

   +++

1. 选择&#x200B;**[!UICONTROL 导出PPT]**。

   .pptx演示文稿会自动下载到您的工作站。

1. （推荐）打开.pptx演示文稿并进行查看。 进行任何所需的更改。

## 生成幻灯片的权限要求

>[!AVAILABILITY]
>
>如果贵组织无权从Workspace项目生成幻灯片演示，请联系您的Adobe客户代表以了解有关许可的更多信息。

默认情况下，组织中拥有所需许可的所有用户都会启用生成幻灯片的功能。

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

   * 面积图

   * 项目符号

   * 同类群组表

   * 组合

   * 流失

   * 流量

   * 历程画布

   * 散点图

   * 树状图

* 引导式分析

* 数据治理策略限制无法导出的组件

  有关详细信息，请参阅[导出失败疑难解答](/help/components/exports/troubleshoot-exports.md)。

## 有限支持的项目元素和功能

* 细分

  在生成相关见解时，作为重复数据删除和评分过程的一部分，会单独分析自由格式表中的每个划分，并且只分析单个自由格式表中的前5个划分。

  仅支持第一级细分。 划分不包含在演示文稿中。


