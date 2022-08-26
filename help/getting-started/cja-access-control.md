---
title: CJA 访问控制
description: 了解在CJA中实施访问控制的方法。
solution: Customer Journey Analytics
feature: CJA Basics
exl-id: c258fa39-c0b6-45a1-8547-79516c15a215
mini-toc-levels: 3
source-git-commit: 669b8d6e0c8b8741edf82a83fead6b2030a57d40
workflow-type: tm+mt
source-wordcount: '913'
ht-degree: 17%

---

# CJA 访问控制

Customer Journey Analytics(CJA)受三个访问级别或三个角色的约束：产品管理员角色、产品配置文件管理员角色和用户级别访问权限。 本主题将更详细地介绍这些角色。

## 产品管理员角色

产品管理员有权在CJA中完成任何必需的任务。 您必须作为产品管理员添加到 **Customer Journey Analytics产品配置文件** 在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 在 [!UICONTROL Customer Journey Analytics] > [!UICONTROL 管理员] 选项卡> [!UICONTROL 添加管理员]. 产品管理员享有以下权限：

* 创建/更新/删除连接或数据视图
* 更新/删除其他用户创建的项目、过滤器、计算量度、受众、批注或过滤器
* 将工作区项目共享给所有用户

仅作为Customer Journey Analytics中的产品管理员，还不足以创建、更新或删除 [连接](/help/connections/overview.md). 要创建与 Experience Platform 数据集的连接，您还需要取得 Experience Platform 权限。具体而言，您必须属于授予您以下权限的 **Experience Platform 产品用户档案**：

* 数据建模：查看架构，管理架构
* 数据管理：查看数据集，管理数据集
* 数据摄取：管理源
* 查看标识命名空间

有关 Experience Platform 权限的更多信息，请参阅 [Adobe Experience Platform 中的访问控制](https://experienceleague.adobe.com/docs/experience-platform/access-control/home.html)。

## 产品配置文件管理员角色

产品配置文件是一组权限。 产品配置文件管理员可以

* 创建和管理单个产品配置文件，例如添加新用户或管理用户组及其关联的产品配置文件。

* 在CJA中，编辑属于他们管理的产品配置文件一部分的数据视图。 无法创建新的数据视图。

## 用户级别访问

Customer Journey Analytics中的用户无法创建、编辑或查看数据视图或连接。 用户可以在Admin Console中创建具有特殊权限的过滤器、项目、受众和计算量度。

## 工作区项目策划

工作区报表级别可以使用另一级别的访问控制。 您可以限制特定用户对特定组件的访问权限。 有关如何在工作区项目级别限制组件（维度、量度、区段、日期范围）以及管理与数据视图关联的更多信息，请参阅 [组织项目](/help/analysis-workspace/curate-share/curate.md).

## 授予对单个量度或维度的访问权限

您不能像在传统的 Adobe Analytics 中那样，在 Customer Journey Analytics 中授予或拒绝对单个量度或维度的权限。 量度和维度可在 [数据视图](/help/data-views/data-views.md) 因此在CJA中可能会发生更改。 更改它们还会以追溯方式更改报表。

## 用例

以下几个用例说明了如何在现实场景中使用访问控制。

### 第三方访问

贵公司与之合作的第三方具有可以成为产品用户档案管理员的团队负责人。 然后，此管理员可以将其团队中的用户添加到此产品配置文件。 此管理员可以授予对特定数据视图的访问权限，并将其他用户添加到此产品配置文件。 他们还可以修改他们拥有控制权的数据视图，以满足其团队的需求。

### 行级访问控制

假设您希望仅允许用户从一天内访问数据。 下面是如何限制对这些特定行的访问：

1. 在CJA中创建过滤器，其中 **[!UICONTROL 日]** 等于您希望他们有权访问数据的日期。
1. 在 [!UICONTROL 数据视图] > [!UICONTROL 设置]，将该过滤器添加到数据视图。
1. 保存数据视图，然后会自动将过滤器应用到数据集。 现在，任何不符合过滤器定义的行都会自动从编辑的数据视图中排除。
1. 在Admin Console中创建新的产品配置文件，向其中添加用户并限制其对此数据视图的访问权限。

### 值级访问控制

有权访问数据视图的用户只能使用管理员在此数据视图中包含的量度和维度。 管理员可以使用 [包含/排除功能](/help/data-views/component-settings/include-exclude-values.md) 例如，在数据视图中，从数据视图中排除某些维度值。

以下是一个与医疗保健相关的示例：假设您在数据视图中从包含此数据的数据集创建一个名为“高血压”的量度。 事实上，它是一个量度，它可以让您查看此量度的总值，但不能查看属于此量度的患者。

## CJA权限

的 **[!UICONTROL 权限]** 选项卡是 [Admin Console](https://adminconsole.adobe.com/enterprise/). 您可以将用户添加到特定的产品配置文件。 然后，您可以为特定数据视图分配权限，并指定产品配置文件中的用户具有哪些权限。 以下是特定于CJA的权限：

![管理控制台权限](assets/permissions.png)

| 权限 | 定义 |
| --- | --- |
| **[!UICONTROL 数据视图]** | 如果切换 **[!UICONTROL 自动包含]** to **[!UICONTROL 开]**，则属于此产品配置文件的用户可以查看所有现有和新创建的数据视图。 如果此设置设置为 **[!UICONTROL 关闭]**，则可以选择用户有权访问的特定数据视图。 |
| **[!UICONTROL 报表工具]**: |  |
| **[!UICONTROL 审核日志访问]** | 目前， [审核日志](https://adobe.io/cja-apis/docs/endpoints/auditlogs/) 只能通过API使用。 此权限适用于正在开发的未来UI。 |
| **[!UICONTROL 报告使用情况管理员]** | 允许用户查看和删除其公司中运行的任何报表。 （报表使用情况功能尚未发布。） |
| **[!UICONTROL 报告使用情况视图]** | 允许用户查看所有并发报表请求。 （报表使用情况功能尚未发布。） |
| **[!UICONTROL 计算量度创建]** | 允许用户创建 [计算量度](/help/components/calc-metrics/calc-metr-overview.md). |
| **[!UICONTROL 过滤器创建]** | 允许用户创建 [过滤器](/help/components/filters/filters-overview.md). |
| **[!UICONTROL Labs 访问权限]** | 允许用户访问 [Labs](/help/labs/labs.md) 选项卡。 |
| **[!UICONTROL 创建注释]** | 允许用户创建 [批注](/help/components/annotations/overview.md). |
| **[!UICONTROL 受众创建]** | 允许用户创建 [受众](/help/components/audiences/audiences-overview.md). |
| **[!UICONTROL 受众视图]** | 允许用户查看 [受众](/help/components/audiences/audiences-overview.md). |
