---
title: Customer Journey Analytics 访问控制
description: 了解在 CJA 中实现访问控制的方法。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: 34ee7954329d7dc8520031a977bb83d6e1bf3d3d
workflow-type: ht
source-wordcount: '925'
ht-degree: 100%

---

# Customer Journey Analytics 访问控制

Customer Journey Analytics (CJA) 由三个访问级别或三个角色管理：产品管理员角色、产品配置文件管理员角色和用户级别访问。本主题将更详细地解释这些角色。

此外，我们还讨论了限制访问的更加细粒度化的方法，如工作区管理和行级以及值级访问控制。

## 产品管理员角色

产品管理员有权完成 CJA 内的任何必要任务。必须将您作为产品管理员的角色添加到“[!UICONTROL Customer Journey Analytics]”>“[!UICONTROL 管理员]选项卡”>“[!UICONTROL 添加管理员]”下 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中的&#x200B;**Customer Journey Analytics 产品配置文件**。产品管理员享有以下权限：

* 创建/更新/删除连接或数据视图
* 更新/删除项目、过滤器、计算量度、受众、批注或其他用户创建的过滤器
* 将工作区项目共享给所有用户

仅在 Customer Journey Analytics 中担任产品管理员不足以创建、更新或删除[连接](/help/connections/overview.md)。 要创建与 Experience Platform 数据集的连接，您还需要取得 Experience Platform 权限。具体而言，您必须属于授予您以下权限的 **Experience Platform 产品用户档案**：

* 数据建模：查看架构，管理架构
* 数据管理：查看数据集，管理数据集
* 数据摄取：管理源
* 查看标识命名空间

有关 Experience Platform 权限的更多信息，请参阅 [Adobe Experience Platform 中的访问控制](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html?lang=zh-Hans)。

## 产品配置文件管理员角色

产品配置文件是一组权限。产品配置文件管理员可以

* 创建和管理单个产品配置文件，例如添加新用户或管理用户组及其关联的产品配置文件。

* 在 CJA 中，编辑作为其管理的产品配置文件一部分的数据视图。他们无法创建新的数据视图。

## 用户级别访问

Customer Journey Analytics 中的用户无法创建、编辑或查看数据视图或连接。用户可以在 Admin Console 中创建具有特殊权限的过滤器、项目、受众和计算量度。

## 工作区项目策划

可以在工作区报告级别使用另一级别的访问控制。您可以限制某些用户对特定组件的访问。有关如何在工作区项目级别限制组件（维度、量度、区段、日期范围）以及如何将管理与数据视图绑定在一起的更多信息，请参阅[管理项目](/help/analysis-workspace/curate-share/curate.md)。

## 授予对单个量度或维度的访问权限

您不能像在传统的 Adobe Analytics 中那样，在 Customer Journey Analytics 中授予或拒绝针对单个量度或维度的权限。 量度和维度可以在[数据视图](/help/data-views/data-views.md)中修改，因此可能会在 CJA 中出现更改。更改它们也会追溯性地更改报告。

## 用例

这里有几个用例说明了如何在现实场景中使用访问控制。

### 第三方访问

与您公司合作的第三方有一个团队负责人，该团队负责人可以成为产品配置文件管理员。然后，该管理员可以将其团队中的用户添加到此产品配置文件。此管理员可以授予访问特定数据视图的权限，并将其他用户添加到此产品配置文件。他们还可以修改自己具有控制权的数据视图，以满足团队的需要。

### 行级访问控制

假设您想让用户只访问一天的数据，以下是如何限制对这些特定行的访问：

1. 在 CJA 中创建一个过滤器，其中&#x200B;**[!UICONTROL 天]**&#x200B;等于您希望他们访问数据的日期。
1. 在“[!UICONTROL 数据视图]”>“[!UICONTROL 设置]”中，将该过滤器添加到数据视图。
1. 保存数据视图，它会自动将过滤器应用于数据集。任何不符合过滤器定义的行现在将自动从编辑的数据视图中排除。
1. 在 Admin Console 中创建新的产品配置文件，将用户添加到其中，并限制他们对此数据视图的访问。

### 值级访问控制

有权访问数据视图的用户只能使用管理员在此数据视图中包含的量度和维度。管理员可以在数据视图中使用[包含/排除功能](/help/data-views/component-settings/include-exclude-values.md)来从数据视图中排除某些维度值。

这是与医疗保健相关的示例：假设您在数据视图中创建了一个名为“高血压”的量度，该量度来自包含该数据的数据集。由于这是一个量度，因此它可以让您看到该量度的总计价值，但不包括属于它的个体患者。

## Admin Console 中的 CJA 权限

**[!UICONTROL 权限]**&#x200B;选项卡是 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中每个产品配置文件的一部分。您可以将用户添加到特定的产品配置文件。然后将权限分配给特定的数据视图，并指定用户在产品配置文件中拥有的权限。以下是特定于 CJA 的权限：

![Admin Console 权限](assets/permissions.png)

| 权限 | 定义 |
| --- | --- |
| **[!UICONTROL 数据视图]** | 如果您将&#x200B;**[!UICONTROL 自动包含]**&#x200B;切换到&#x200B;**[!UICONTROL 开启]**，则属于此产品配置文件的用户可以查看所有现有和新创建的数据视图。如果此设置被设置为&#x200B;**[!UICONTROL 关闭]**，则可以选择用户有权访问的特定数据视图。 |
| **[!UICONTROL 报告工具]**： |  |
| **[!UICONTROL 审核日志访问]** | 此权限将强制对 [API](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) 和审核日志 UI 进行权限检查。 |
| **[!UICONTROL 报告使用情况管理员]** | 允许用户查看和删除公司中运行的任何报告。 |
| **[!UICONTROL 报告使用情况视图]** | 允许用户查看所有并发报告请求。 |
| **[!UICONTROL 计算量度创建]** | 允许用户创建[计算量度](/help/components/calc-metrics/calc-metr-overview.md)。 |
| **[!UICONTROL 过滤器创建]** | 允许用户创建[过滤器](/help/components/filters/filters-overview.md)。 |
| **[!UICONTROL Labs 访问权限]** | 允许用户访问 CJA 中的 [Labs](/help/labs/labs.md) 选项卡。 |
| **[!UICONTROL 创建注释]** | 允许用户创建[注释](/help/components/annotations/overview.md)。 |
| **[!UICONTROL 受众创建]** | 允许用户创建[受众](/help/components/audiences/audiences-overview.md)。 |
| **[!UICONTROL 受众视图]** | 允许用户查看[受众](/help/components/audiences/audiences-overview.md)。 |

{style=&quot;table-layout:auto&quot;}
