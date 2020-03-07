---
title: 客户旅程分析概述
description: 客户旅程分析简介
translation-type: tm+mt
source-git-commit: 7afdf490d0a63b1286a1a646a487ee96d4b6ed8f

---


# 客户旅程分析概述

客户旅程分析是一项分析功能，可让您将Analysis Workspace的强大功能与Adobe Experience Platform中的数据结合使用。 它可以细分、筛选、查询和可视化数据的年份价值，并与平台保存各种数据架构和类型的能力相结合。 使用体 **验数据模型(XDM)**，数据可以统一地表示和组织，随时可以进行组合和探索。 **Experience Query Services允许您使用SQL兼容工具和框架来查询和处理所有数据。**

## 将CJA与Analysis Workspace进行比较

客户旅程分析通过提供易于使用的跨渠道功能并消除Adobe Analytics先前版本中的限制，扩展了Analytics的范围。 一些显着的改进包括：

* **无限变量和事件**:eVar、prop和事件的概念已不复存在。 数据主要侧重于维度和指标。 数据集可以具有无限数量的唯一维度和指标。
* **无限制的独立**:Adobe Experience Platform不受任何独特限制的限制，如传统报表包中的500k唯一值。
* **更改历史数据**:使用Adobe Experience Platform，可以删除或更正数据。
* **跨报表包数据**:可以在平台中组合来自多个数据集的现有实现。

客户旅程分析的初始版本包括Analysis Workspace中包含的许多功能。 有关完整列表，请参阅客 [户旅程分析功能支持](cja-aa.md)。

### 术语更新

CJA中的几项功能已更名为符合行业标准。 一些更新的名称包括：

* 区段现在称为“过滤器”
* 虚拟报表包现在称为“查看”
* 分类现在称为“查找数据集”
* 客户属性现在称为“配置文件数据集”
* 命中容器现在称为“事件”容器
* 访问容器现在称为“会话”容器
* 访客容器现在称为“人员”容器

## 主要用例

通过客户旅程分析，您可以：

* **在旅程情境中查看客户**:您可以按顺序查看和分析跨多个渠道的数据。 来自呼叫中心、POS系统和在线属性的数据可以合并到单个报告视图中。
* **让所有人都能了解**:实现数据访问大众化，让更多人利用数据得出的洞察做出业务决策。 组织中对客户体验的任何方面负责的任何人都可以基于更完整的数据更快地做出真正的决策。
* **为您的分析师利用数据科学的力量**:客户旅程分析让普通人能够利用数据科学挖掘深层洞察和分析。
* **使用专门报告可视化数据集并与之交互**:Workspace可以使用Adobe Experience Platform中符合某些基本规则的任何数据集。
* **查看非Web数据**:工作区不再局限于“点击”或“事件”的严格定义。 自定义架构允许完全控制数据和定义。
* **对数据操作进行更大的控制**:更改您上传的数据，创建新数据集，并将其导入Workspace。 Adobe Experience Platform通过Experience Cloud查询服务提供查询、提取、转换和加载工具。

## 先决条件

在开始使用客户旅程分析之前，必须先完成以下步骤：

* 您的组织与Adobe Analytics（针对Select、Prime或Ultimate）签订了有效合同，并安装了Customer Journey Analytics Add-on。 如果您不确定您拥有的合同类型，或不确定您是否拥有CJA加载项，请与贵组织的客户经理联系。
* 您的组织已针对Adobe Experience Platform进行配置。

## 用户访问权限

要创建连接、添加数据集等，您需要在 [Admin Console中拥有以下权限](https://adminconsole.adobe.com/enterprise/):

* 要管理Experience Platform中的数据集，您必须是为您提供“管理数据集”权限的平台产品配置文件的一部分。 有关详细信息，请参 [阅Adobe Experience Platform中的访问控制](https://www.adobe.io/apis/experienceplatform/home/permissions-and-sandboxes/permissions-and-sandboxes.html#!api-specification/markdown/narrative/technical_overview/access-control/access-control-overview.md)。
* 要创建与平台数据集的连接，您必须是平台产品配置文件的一部分，该配置文件赋予您以下权限：
   * 查看架构
   * 查看数据集
   * 管理标识命名空间
   * 查看沙箱
* 要访问客户旅程分析或建立连接，您还需要添加到 [Admin Console中的客户旅程分析产品配置](https://adminconsole.adobe.com/enterprise/)。

## 构建在Adobe Experience Platform上的其他功能

客户旅程分析是众多依赖Adobe Experience Platform的功能之一。 还构建在平台上的其他几项功能使您能够充分利用数据。

Adobe Experience Platform可让您集中和标准化来自任何系统的客户数据和内容，并应用数据科学和机器学习来改进个性化体验的设计和交付。 平台中的客户数据作为数据集进行存储，数据集由架构和数据批量组成。 有关该平台的更多详细信息，请参 [阅Adobe Experience Platform架构概述](https://www.adobe.io/apis/experienceplatform/home/overview.html)。

从数据摄取到直接SQL访问，Experience Platform的几个组件是客户旅程分析的核心，并与之一起采取行动：

* [查询服务](https://www.adobe.io/apis/experienceplatform/home/query-service/sql-reference.html):使用标准SQL从Adobe Experience Platform检索数据，如Adobe解决方案数据、客户第一方数据或任何其他平台数据。 它是一个无服务器工具，允许您加入任何数据集并将查询结果捕获为新数据集以用于报告、Data Science Workspace或引入Profile Service中。 您可以使用查询服务来构建数据分析生态系统，从而创建消费者在不同互动渠道中的图景。 这些渠道可能包括销售点系统、Web、移动、CRM系统等。
* [实时客户档案](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md):
* [标识服务](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/identity_services_architectural_overview/identity_services_architectural_overview.md):
* [“开发人员](https://www.adobe.io/apis/experienceplatform/home/data-science-workspace.html) ”选项中的Data Science Workspace:您可以使用Adobe Experience Platform中预建的人工智能(AI)和机器学习模型来影响客户旅程的各个点。 通过发掘隐藏的洞察，您可以在整个客户旅程中做出更好的预测、建议最佳的后续步骤或自动处理繁琐的流程。
