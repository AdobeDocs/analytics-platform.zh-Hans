---
title: Customer Journey Analytics 概述
description: 了解如何通过 Customer Journey Analytics 来使用 Analysis Workspace 处理来自 Experience Platform 的数据。
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
translation-type: tm+mt
source-git-commit: 76260b7362396c76942dadab599607cd038ed651
workflow-type: tm+mt
source-wordcount: '1217'
ht-degree: 94%

---

# Customer Journey Analytics 概述

Customer Journey Analytics 是一项 Analytics 功能，让您可以运用 Analysis Workspace 的强大功能处理来自 Adobe Experience Platform 的数据。它可以划分、过滤、查询和可视化数年积累的有价值的数据，并结合 Platform 的功能来保存各种数据架构和类型。使用&#x200B;**体验数据模型 (XDM)**，可以采用统一的方式来表示和组织数据，以便进行数据合并和分析。**Experience 查询**&#x200B;允许您使用 SQL 兼容工具和框架来查询和处理所有数据。

## 比较 CJA 与传统 Adobe Analytics

Customer Journey Analytics 通过提供易于使用的跨渠道分析功能和消除 Adobe Analytics 先前版本中的限制，扩展了 Analytics 的适用范围。一些显着改进的功能包括：

* **无限量的变量和事件**：eVar、prop 和事件的概念已不复存在。数据主要侧重于维度和量度。数据集可以拥有无限量的唯一维度和量度。
* **无限制的唯一值**:Adobe Experience Platform不受任何独特限制的限制。
* **更改历史数据**：使用 Adobe Experience Platform，可以删除或更正数据。
* **跨报表包数据**：可以在 Platform 中组合来自多个数据集的现有实施。

Customer Journey Analytics 的初始版本包括 Analysis Workspace 中的许多功能。有关完整列表，请参阅 [Customer Journey Analytics 功能支持](cja-aa.md)。

## 比较 CJA 与 Cross-Device Analytics

[Cross-Device Analytics ](https://docs.adobe.com/content/help/zh-Hans/analytics/components/cda/cda-home.html)与 Adobe Experience Platform Identity 服务集成，利用协作图形或专用图形来识别数字设备如何映射到人员。它适用于 Adobe Analytics Ultimate 客户。

另一方面，CJA 与 Adobe Experience Platform 数据集集成，并且支持在 Analysis Workspace 中进行跨渠道分析。尽管 CJA 尚未与协作或专用身份图形集成，但您可以“自带 ID”将数据集合在一起，这些数据集不仅包含数字数据，而且包含线上和线下接触点。下文将详细介绍使用 CJA 的先决条件。

## 主要用例

通过 Customer Journey Analytics，您可以：

* **在历程情境中查看客户**：您可以跨多个渠道按顺序查看和分析数据。将来自呼叫中心、POS 系统以及在线属性的数据合并到单个报表视图。
* **为所有人提供洞察**：实现数据访问大众化，让更多人利用数据衍生的洞察做出业务决策。组织中任何负责客户体验某一方面的人员，都可以基于更完整全面的数据，更快地做出真正明智的决策。
* **助力分析师充分利用数据科学的强大力量**：Customer Journey Analytics 让普通人能够运用数据科学获得深入的分析和洞察信息。
* **使用临时报表实现数据集可视化并进行交互**：工作区可以使用 Adobe Experience Platform 中符合某些基本规则的任何数据集。
* **查看非 Web 数据**：工作区不再局限于“点击”或“事件”的严格定义。自定义架构允许完全控制数据和定义。
* **更好地控制数据操作**：更改您上传的数据，创建新数据集，并将这些数据导入工作区。Adobe Experience Platform 通过 Experience Cloud 查询服务来提供查询、提取、转换和加载工具。

## 先决条件

在开始使用 Customer Journey Analytics 之前，必须满足以下先决条件：

* 您的组织与 Adobe 签订了一份 Analytics for Select、Prime 或 Ultimate 的有效合同，其中包含 Customer Journey Analytics 附加产品。如果您不确定您拥有哪种合同类型，或不确定您是否拥有 CJA 附加产品，请联系贵公司的客户经理。
* 您的组织已配置 Adobe Experience Platform。

## 管理员访问权限

要创建连接、添加数据集等，您需要在 [Admin Console](https://adminconsole.adobe.com/enterprise/) 中拥有以下权限：

* 要访问Customer Journey Analytics或建立连接，您需要作为管理员添加到[Admin Console](https://adminconsole.adobe.com/enterprise/)中的&#x200B;**Customer Journey Analytics产品**。 产品管理员享有以下权限：
   * 创建/更新/删除连接或数据视图
   * 更新/删除其他用户创建的项目、过滤器、计算量度或过滤器
   * 将工作区项目共享给所有用户
* 仅作为 Customer Journey Analytics 的产品管理员，并不足以创建、更新或删除连接。要创建与 Experience Platform 数据集的连接，您还需要取得 Experience Platform 权限。具体而言，您必须属于授予您以下权限的 **Experience Platform 产品用户档案**：
   * 查看架构
   * 管理架构
   * 查看身份命名空间
   * 查看数据集

有关 Experience Platform 权限的更多信息，请参阅 [Adobe Experience Platform 中的访问控制](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md)。

### 用户访问

Customer Journey Analytics 中的非产品管理员（用户）无法查看数据视图或连接，但可以创建过滤器、项目和计算量度。

## 术语更新

与传统的 Adobe Analytics 相比，为了符合行业标准，CJA 中的一些功能已重新命名。一些更新的术语包括：

* “区段”现在称为“过滤器”。
* 虚拟报表包现在称为“数据视图”。
* “分类”现在称为“查找数据集”。
* “客户属性”现在称为“用户档案数据集”。
* “点击”容器现在称为“事件”容器。
* “访问”容器现在称为“会话”容器。
* “访客”容器现在称为“人员”容器。

## 基于 Adobe Experience Platform 构建的其他功能

Customer Journey Analytics 是依赖于 Adobe Experience Platform 的众多功能之一。此外，基于 Experience Platform 构建的几项其他功能也可让您充分利用数据。

Adobe Experience Platform 让您可以实现源自任何系统的客户数据和内容的集中化和标准化，并应用数据科学和机器学习来优化个性化体验的设计和交付。Platform 中的客户数据将作为数据集存储，数据集由一个架构和批量数据组成。有关 Platform 的更多详细信息，请参阅 [Adobe Experience Platform 体系架构概述](https://www.adobe.io/apis/experienceplatform/home/overview.html)。

从数据摄取到直接 SQL 访问，Experience Platform 的多个组件在 Customer Journey Analytics 中发挥着重要作用，并且可与之搭配使用：

* [查询服务](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html)：使用标准 SQL 从 Adobe Experience Platform 检索数据，例如，Adobe 解决方案数据、客户第一方数据，或任何其他 Platform 数据。它是一个无服务器工具，让您可以加入任何数据集，并作为新数据集获取查询结果，以用于报表、Data Science Workspace，或将数据摄取到用户档案服务。您可以使用“查询服务”构建数据分析生态系统，进而创建消费者在各种交互渠道中的全景图。这些渠道可能包括销售点系统、Web、移动设备、CRM 系统等。
* [实时客户用户档案](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md)：
* [Identity 服务](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md)：
* “开发人员”选项中的 [Data Science Workspace](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html)：您可以使用 Adobe Experience Platform 中预建的人工智能 (AI) 和机器学习模型来影响客户历程的各个接触点。通过揭示暗藏的洞察信息，您可以在整个客户历程中做出更好的预测、提出最佳的后续步骤建议，或自动处理繁琐的流程。
