---
title: Customer Journey Analytics 概述
description: 了解如何通过 Customer Journey Analytics 来使用 Analysis Workspace 处理来自 Experience Platform 的数据。
exl-id: f4f692c9-5951-4fa2-8e9f-5eeff0f79d10
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
source-git-commit: b14bc43a0cdf4901c5df171a116943beb2124991
workflow-type: ht
source-wordcount: '985'
ht-degree: 100%

---

# Customer Journey Analytics 概述

Customer Journey Analytics 是 Adobe 推出的新一代 Analytics 解决方案，可让您运用 Analysis Workspace 的强大功能处理来自 Adobe Experience Platform 的数据。它可以细分、分段、查询以及将多年的数据可视化显示，并结合 Platform 的功能来保存各种数据架构和类型。使用&#x200B;**体验数据模型 (XDM)**，可以采用统一的方式来表示和组织数据，以便进行数据合并和分析。通过 **Adobe Experience Platform Query Service**，可使用与 SQL 兼容的工具和框架查询和操作所有数据。

Customer Journey Analytics 架构大致如下所示：

![在此部分中解释的 Customer Journey Analytics 架构](assets/cja-architecture.png)


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Customer Journey Analytics：适用于 Experience Business 的 Analytics](https://video.tv.adobe.com/v/36211/?quality=12&learn=on&captions=chi_hans){target="_blank"} 以获取有关 Customer Journey Analytics 的介绍视频。

>[!ENDSHADEBOX]


## 比较 Customer Journey Analytics 和传统 Adobe Analytics

Customer Journey Analytics 通过提供易于使用的跨渠道功能和消除 Adobe Analytics 早期版本中的限制，扩展了 Adobe Analytics 的范围。一些显著改进的功能包括：

* **无限量的变量和事件**：eVar、prop 和事件的概念已不复存在。数据主要侧重于维度和量度。数据集可以有无限数量的唯一维度和量度。
* **无限唯一值**：Adobe Experience Platform 不受任何特有限制的约束。
* **更改历史数据**：使用 Adobe Experience Platform，可以删除或更正数据。
* **跨报告包数据**：可以在 Platform 中组合来自多个数据集的现有实施。

>[!TIP]
>
>如果您一直在使用 Adobe Analytics，并希望在 Customer Journey Analytics 中使用您的 Adobe Analytics 数据，请参阅[数据摄取](../data-ingestion/data-ingestion.md)部分中包含的[从传统 Adobe Analytics 中摄取和使用数据](../data-ingestion/analytics.md)快速入门指南。

Customer Journey Analytics 的初始版本包括 Adobe Analytics 中的许多功能。有关完整列表，请参阅 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。

## 主要用例

通过 Customer Journey Analytics，您可以：

* **在历程情境中查看客户**：您可以跨多个渠道按顺序查看和分析数据。将来自呼叫中心、POS 系统以及在线属性的数据合并到单个报告视图。
* **为所有人提供洞察信息**：实现数据访问大众化，让更多人利用数据衍生的洞察信息做出业务决策。组织中任何负责客户体验某一方面的人员，都可以基于更完整全面的数据，更快地做出真正明智的决策。
* **助力分析师充分利用数据科学的强大力量**：Customer Journey Analytics 让普通人能够运用数据科学获得深入的分析和洞察信息。
* **使用按需报告实现数据集可视化并进行交互**：工作区可以使用 Adobe Experience Platform 中符合某些基本规则的任何数据集。
* **查看非 Web 数据**：工作区不再局限于“点击”或“事件”的严格定义。自定义架构允许完全控制数据和定义。
* **对数据操作加强控制**：更改已上载的数据，创建数据集，并将其导入工作区。Adobe Experience Platform 通过 Experience Platform Query Service 提供查询、提取、转换和加载工具。

## 前提条件

在开始使用 Customer Journey Analytics 之前，必须满足以下前提条件：

* 您的组织与 Adobe 签订了一份 Analytics for Select、Prime 或 Ultimate 的有效合同，其中包含 Customer Journey Analytics 附加产品。如果您不确定您拥有哪种合同类型，或不确定您是否拥有 Customer Journey Analytics 附加产品，请联系您的 Adobe 帐户团队。
* 您的组织已配置 Adobe Experience Platform。
* 您还可以将 Customer Journey Analytics 作为独立产品购买，而无需 Adobe Analytics。

## 访问控制

请参阅[访问控制](/help/technotes/access-control.md)。

## 术语更新

与传统的 Adobe Analytics 相比，为了符合行业标准，Customer Journey Analytics 中的一些功能已重新命名。一些更新的术语包括：

* 虚拟报告包现在称为“数据视图”。
* “分类”现在称为“查找数据集”。
* “客户属性”现在称为“配置文件数据集”。
* “点击”容器现在称为“事件”容器。
* “访问”容器现在称为“会话”容器。
* “访客”容器现在称为“人员”容器。

## 基于 Adobe Experience Platform 构建的其他功能

Customer Journey Analytics 是依赖于 Adobe Experience Platform 的众多功能之一。此外，基于 Experience Platform 构建的几项其他功能也可让您充分利用数据。

Adobe Experience Platform 让您可以实现源自任何系统的客户数据和内容的集中化和标准化，并应用数据科学和机器学习来优化个性化体验的设计和交付。Platform 中的客户数据将作为数据集存储，数据集由一个架构和批量数据组成。有关 Platform 的更多详细信息，请参阅 [Adobe Experience Platform 体系架构概述](https://experienceleague.adobe.com/docs/platform-learn/tutorials/intro-to-platform/basic-architecture.html?lang=zh-Hans)。

从数据摄取到 SQL 直接访问，Experience Platform 的多个组件在 Customer Journey Analytics 中发挥着极为重要的作用，并且与之相辅相成：

* [Experience Platform Query Service](https://experienceleague.adobe.com/docs/experience-platform/query/home.html?lang=zh-Hans)：使用标准 SQL 从 Adobe Experience Platform 检索数据，如 Adobe 解决方案数据、客户第一方数据或任何其他 Platform 数据。它是一个无服务器工具，通过它可连接任何数据集，并将查询结果记录为新数据集，以供在报告中使用或摄取到配置文件服务。可使用 Experience Platform Query Service 构建数据分析生态系统，在使用者的各种交互渠道上为使用者画像。这些渠道可能包括销售点系统、Web、移动、CRM 系统等。
* [实时客户配置文件](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans)：
* [身份标识服务](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-hans)

## 视频

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [在 Customer Journey Analytics 中处理数据](https://video.tv.adobe.com/v/35911/?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取有关如何在 Customer Journey Analytics 中处理数据的介绍视频。

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [架构与集成](https://video.tv.adobe.com/v/330413/?quality=12&learn=on&captions=chi_hans){target="_blank"}以获取有关 Customer Journey Analytics 架构与集成的介绍视频。

>[!ENDSHADEBOX]

>[!MORELIKETHIS]
>
>* [面向分析师的 Adobe Customer Journey Analytics 速成课程](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/adobe-customer-journey-analytics-crash-course-for-analysts/ba-p/719261)
>* [优化您的思维方式和 Adobe Customer Journey Analytics 工作流程：适合任何规模组织的团队模型](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/optimizing-your-mindset-and-adobe-customer-journey-analytics/ba-p/721456)
>* [构建组织准备工作：以人为本的 Adobe Customer Journey Analytics 扩展指南](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/building-organizational-readiness-a-people-first-guide-to/ba-p/723273)
