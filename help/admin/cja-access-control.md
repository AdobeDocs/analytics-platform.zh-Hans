---
title: Customer Journey Analytics 访问控制
description: 了解在Customer Journey Analytics中实施访问控制的方法。
solution: Customer Journey Analytics
feature: Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
role: Admin
source-git-commit: 24d8d03867cf9619bbee1dd647b2a2a57a36492b
workflow-type: tm+mt
source-wordcount: '1047'
ht-degree: 63%

---

# Customer Journey Analytics 访问控制

Customer Journey Analytics由三个访问级别或三个角色管理：产品管理员角色、产品配置文件管理员角色和用户级别访问。 本主题将更详细地解释这些角色。

此外，我们还讨论了限制访问的更加细粒度化的方法，如工作区管理和行级以及值级访问控制。

## 产品管理员角色

默认情况下，分配了产品管理员角色的用户将获得在Customer Journey Analytics中执行大多数任务的必要权限。 但是，某些任务需要附加权限。

要将用户添加为产品管理员，请执行以下操作：

1. 转到 [Admin Console](https://adminconsole.adobe.com/enterprise/).

1. 选择 [!UICONTROL **Customer Journey Analytics**] > [!UICONTROL **管理员**] 选项卡> [!UICONTROL **添加管理员**].

   您添加的用户将获得 [产品管理员默认权限](#product-admin-default-permissions). 您还可以授予他们 [其他权限](#product-admin-additional-permissions) 如果需要。

### 产品管理员默认权限

产品管理员有权完成Customer Journey Analytics中的大多数任务。

默认情况下，产品管理员有权执行以下任务：

* 创建、更新和删除数据视图
* 更新和删除项目、过滤器、计算量度、受众、批注或其他用户创建的过滤器
* 将工作区项目共享给所有用户
* 在中管理报告活动 [报告活动管理器](/help/reporting-activity-manager/reporting-activity-overview.md)

### 产品管理员其他权限

除了在中作为产品管理员添加外， **Customer Journey Analytics产品配置文件** 在 [Admin Console](https://adminconsole.adobe.com/enterprise/)，则需要其他权限才能在Customer Journey Analytics中完成以下任务：

* 创建、更新和删除数据 [连接](/help/connections/overview.md)

  要执行此任务，用户必须属于 **Experience Platform产品配置文件** 提供了以下权限：
   * 数据建模：查看架构，管理架构
   * 数据管理：查看数据集，管理数据集
   * 数据摄取：管理源
   * 查看标识命名空间

     有关 Experience Platform 权限的更多信息，请参阅 [Adobe Experience Platform 中的访问控制](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=zh-Hans)。

* 从AEP目标导出数据集

  要执行此任务，用户还需要以下Experience Platform权限：
   * 管理目标
   * 激活目标

     有关Experience Platform目标权限的更多信息，请参阅 [目标概述](https://experienceleague.adobe.com/docs/experience-platform/destinations/home.html?lang=zh-Hans).

## 产品配置文件管理员角色

产品配置文件是一组权限。产品配置文件管理员可以

* 创建和管理单个产品配置文件，例如添加新用户或管理用户组及其关联的产品配置文件。

* 在Customer Journey Analytics中，编辑作为其管理的产品配置文件一部分的数据视图。 他们无法创建新的数据视图。

## 用户级别访问

Customer Journey Analytics 中的用户无法创建、编辑或查看数据视图或连接。用户可以在 Admin Console 中创建具有特殊权限的过滤器、项目、受众和计算量度。

## 工作区项目策划

可以在工作区报告级别使用另一级别的访问控制。您可以限制某些用户对特定组件的访问。有关如何在工作区项目级别限制组件（维度、量度、过滤器、日期范围）以及如何将管理与数据视图绑定在一起的更多信息，请参阅 [策划项目](/help/analysis-workspace/curate-share/curate.md).

## 授予对单个量度或维度的访问权限

您不能像在传统的 Adobe Analytics 中那样，在 Customer Journey Analytics 中授予或拒绝针对单个量度或维度的权限。 可以在以下位置修改量度和维度： [数据视图](/help/data-views/data-views.md) 因此，随时可能出现Customer Journey Analytics变化。 更改它们也会追溯性地更改报告。

## 用例

这里有几个用例说明了如何在现实场景中使用访问控制。

### 第三方访问

与您公司合作的第三方有一个团队负责人，该团队负责人可以成为产品配置文件管理员。然后，该管理员可以将其团队中的用户添加到此产品配置文件。此管理员可以授予访问特定数据视图的权限，并将其他用户添加到此产品配置文件。他们还可以修改自己具有控制权的数据视图，以满足团队的需要。

### 行级访问控制

假设您想让用户只访问一天的数据，以下是如何限制对这些特定行的访问：

1. 在Customer Journey Analytics中创建过滤器，其中 **[!UICONTROL 天]** 等于您希望他们访问数据的日期。
1. 在“[!UICONTROL 数据视图]”>“[!UICONTROL 设置]”中，将该过滤器添加到数据视图。
1. 保存数据视图，它会自动将过滤器应用于数据集。任何不符合过滤器定义的行现在将自动从编辑的数据视图中排除。
1. 在 Admin Console 中创建新的产品配置文件，将用户添加到其中，并限制他们对此数据视图的访问。

### 值级访问控制

有权访问数据视图的用户只能使用管理员在此数据视图中包含的量度和维度。管理员可以在数据视图中使用[包含/排除功能](/help/data-views/component-settings/include-exclude-values.md)来从数据视图中排除某些维度值。

这是与医疗保健相关的示例：假设您在数据视图中创建了一个名为“高血压”的量度，该量度来自包含该数据的数据集。由于这是一个量度，因此它可以让您看到该量度的总计价值，但不包括属于它的个体患者。

## Admin Console中的Customer Journey Analytics权限

**[!UICONTROL 权限]**&#x200B;选项卡是 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中每个产品配置文件的一部分。您可以将用户添加到特定的产品配置文件。然后将权限分配给特定的数据视图，并指定用户在产品配置文件中拥有的权限。以下是特定于Customer Journey Analytics的权限：

![Admin Console 权限](assets/permissions.png)

| 权限 | 定义 |
| --- | --- |
| **[!UICONTROL 数据视图]** | 如果您将&#x200B;**[!UICONTROL 自动包含]**&#x200B;切换到&#x200B;**[!UICONTROL 开启]**，则属于此产品配置文件的用户可以查看所有现有和新创建的数据视图。如果此设置被设置为&#x200B;**[!UICONTROL 关闭]**，则可以选择用户有权访问的特定数据视图。 |
| **[!UICONTROL 报告工具]**： |   |
| **[!UICONTROL 审核日志访问]** | 此权限将强制对 [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) 和审核日志 UI 进行权限检查。 |
| **[!UICONTROL 报告使用情况管理员]** | 允许用户查看和删除公司中运行的任何报告。 |
| **[!UICONTROL 报告使用情况视图]** | 允许用户查看所有并发报告请求。 |
| [!UICONTROL **完整表导出**] | 允许用户 [将整个表导出到云](/help/analysis-workspace/export/export-cloud.md). |
| **[!UICONTROL 计算量度创建]** | 允许用户创建[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。 |
| **[!UICONTROL 过滤器创建]** | 允许用户创建[过滤器](/help/components/filters/filters-overview.md)。 |
| **[!UICONTROL Labs 访问权限]** | 允许用户访问 [Labs](/help/labs/labs.md) 选项卡中的Customer Journey Analytics。 |
| **[!UICONTROL 创建注释]** | 允许用户创建[注释](/help/components/annotations/overview.md)。 |
| **[!UICONTROL 受众创建]** | 允许用户创建[受众](/help/components/audiences/audiences-overview.md)。 |
| **[!UICONTROL 受众视图]** | 允许用户查看[受众](/help/components/audiences/audiences-overview.md)。 |

{style="table-layout:auto"}
