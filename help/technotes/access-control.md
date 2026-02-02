---
title: Customer Journey Analytics 访问控制
description: 了解如何在 Customer Journey Analytics 中实施访问控制。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: e51dced9ac7886ae8d087ca3b2fc6ac2755c3ac6
workflow-type: ht
source-wordcount: '1551'
ht-degree: 100%

---

# 访问控制

三个访问级别或三个角色负责管理 Customer Journey Analytics：产品管理员角色、产品配置文件管理员角色和用户级别访问。本主题将更详细地解释这些角色。

此外，这篇文章还讨论了更加细粒度化的访问限制方法，如工作区策划、行级和值级访问控制。

## 基于角色的访问控制

以下基于角色的访问控制级别可用。

### 产品管理员角色

默认情况下，分配了产品管理员角色的用户会获得在 Customer Journey Analytics 中执行大多数任务所需的权限。但是，有些任务需要额外的权限。

要将用户添加为产品管理员：

1. 前往 [Admin Console](https://adminconsole.adobe.com/enterprise/)。

1. 选择 [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **管理员**]&#x200B;选项卡 > [!UICONTROL **添加管理员**]。

   您添加的用户会获得[产品管理员默认权限](#product-admin-default-permissions)。如果需要，您还可以授予他们[额外权限](#product-admin-additional-permissions)。

#### 产品管理员默认权限

产品管理员具有相应的权限，能够完成 Customer Journey Analytics 中的大多数任务。

默认情况下，产品管理员获得必要的权限，能够执行以下任务：

* 更新及删除项目、区段、计算量度、受众、批注或其他用户创建的区段
* 将工作区项目共享给所有用户
* 在[报告活动管理器](/help/reporting-activity-manager/reporting-activity-overview.md)中管理报告活动
* 从 Analysis Workspace [导出完整表格](/help/analysis-workspace/export/export-cloud.md)

#### 产品管理员的其他权限

除了在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 的 **Customer Journey Analytics 产品配置文件**&#x200B;中添加为产品管理员外，还需要有额外的权限才能在 Customer Journey Analytics 中完成以下任务：

* 创建、更新和删除[数据视图](/help/data-views/data-views.md)。
* 创建、更新和删除[连接](/help/connections/overview.md)

  要执行此任务，用户必须是提供以下权限的 **Experience Platform 产品配置文件**&#x200B;的一部分：

  | 类别 | 权限 | 描述 |
  |---|---|---|
  | [!UICONTROL 沙盒] | [!UICONTROL 至少一个] | 访问相关的沙盒用于连接。 |
  | [!UICONTROL 数据建模] | [!UICONTROL 查看架构] | 架构和相关资源的只读访问权限。 |
  | [!UICONTROL 数据建模] | [!UICONTROL 管理架构] | 读取、创建、编辑和删除架构和相关资源的访问权限。 |
  | [!UICONTROL 数据管理] | [!UICONTROL 查看数据集] | 数据集和架构的只读访问权限。 |
  | [!UICONTROL 身份标识管理] | [!UICONTROL 查看身份标识命名空间] | 身份标识命名空间的只读访问权限。 |

  关于 Experience Platform 权限的详细信息请参阅[管理产品配置文件的权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/ui/permissions)。


* 如果 Journey Optimizer 与存在 Journey Optimizer 连接的 Customer Journey Analytics 集成，就必须添加历程权限才能访问连接：

  | 类别 | 权限 | 描述 |
  |---|---|---|
  | [!UICONTROL 历程] | [!UICONTROL 查看历程事件、数据源和操作] | 历程事件、历程自定义操作和历程数据源的只读访问权限。 |
  | [!UICONTROL 历程] | [!UICONTROL 管理历程事件、数据源和操作] | 读取、创建、编辑和删除事件、源或操作。 |
  | [!UICONTROL 历程] | [!UICONTROL 查看历程] | 历程的只读访问权限。 |
  | [!UICONTROL 历程] | [!UICONTROL 管理历程] | 读取、创建、编辑和删除历程。 |

* 将数据集导出到[目标](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets)

  要执行此任务，用户必须是提供以下权限的 **Experience Platform 产品配置文件**&#x200B;的一部分：

  | 类别 | 权限 | 描述 |
  |---|---|---|
  | [!UICONTROL 目标] | [!UICONTROL 管理目标] | 读取、创建和删除目标连接和目标帐户的访问权限。 |
  | [!UICONTROL 目标] | [!UICONTROL 激活目标] | 允许用户将区段激活到现有目标。在激活工作流中启用映射步骤。此权限还要求给想要将数据激活到目标的用户授予“查看目标”权限。 |

  关于 Experience Platform 权限的详细信息请参阅[管理产品配置文件的权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/ui/permissions)。

* 使用 [BI 扩展](../data-views/bi-extension.md)

  要让用户使用 BI 扩展，产品管理员

   * 必须确保用户的 Experience Platform 权限包括一个有查询服务资源的角色，并且有“管理查询”和“管理查询服务集成”选项。关于 Experience Platform 权限的详细信息请参阅[管理产品配置文件的权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/ui/permissions)。

     | 类别 | 权限 | 描述 |
     |---|---|---|
     | [!UICONTROL 查询服务] | [!UICONTROL 管理查询] | 读取、创建、编辑和删除 Platform 数据的结构化 SQL 查询的访问权限。 |
     | [!UICONTROL 查询服务] | [!UICONTROL 管理查询服务集成] | 创建、更新和删除未过期的查询服务访问凭据的访问权限。 |

   * 必须确保用户有适当的 Customer Journey Analytics 权限：
      * 相关数据视图的访问权限。查看[用户级别的访问](#user-level-access)中的[!UICONTROL 数据视图]。
      * Customer Journey Analytics BI 扩展的访问权限。查看[用户级别的访问](#user-level-access)中的[!UICONTROL 数据视图工具]。

### 产品配置文件管理员角色

产品配置文件是一组权限。产品管理员可以创建产品配置文件，可以分配产品配置文件管理员以管理一个或多个产品配置文件。分配后，产品配置文件管理员可以：

* 管理所分配的产品配置文件。例如，添加或移除用户或用户组，以及更改产品配置文件的权限。

* 在 Customer Journey Analytics 中编辑成为所分配产品配置文件一部分的数据视图。产品配置文件管理员无法创建新的数据视图。

### 用户级别访问

下表概述了您可以为相关用户配置的各种 Customer Journey Analytics 功能的主要访问权限。您可以通过产品配置文件管理不同级别的用户访问权限。产品配置文件将大量权限组合在一起，您可以将这些权限分配给单个用户或用户组。

**[!UICONTROL 权限]**&#x200B;选项卡是 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中每个产品配置文件的一部分。

![Admin Console 权限](assets/permissions.png)

| 类别 | 权限 | 描述 |
| --- | --- | ---|
| [!UICONTROL 数据视图] | *数据视图名称* | 如果您将&#x200B;**[!UICONTROL 自动包含]**&#x200B;切换到&#x200B;**[!UICONTROL 开启]**，则属于此产品配置文件的用户可以查看所有现有和新创建的数据视图。如果此设置被设置为&#x200B;**[!UICONTROL 关闭]**，则可以选择用户有权访问的特定数据视图。 |
| [!UICONTROL 报告工具] | [!UICONTROL Analysis Workspace 访问权限] | 允许用户访问 [Analysis Workspace](/help/analysis-workspace/home.md)。 |
| [!UICONTROL 报告工具] | [!UICONTROL 引导式分析访问权限] | 允许用户访问[引导分析](/help/guided-analysis/overview.md)。 |
| [!UICONTROL 报告工具] | [!UICONTROL 计算量度创建] | 允许用户创建[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。用户只能标记、共享、删除、重命名、批准和取消批准自己创建的计算量度或与他们共享的计算量度。 |
| [!UICONTROL 报告工具] | [!UICONTROL 区段创建] | 允许用户创建[区段](/help/components/segments/seg-overview.md)。用户只能标记、共享、删除、重命名、批准和取消批准自己创建的区段或与他们共享的区段。 |
| [!UICONTROL 报告工具] | [!UICONTROL Labs 访问权限] | 允许用户访问 Customer Journey Analytics 中的 [Labs](/help/labs/labs.md) 选项卡。 |
| [!UICONTROL 报告工具] | [!UICONTROL 注释创建] | 允许用户创建[注释](/help/components/annotations/overview.md)。用户只能标记、共享、删除和重命名自己创建的注释或与他们共享的注释。 |
| [!UICONTROL 报告工具] | [!UICONTROL 受众视图] | 允许用户查看[受众](/help/components/audiences/audiences-overview.md)。 |
| [!UICONTROL 报告工具] | [!UICONTROL 受众创建] | 允许用户创建[受众](/help/components/audiences/audiences-overview.md)。需要 Adobe Experience Platform 中的[管理区段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/home)。 |
| [!UICONTROL 报告工具] | [!UICONTROL 数据故事讲述] | 允许用户[根据 Workspace 项目生成幻灯片演示文稿。](/help/analysis-workspace/curate-share/generate-slides.md) |
| [!UICONTROL 报告工具] | [!UICONTROL 审核日志访问] | 强制对 [API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/) 和审核日志 UI 进行权限检查。 |
| [!UICONTROL 报告工具] | [!UICONTROL 与任何人共享项目链接] | 允许用户[与任何人共享项目。](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL 报告工具] | [!UICONTROL 预测] | 允许用户访问 Analysis Workspace 中的[预测](../analysis-workspace/c-forecast/forecasting.md)功能 |
| [!UICONTROL 报告工具] | [!UICONTROL AI 助手：产品知识] | 允许用户访问 [AI 助手](../ai-assistant.md)，了解产品知识。 |
| [!UICONTROL 报告工具] | [!UICONTROL 智能题注] | 允许用户访问[智能题注](/help/analysis-workspace/visualizations/intelligent-captions.md)。 |
| [!UICONTROL 数据视图工具] | [!UICONTROL 完整表格导出] | 允许用户[将完整表格导出到云](/help/analysis-workspace/export/export-cloud.md)。 |
| [!UICONTROL 数据视图工具] | [!UICONTROL CJA BI 扩展] | 允许用户使用 [BI 扩展](../data-views/bi-extension.md)。 |

{style="table-layout:auto"}

## 工作区项目策划

可以在工作区报告级别使用另一级别的访问控制。您可以限制某些用户对特定组件的访问。有关如何在工作区项目级别限制组件（维度、量度、区段、日期范围）以及如何将管理与数据视图绑定在一起的更多信息，请参阅[管理项目](/help/analysis-workspace/curate-share/curate.md)。

## 授予对单个量度或维度的访问权限

您不能像在传统的 Adobe Analytics 中那样，在 Customer Journey Analytics 中授予或拒绝针对单个量度或维度的权限。 量度和维度可以在[数据视图](/help/data-views/data-views.md)中更改，因此可能会在 Customer Journey Analytics 中发生变化。更改它们也会追溯性地更改报告。

## 用例

这里有几个用例说明了如何在现实场景中使用访问控制。

### 第三方访问

您可以向贵公司合作的第三方的团队负责人提供产品配置文件管理访问权限。然后，这位管理员可以将公司团队的用户添加到这个产品配置文件。这位产品配置文件管理员可以授予对特定数据视图的访问权限，并将第三方的其他用户添加到这个产品配置文件。产品配置文件管理员可以更改数据视图，以满足第三方团队的要求。

### 行级访问控制

您想授予用户只访问一天的数据的权限。以下是如何限制对这些特定行的访问：

1. 在特定数据视图的[!UICONTROL 设置]中创建一个区段，其中的[!UICONTROL 天]就是您希望允许他们访问数据的那个日期。更多信息请参阅[创建数据视图](/help/data-views/create-dataview.md#settings-filters)。
1. 保存数据视图，这会将这个区段应用于基础连接中数据集的数据部分。任何不符合区段定义的行都会自动从数据视图中排除，在 Analysis Workspace 中使用这个数据视图时，这些行都不可用。
1. 在 Admin Console 中创建一个新的[产品配置文件](#product-profile-admin-role)，将用户添加到产品配置文件，并且仅将这个特定的数据视图添加到产品配置文件。

### 值级访问控制

有权访问数据视图的用户只能使用管理员在这个数据视图中包含的量度和维度。管理员可以在数据视图中使用[包含/排除功能](/help/data-views/component-settings/include-exclude-values.md)或[值分段](../data-views/component-settings/value-bucketing.md)组件设置，从数据视图中排除或聚合特定的维度值。

例如：您从一个其中包含数据集中单个患者数据的组件，在数据视图中创建了一个名为&#x200B;*高血压*&#x200B;的量度。您使用值分段提供只是对分段值的访问权限，这样数据的用户就看不到单个患者的数据。
