---
title: 配置Content Analytics（独立）
description: 将Adobe Content Analytics配置为独立解决方案的分步指南。 了解如何设置架构、数据集、数据流和报表，以便在没有完整Customer Journey Analytics实施的情况下获得全面的内容性能见解。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
source-git-commit: f95910d3bd6e9f0e7be7bf272e9c363b4a4a5429
workflow-type: tm+mt
source-wordcount: '2539'
ht-degree: 6%

---

# 独立配置

>[!IMPORTANT]
>
>本配置指南适用于已获得独立Adobe Content Analytics软件包许可的客户。 本指南假定您尚未使用或计划使用Customer Journey Analytics或Content Analytics功能和特性之外的任何其他Experience Platform应用程序。 如果要配置和使用Content Analytics作为现有Customer Journey Analytics实施的一部分，请参阅[配置Content Analytics](configuration.md)。
>

Content Analytics作为独立产品授予许可，但配置是在Experience Platform和Customer Journey Analytics中进行的。 这些平台提供了Content Analytics需要和使用的数据收集和分析基础架构。 本指南提供了您需要的所有具体说明，即使您是Experience Platform和Customer Journey Analytics的新手。

在开始设置独立Content Analytics之前，您应：

* 基本了解Web分析概念，熟悉标签管理系统，并具备JavaScript基础知识。
* 规划4 - 6小时进行初始设置，并安排额外的时间来测试和验证设置。

## 术语

本指南使用来自Experience Platform和Customer Journey Analytics的多个技术术语，您可能不熟悉这些术语。 以下是Content Analytics中这些术语（带有引用链接）的说明：

