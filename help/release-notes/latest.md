---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 64a774d9151c40ea9eadb1fb80c07db168ac8667
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 66%

---

# 当前Customer Journey Analytics(CJA)发行说明（2023年4月）

**上次更新时间**：2023 年 4 月 12 日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 主要功能及更新

| 功能 | 描述 | [开始推出](/help/release-notes/releases.md) | [正式发布](/help/release-notes/releases.md) |
| ----------- | ---------- | ----- | --- |
| **Analytics 源连接器流式处理的行/列筛选** | Adobe Experience Platform 中的 Analytics 源连接器现在允许过滤 Analytics 数据，这些数据用于填充[实时客户配置文件](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans)中的配置文件。行级过滤有助于减少与配置文件关联的事件数。列级过滤有助于减少事件本身的丰富性，从而使您能够优化对配置文件权利的使用。此过滤仅适用于发送至实时客户配置文件和[标识服务](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hans)的数据。**过滤不会影响发送到数据湖以用于 Customer Journey Analytics** 等应用程序的数据。[了解详情](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans#filtering-for-profile) | 不适用 | 2023 年 3 月 29 日 |
| **Analysis Workspace 中的数据词典** | 数据词典可帮助用户和管理员跟踪并更好地了解其 CJA 环境中的组件（如维度、量度等）。[了解详情](/help/components/data-dictionary/data-dictionary-overview.md) | 2023 年 3 月 8 日 | 2023 年 3 月 29 日 |
| **共享项目链接（无需登录）** | <p>您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置CJA的人员共享。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link)</p> <p>默认情况下，此功能处于启用状态，系统管理员可以禁用此功能。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023年4月26日（仅限私人测试版访问） | 2023 年 6 月 |
| **Adobe产品分析 — 仅限私人测试版访问** | 2023年3月21日，Adobe宣布推出Adobe产品分析，这是一种与Customer Journey Analytics中的跨渠道数据和分析进行交互的新方法。 这些新功能使产品团队能够通过指导分析工作流程为其产品体验提供自助数据和洞&#x200B;察。 团队可以：<ul><li>了解用户参与度随时间变化的模式&#x200B;</li><li>分析用户群的增&#x200B;长</li><li>识别一系列步骤的摩擦区域&#x200B;</li><li>衡量功能发布的影响&#x200B;</li><li>探索有意义的客户群，以便在整个产品的终身历程中参与和培&#x200B;养</li><li>在Analysis Workspace中打开，以便与分析人员进行更深入的分析和协作，以及执行更多其他操&#x200B;作！</li></ul>如果您是CJA客户，并且有兴趣参加私有测试版，请联系您的Adobe客户团队。 [了解详情](https://business.adobe.com/products/product-analytics/adobe-product-analytics.html) | 不适用 | 2023 年 7 月 17 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-313118;AN-313390;AN-314135;AN-316381;AN-316811

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | 不适用 | 不适用 |

{style="table-layout:auto"}

## 相关资源

* [以前的 2023 年 CJA 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
