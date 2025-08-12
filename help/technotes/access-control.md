---
title: Customer Journey Analytics 访问控制
description: 了解在Customer Journey Analytics中实施访问控制的方法。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 8da8d22d35e0b4a77da010d0ba5fb230946ccce5
workflow-type: tm+mt
source-wordcount: '1560'
ht-degree: 17%

---

# 访问控制

Customer Journey Analytics由三个访问级别或三个角色控制：产品管理员角色、产品配置文件管理员角色和用户级别访问。 本主题将更详细地解释这些角色。

此外，本文还讨论了限制访问的更加细粒度化的方法，例如Workspace管理和行级以及值级访问控制。

## 基于角色的访问控制

可以使用以下基于角色的访问控制级别。

### 产品管理员角色

默认情况下，分配给产品管理员角色的用户将获得在Customer Journey Analytics中执行大多数任务所需的权限。 但是，某些任务需要附加权限。

要将用户添加为产品管理员，请执行以下操作：

1. 转到[Admin Console](https://adminconsole.adobe.com/enterprise/)。

1. 选择&#x200B;[!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **管理员**]&#x200B;选项卡> [!UICONTROL **添加管理员**]。

   您添加的用户具有[产品管理员默认权限](#product-admin-default-permissions)。 如果需要，您还可以授予他们[其他权限](#product-admin-additional-permissions)。

#### 产品管理员默认权限

产品管理员有权完成Customer Journey Analytics中的大多数任务。

默认情况下，产品管理员有权执行以下任务：

* 创建、更新和删除数据视图
* 更新和删除项目、区段、计算量度、受众、批注或其他用户创建的区段
* 将工作区项目共享给所有用户
* 在[报告活动管理器](/help/reporting-activity-manager/reporting-activity-overview.md)中管理报告活动
* 从Analysis Workspace [导出完整的表](/help/analysis-workspace/export/export-cloud.md)

#### 产品管理员其他权限

除了在&#x200B;**Admin Console**&#x200B;的[Customer Journey Analytics产品配置文件](https://adminconsole.adobe.com/enterprise/)中添加为产品管理员外，还需要其他权限才能在Customer Journey Analytics中完成以下任务：

* 创建、更新和删除数据[连接](/help/connections/overview.md)

  要执行此任务，用户必须是提供以下权限的&#x200B;**Experience Platform产品配置文件**&#x200B;的一部分：

  | 类别 | 权限 | 描述 |
  |---|---|---|
  | [!UICONTROL 沙盒] | [!UICONTROL 至少一个] | 访问CJA连接的相关沙盒。 |
  | [!UICONTROL 数据建模] | [!UICONTROL 查看架构] | 对架构和相关资源的只读访问权限。 |
  | [!UICONTROL 数据建模] | [!UICONTROL 管理架构] | 有权读取、创建、编辑和删除架构和相关资源。 |
  | [!UICONTROL 数据管理] | [!UICONTROL 查看数据集] | 对数据集和架构的只读访问权限。 |
  | [!UICONTROL 数据管理] | [!UICONTROL 管理数据集] | 有权读取、创建、编辑和删除数据集。 架构的只读访问权限。 |
  | [!UICONTROL 数据获取] | [!UICONTROL 管理源] | 有权读取、创建、编辑和禁用源。 |
  | [!UICONTROL Identity Management] | [!UICONTROL 查看身份命名空间] | 对身份命名空间的只读访问。 |

  有关Experience Platform权限的详细信息，请参阅[管理产品配置文件的权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/ui/permissions)。


* 如果Adobe Journey Optimizer与存在AJO连接的CJA集成，则还必须添加历程权限才能访问连接：

  | 类别 | 权限 | 描述 |
  |---|---|---|
  | [!UICONTROL 历程] | [!UICONTROL 查看历程事件、数据源和操作] | 对历程事件、历程自定义操作和历程数据源的只读访问权限。 |
  | [!UICONTROL 历程] | [!UICONTROL 管理历程事件、数据源和操作] | 读取、创建、编辑和删除事件、源或操作。 |
  | [!UICONTROL 历程] | [!UICONTROL 查看历程] | 对历程的只读访问权限。 |
  | [!UICONTROL 历程] | [!UICONTROL 管理历程] | 读取、创建、编辑和删除历程。 |

* 将数据集导出到[目标](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/destinations/ui/activate/export-datasets)

  要执行此任务，用户必须是提供以下权限的&#x200B;**Experience Platform产品配置文件**&#x200B;的一部分：

  | 类别 | 权限 | 描述 |
  |---|---|---|
  | [!UICONTROL 目标] | [!UICONTROL 管理目标] | 读取、创建和删除目标连接和目标帐户的权限。 |
  | [!UICONTROL 目标] | [!UICONTROL 激活目标] | 允许用户将区段激活到现有目标。 在激活工作流中启用映射步骤。 此权限还要求向想要将数据激活到目标的用户授予“查看目标”权限。 |

  有关Experience Platform权限的详细信息，请参阅[管理产品配置文件的权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/ui/permissions)。

* 使用[BI扩展](../data-views/bi-extension.md)

  对于要使用BI扩展的用户，请使用产品管理员

   * 必须确保用户的Experience Platform权限包括具有查询服务资源的角色，该资源具有“管理查询”和“管理查询服务集成”选项。 有关Experience Platform权限的详细信息，请参阅[管理产品配置文件的权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/ui/permissions)。

     | 类别 | 权限 | 描述 |
     |---|---|---| 
     | [!UICONTROL 查询服务] | [!UICONTROL 管理查询] | 访问Platform数据的读取、创建、编辑和删除结构化SQL查询。 |
     | [!UICONTROL 查询服务] | [!UICONTROL 管理查询服务集成] | 访问创建、更新和删除未过期的凭据以访问查询服务。 |

   * 必须确保用户具有适当的Customer Journey Analytics权限：
      * 相关数据视图的访问权限。 在[!UICONTROL 用户级访问]中查看[数据视图](#user-level-access)。
      * 访问Customer Journey Analytics BI扩展的权限。 在[!UICONTROL 用户级访问]中查看[数据视图工具](#user-level-access)。

### 产品配置文件管理员角色

产品配置文件是一组权限。产品管理员可创建产品配置文件，并可分配产品配置文件管理员以管理一个或多个产品配置文件。 然后，产品配置文件管理员可以：

* 管理分配的产品配置文件。 例如，添加或删除用户或用户组，以及修改产品配置文件的权限。

* 在Customer Journey Analytics中，编辑作为已分配产品配置文件一部分的数据视图。 产品配置文件管理员无法创建新数据视图。

### 用户级别访问

下表概述了您可以为相关用户配置的各种Customer Journey Analytics功能的主要访问权限。 您可以通过产品配置文件管理不同级别的用户访问权限。 产品配置文件将组合大量权限，然后您可以将这些权限分配给单个用户或用户组。

**[!UICONTROL 权限]**&#x200B;选项卡是[Admin Console](https://adminconsole.adobe.com/enterprise/)中每个产品配置文件的一部分。

![Admin Console 权限](assets/permissions.png)

| 类别 | 权限 | 描述 |
| --- | --- | ---|
| [!UICONTROL 数据视图] | *数据视图名称* | 如果您将&#x200B;**[!UICONTROL 自动包含]**&#x200B;切换到&#x200B;**[!UICONTROL 开启]**，则属于此产品配置文件的用户可以查看所有现有和新创建的数据视图。如果此设置被设置为&#x200B;**[!UICONTROL 关闭]**，则可以选择用户有权访问的特定数据视图。 |
| [!UICONTROL 报告工具] | [!UICONTROL Analysis Workspace 访问权限] | 允许用户访问[Analysis Workspace](/help/analysis-workspace/home.md)。 |
| [!UICONTROL 报告工具] | [!UICONTROL 引导式分析访问] | 允许用户访问[引导分析](/help/guided-analysis/overview.md)。 |
| [!UICONTROL 报告工具] | [!UICONTROL 计算量度创建] | 允许用户创建[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。 用户只能标记、共享、删除、重命名、批准和取消批准其创建的计算指标或与他们共享的计算指标。 |
| [!UICONTROL 报告工具] | [!UICONTROL 区段创建] | 允许用户创建[区段](/help/components/segments/seg-overview.md)。 用户只能标记、共享、删除、重命名、批准和取消批准他们创建的区段或与他们共享的区段。 |
| [!UICONTROL 报告工具] | [!UICONTROL Labs 访问权限] | 允许用户访问Customer Journey Analytics中的[Labs](/help/labs/labs.md)选项卡。 |
| [!UICONTROL 报告工具] | [!UICONTROL 创建注释] | 允许用户创建[注释](/help/components/annotations/overview.md)。 用户只能标记、共享、删除和重命名他们创建的注释或与他们共享的注释。 |
| [!UICONTROL 报告工具] | [!UICONTROL 受众视图] | 允许用户查看[受众](/help/components/audiences/audiences-overview.md)。 |
| [!UICONTROL 报告工具] | [!UICONTROL 受众创建] | 允许用户创建[受众](/help/components/audiences/audiences-overview.md)。 |
| [!UICONTROL 报告工具] | [!UICONTROL 审核日志访问] | 强制对[API](https://developer.adobe.com/cja-apis/docs/endpoints/auditlogs/)和审核日志UI进行权限检查。 |
| [!UICONTROL 报告工具] | [!UICONTROL 与任何人共享项目链接] | 允许用户[与任何人共享项目。](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/curate-share/share-projects) |
| [!UICONTROL 报告工具] | [!UICONTROL 预测] | 允许用户访问Analysis Workspace中的[Forecasting](../analysis-workspace/c-forecast/forecasting.md)功能 |
| [!UICONTROL 报告工具] | [!UICONTROL AI 助手：产品知识] | 允许用户访问[AI助手](../ai-assistant.md)以了解产品知识。 |
| [!UICONTROL 报告工具] | [!UICONTROL 智能题注] | 允许用户访问[智能字幕](/help/analysis-workspace/visualizations/intelligent-captions.md)。 |
| [!UICONTROL 数据视图工具] | [!UICONTROL 完全表导出] | 允许用户[将全部表导出到云](/help/analysis-workspace/export/export-cloud.md)。 |
| [!UICONTROL 数据视图工具] | [!UICONTROL CJA BI扩展] | 允许用户使用[BI扩展](../data-views/bi-extension.md)。 |

{style="table-layout:auto"}

## 工作区项目策划

可以在工作区报告级别使用另一级别的访问控制。您可以限制某些用户对特定组件的访问。有关如何在工作区项目级别限制组件（维度、量度、区段、日期范围）以及如何将管理与数据视图绑定在一起的更多信息，请参阅[管理项目](/help/analysis-workspace/curate-share/curate.md)。

## 授予对单个量度或维度的访问权限

您不能像在传统的 Adobe Analytics 中那样，在 Customer Journey Analytics 中授予或拒绝针对单个量度或维度的权限。 量度和维度可以在[数据视图](/help/data-views/data-views.md)中修改，因此可能会在Customer Journey Analytics中出现更改。 更改它们也会追溯性地更改报告。

## 用例

这里有几个用例说明了如何在现实场景中使用访问控制。

### 第三方访问

您可以向贵公司合作的第三方的团队负责人提供产品配置文件管理访问权限。 此管理员可以将公司团队中的用户添加到此产品配置文件。 此产品配置文件管理员可以授予访问特定数据视图的权限，并将第三方中的其他用户添加到此产品配置文件。 产品配置文件管理员可以修改数据视图，以满足第三方团队的要求。

### 行级访问控制

您希望向用户授予仅从一天开始访问数据的权限。 以下是如何限制对这些特定行的访问：

1. 在特定数据视图的[!UICONTROL 设置]中创建区段，其中[!UICONTROL 天]等于您希望他们访问数据的日期。 有关详细信息，请参阅[创建数据视图](/help/data-views/create-dataview.md#settings-filters)。
1. 保存数据视图，这会将区段应用于基础连接中数据集的数据部分。 任何不符合区段定义的行都会自动从数据视图中排除，并且在使用此数据视图时不可用于Analysis Workspace。
1. 在Admin Console中创建新的[产品配置文件](#product-profile-admin-role)，将用户添加到产品配置文件，并仅将此特定数据视图添加到产品配置文件。

### 值级访问控制

有权访问数据视图的用户只能使用管理员在此数据视图中包含的量度和维度。 管理员可以在数据视图中使用[包含/排除功能](/help/data-views/component-settings/include-exclude-values.md)或[值分段](../data-views/component-settings/value-bucketing.md)组件设置从数据视图中排除或聚合某些维度值。

例如：您在数据视图中创建了一个名为&#x200B;*高血压*&#x200B;的量度，该量度来自包含数据集中的个别患者数据的组件。 您使用值分段来仅提供对分段值的访问权限，以便数据的用户看不到各个患者数据。