| 术语 | 说明 |
|---|---|
| **架构** | [架构](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition)是一组规则，用于表示和验证数据的结构和格式。 在高层面上，架构提供了真实世界对象的抽象定义，例如网站上发生的事件，如点击。 并概述该对象的每个实例中应包含哪些数据。 |
| **数据集** | [数据集](https://experienceleague.adobe.com/en/docs/experience-platform/catalog/datasets/overview)是用于数据集合的存储和管理结构，通常是包含架构（列）和字段（行）的表。 数据集类似于数据库表，其中每一行都是来自您网站的事件。 |
| **数据流** | [数据流](https://experienceleague.adobe.com/en/docs/experience-platform/datastreams/overview)表示将数据从您的网站路由到Adobe Experience Platform中的正确数据集的服务器端配置。 数据流充当连接您的网站与存储的数据高速公路。 |
| **标记** | Experience Platform中的[标记](https://experienceleague.adobe.com/en/docs/experience-platform/tags/home)是Adobe推出的新一代标记管理功能。 标记为客户提供了一种简单的方式来部署和管理用来加强相关客户体验的分析、营销和广告标记。 在Content Analytics中，Adobe的标签管理系统允许您在网站上部署跟踪代码，而无需以类似方式编辑每个页面。 标记功能类似于您可能从Google Tag Manager中了解的功能。 |
| **沙盒** | Experience Platform提供了[沙盒](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sandbox/home)，可将单个Experience Platform实例划分为单独的虚拟环境，以帮助开发和改进数字体验应用程序。 Content Analytics通常使用&#x200B;*生产*&#x200B;沙盒。 |
| **连接** | [连接](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview)定义要引入的Experience Platform数据集。 连接定义了数据集(数据存储在AEP中)与Customer Journey Analytics（可在其中分析数据）之间的链接。 通过连接，收集的数据可用于报告。 |
| **** | [数据视图](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/data-views)是一个容器，通过它可决定如何解释来自连接的数据。 数据视图指定可用于报告的所有维度和量度。 数据视图与确定可在分析中使用的行和列的配置类似。 |
| **Analysis Workspace** | [Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/home)是用于构建Content Analytics报告和分析的拖放浏览器界面。 |
| **体验** | 在Content Analytics中，[体验](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology)是指网页上所有可根据页面URL捕获和分析的文本内容。 |
| **资源** | 在Content Analytics中，[资源](https://experienceleague.adobe.com/en/docs/analytics-platform/using/content-analytics/content-analytics#terminology)是个别且唯一的内容，如图像。 |


## 设置概述

此配置将指导您设置需要具有有效的&#x200B;**独立** Content Analytics实施的所有应用程序。 您可以将设置分为三个阶段，每个阶段均在前一个阶段的基础上进行构建：

**阶段1** - [准备环境](#prepare-your-environment)。 在此阶段，您需要设置用户权限并验证数据基础架构。 如果没有这些适当的权限和数据结构，您将无法完成其余步骤。 涉及的步骤包括：

1. **配置访问控制和权限**&#x200B;以支持Content Analytics配置和实施。
1. **设置架构和数据集**&#x200B;以定义您要从中收集内容分析见解的数据的模型（架构）以及收集该数据（数据集）的位置。

**阶段2** - [配置数据收集](#configure-data-collection)。 在此阶段，您将创建从网站捕获内容数据的管道。 因此，Content Analytics知道访客与您的内容交互的内容。

1. **设置数据流**&#x200B;以配置如何将收集的数据路由到数据集。
1. **使用网站标记**&#x200B;针对网站上数据层中的数据配置规则和数据元素，并确保将数据发送到配置的数据流。
1. **将**&#x200B;部署到测试环境&#x200B;**并验证**&#x200B;数据收集，然后再发布到生产环境。

**阶段3** - [设置报表](#set-up-reporting)。 在此阶段中，使收集的数据可用于在报表中分析。 因此，您实际上可以获得要从Content Analytics中获得的内容性能见解。

1. **设置与您的数据集的连接**。
1. **设置数据视图**&#x200B;以定义量度和维度。
1. **配置和实施Content Analytics**。
1. **设置项目**&#x200B;以生成您的Content Analytics报告和可视化图表。


## 准备环境

在此阶段，您需要设置用户权限并验证数据基础架构。

### 配置访问控制和权限

本节介绍了您需要对产品拥有的访问权限、产品配置文件以及配置和设置独立Content Analytics所需的权限。 尽管您只对Content Analytics的功能感兴趣，但是要使该功能正常工作，您仍需要拥有其他Experience Platform产品的访问权限和权限。

#### 访问控制

访问控制可确定是否允许您访问Experience Platform产品。

您需要系统管理员或产品管理员将您添加为产品或产品配置文件的管理员。 产品管理员只能将您添加为所管理产品（配置文件）的管理员，系统管理员可以将产品管理员添加到任何产品（配置文件）。

>[!BEGINSHADEBOX]

请参阅![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [管理产品配置文件的用户](https://video.tv.adobe.com/v/333860/?quality=12&learn=on){target="_blank"}以观看演示视频。


>[!ENDSHADEBOX]

对于独立Content Analytics，您需要成为以下产品和产品配置文件的产品管理员：

* Adobe Experience Platform
   * AEP-Default-All-Users（用于访问生产沙盒的默认配置文件）

* Adobe Experience Platform 数据收集
   * 默认数据收集所有访问

* Adobe Experience Platform Privacy Service

* Customer Journey Analytics（自定义）
   * Customer Journey Analytics（或任何其他默认配置的产品配置文件）

您可以通过Admin Console定义产品管理员访问权限：

1. 访问[Admin Console](https://adminconsole.adobe.com)。
1. 选择&#x200B;**[!UICONTROL 产品]**。
1. 选择特定产品。
1. 选择&#x200B;**[!UICONTROL 管理员]**&#x200B;选项卡。
1. 选择&#x200B;**[!UICONTROL 添加管理员]**&#x200B;以向产品添加管理员。
1. 在&#x200B;**[!UICONTROL 添加产品管理员]**&#x200B;对话框中输入一个或多个电子邮件或用户名。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存。


您可以通过Admin Console定义产品配置文件管理员访问权限：

1. 访问[Admin Console](https://adminconsole.adobe.com)。
1. 选择&#x200B;**[!UICONTROL 产品]**。
1. 选择特定产品。 确保您已具有产品管理员访问权限。
1. 选择&#x200B;**[!UICONTROL 产品配置文件]**。
1. 选择特定的产品配置文件。
1. 选择&#x200B;**[!UICONTROL 管理员]**&#x200B;选项卡。
1. 选择&#x200B;**[!UICONTROL 添加管理员]**&#x200B;将管理员添加到产品配置文件。
1. 在&#x200B;**[!UICONTROL 添加产品配置文件管理员]**&#x200B;对话框中输入一个或多个电子邮件或用户名。 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存。


#### 权限

权限定义了在您有权访问产品后可以在产品中执行的操作。

您在[!UICONTROL 权限]界面中为Experience Platform定义权限，并使用基于属性的访问控制。 对于Customer Journey Analytics，您通过[!UICONTROL Admin Console]定义权限。

##### Experience Platform

Experience Platform中的[!UICONTROL Permissions]界面基于角色的定义。 角色是基于资源的权限集合。 在新配置的环境中，有两个默认角色可用： **[!UICONTROL 默认的生产所有访问权限]**&#x200B;和&#x200B;**[!UICONTROL 沙盒管理员]**。

对于Content Analytics，您需要验证是否将以下资源和关联的权限添加到这些角色：

* 默认的生产全部访问角色

   * 数据收集
      * 查看数据流
      * 管理数据流

   * 数据管理
      * 查看数据集
      * 管理数据集

   * 数据建模
      * 查看架构
      * 管理架构
      * 管理身份元数据


* 沙盒管理员角色

   * 沙盒
      * Prod
      * (任何其他要用于Content Analytics的沙盒)

   * 沙盒管理
      * 管理包
      * 管理沙盒
      * 重置沙盒
      * 查看沙盒


在“权限”界面中，您可以同时验证角色和相关权限。 以及哪些用户属于该角色。

1. 访问贵组织的Experience Platform。
1. 在欢迎屏幕的&#x200B;**[!UICONTROL 快速访问]**&#x200B;中，选择&#x200B;**[!UICONTROL 查看全部]**。
1. 为![权限](/help/assets/icons/PinOn.svg)启用pin **[!UICONTROL PinOn]**，因此&#x200B;**[!UICONTROL 快速访问]**&#x200B;中的&#x200B;**[!UICONTROL 权限]**&#x200B;可供将来使用。
1. 选择&#x200B;**[!UICONTROL 权限]**。
1. 选择![用户](/help/assets/icons/User.svg) **[!UICONTROL 角色]**。
1. 选择要验证的特定角色（例如，**[!UICONTROL 默认的生产所有访问]**）。 选择&#x200B;**[!UICONTROL 查看全部]**&#x200B;以查看所有权限。
1. 在&#x200B;**[!UICONTROL 详细信息]**&#x200B;屏幕中：
   1. 验证&#x200B;**[!UICONTROL 权限]**&#x200B;中列出的&#x200B;**[!UICONTROL 资源]**。
   1. 验证&#x200B;**[!UICONTROL 沙盒]**&#x200B;中的沙盒名称。

   要进行任何更新，请选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**。
   1. 要添加缺少的资源，请从&#x200B;**[!UICONTROL 资源]** > ![Adobe Experience Platform](/help/assets/icons/Add.svg)左边栏中选择&#x200B;**[!UICONTROL 资源名称]** **[!UICONTROL 添加]**。
   1. 要添加缺少的权限，请在主面板中缺少权限的资源中选择![ChevronDown](/help/assets/icons/ChevronDown.svg)，然后选择缺少的权限。

      ![权限界面](/help/content-analytics/assets/aep-permissions-ui.png)

   选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存任何更新。

1. 在用户或用户组屏幕中：
   1. 验证正确的单个用户或用户组是否属于此角色。
      1. 选择![UserAdd](/help/assets/icons/UserAdd.svg) Add Users in Users以添加您在Admin Console中定义的个人用户。
      1. 选择![添加](/help/assets/icons/Add.svg)在用户组中添加组以添加您在Admin Console中定义的用户组。


##### Customer Journey Analytics

Customer Journey Analytics不支持基于属性的访问控制。 要指定权限，请使用Admin Console。

对于Content Analytics，您需要验证是否包含以下Customer Journey Analytics产品配置文件权限：

* 数据视图
   * 所有可用的数据视图。

* 报告工具
   * 引导式分析访问？
   * 计算量度创建
   * 区段创建
   * Labs访问权限？
   * 创建注释
   * 受众创建？
   * 受众视图？
   * 审核日志访问
   * 与任何人共享项目链接
   * 预测
   * AI 助手：产品知识
   * Data Insights 代理
   * 智能题注
   * 数据Storytelling？

* 数据视图工具
   * 是否导出完整表？
   * CJA BI扩展？

要验证和更新Customer Journey Analytics的这些权限，请执行以下操作：

1. 访问[Admin Console](https://adminconsole.adobe.com)。
1. 选择&#x200B;**[!UICONTROL 产品]**。
1. 选择&#x200B;**[!UICONTROL Customer Journey Analytics]**&#x200B;产品。
1. 选择&#x200B;**[!UICONTROL 产品配置文件]**。
1. 选择可用于Customer Journey Analytics的默认已配置产品配置文件。 例如：**[!UICONTROL Customer Journey Analytics]**。
1. 在产品配置文件屏幕中，选择&#x200B;**[!UICONTROL 权限]**。
1. 选择任意![编辑](/help/assets/icons/Edit.svg)按钮以编辑权限。 在&#x200B;**[!UICONTROL Customer Journey Analytics的编辑权限]**&#x200B;对话框中：

   ![CJA权限UI](../assets/cja-permissions-ui.png)

   1. 选择&#x200B;**[!UICONTROL 数据视图]**&#x200B;并启用&#x200B;**[!UICONTROL 自动包含： On]**。 此切换确保所有数据视图自动成为&#x200B;**[!UICONTROL 包含的权限项]**&#x200B;的一部分。
   1. 选择&#x200B;**[!UICONTROL 报告工具]**&#x200B;并确保上面列出的所有权限都是&#x200B;**[!UICONTROL 包含的权限项]**&#x200B;的一部分。
   1. 选择&#x200B;**[!UICONTROL 数据视图工具]**，并确保上面列出的所有权限都是&#x200B;**[!UICONTROL 包含的权限项]**&#x200B;的一部分。

   选择&#x200B;**[!UICONTROL 保存]**。


### 设置架构和数据集

要在受Content Analytics分析影响的情况下从您的网站收集数据，您首先需要定义要收集的数据类型。 以及数据的存储方式。 在[通过Adobe Experience Platform Web SDK引入数据](/help/data-ingestion/aepwebsdk.md#set-up-a-schema-and-dataset)快速入门指南中的[设置架构和数据集](/help/data-ingestion/aepwebsdk.md)中说明了这两个概念。


## 配置数据收集

在此阶段，您将创建从网站捕获内容数据的管道。

### 设置数据流

您已定义要收集哪些数据以及如何存储这些数据。 下一步是确保将从您的网站收集的数据路由到数据集。 您需要设置和配置数据流，如[通过Adobe Experience Platform Web SDK摄取数据](/help/data-ingestion/aepwebsdk.md#set-up-a-datastream)快速入门指南中的[设置数据流](/help/data-ingestion/aepwebsdk.md)中所述。


### 使用标签

您已定义要收集哪些数据（架构），如何存储该数据（数据集），以及如何将从您的网站收集的数据路由到数据集（数据流）。 接下来，您需要标记您的网站，以针对网站上数据层中的数据配置规则和数据元素。 对网站进行标记可确保将数据发送到配置的数据流。 在[通过Adobe Experience Platform Web SDK摄取数据](/help/data-ingestion/aepwebsdk.md#use-tags)快速入门指南中的[使用标记](/help/data-ingestion/aepwebsdk.md)中说明了使用标记帮助标记网站。


### 部署和验证

现在，您可以在`<head>` 标签内的网站开发版本上部署代码。部署后，您的网站即开始将数据收集到Adobe Experience Platform中。 然后，该数据将受Content Analytics约束。

验证实施并在必要时进行更正，一旦正确，可使用Tags的发布工作流功能将其部署到暂存和生产环境


## 设置报表

在此阶段中，您可以使收集的数据可用于报表中的分析。

### 设置与数据集的连接

要报告收集的数据并为Content Analytics配置这些数据，您需要在Customer Journey Analytics中设置连接。 该连接将连接到包含所收集的数据的数据集。 有关如何设置连接的说明，请参阅[通过Adobe Experience Platform Web SDK摄取数据](../../data-ingestion/aepwebsdk.md#set-up-a-connection)快速入门指南中的[设置连接](/help/data-ingestion/aepwebsdk.md)。


### 设置数据视图

配置Content Analytics之前的最后一步是定义数据视图。 数据视图是 Customer Journey Analytics 专属的容器，通过它，可决定如何解释来自连接的数据。 数据视图允许您根据Customer Journey Analytics连接的一个或多个数据集的数据定义指标和维度。 有关如何设置数据视图的说明，请参阅[通过Adobe Experience Platform Web SDK引入数据](/help/data-ingestion/aepwebsdk.md#set-up-a-data-view)快速入门指南中的[设置数据视图](/help/data-ingestion/aepwebsdk.md)。


### 配置 Content Analytics

您现在已准备好配置Content Analytics所需的一切。

#### 引导配置

使用[引导式配置向导](guided.md)并选择您在[设置数据视图](#set-up-a-data-view)步骤中创建的数据视图。 该选择可确保根据您从网站收集的数据来配置和实施Content Analytics。

请注意，引导式配置向导会配置以下其他特定的Content Analytics对象：

* 自动为Content Analytics事件设置的&#x200B;**数据集**。 此数据集使用已创建且可用的特定Content Analytics架构。
* **数据流**，它自动设置为将Content Analytics事件流式传输到Content Analytics数据集中。
* **Tags属性**，该属性是自动设置并使用Content Analytics扩展配置的。 此Tags属性可确保您的网站将Content Analytics数据发送到Content Analytics数据流和Content Analytics数据集。

  >[!IMPORTANT]
  >
  >请确保选择相应选项，以便在向导的[数据收集](guided.md#new-configuration-1)步骤中创建新的标记属性。
  >


#### 手动配置

要为您的网站实施Content Analytics，您需要手动发布Content Analytics标记属性[](manual.md)。


### 设置项目

在Customer Journey Analytics中设置项目以生成您的[Content Analytics报告和可视化图表](/help/content-analytics/report/report.md)。 或者，您可以使用[Content Analytics模板](/help/content-analytics/report/report.md#template)开始。
