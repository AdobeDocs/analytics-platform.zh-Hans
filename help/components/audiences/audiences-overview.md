---
title: Customer Journey Analytics受众发布概述
description: 了解 Customer Journey Analytics 中的受众发布的概念
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 54%

---

# Customer Journey Analytics受众发布概述

您现在可以创建在Customer Journey Analytics中发现的受众，并将其发布到 [Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=en) (RTCDP)，用于Adobe Experience Platform中的客户定位和个性化。

通过发布受众，可以明确地激活在Customer Journey Analytics中找到的分析并对其执行操作。 这些行动可能包括：

* 在 Adobe Journey Optimizer 中将受众用于历程。
* 通过 Experience Platform 目标将受众导出到第三方。
* 使用从Customer Journey Analytics中基于事件的数据派生出的有用属性来扩充实时客户用户档案。
* 在发布受众后可以最低的延迟完成所有这些操作。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html?lang=en#latency)
* 发布一次性受众或定期受众.

您在Customer Journey Analytics中创建的受众不必基于为配置文件启用的数据集。 您可以将历史数据摄取到Experience Platform中，而无需为配置文件启用关联的数据集和架构。 然后，使用这些数据集发现Customer Journey Analytics中的相关受众，并将这些受众发布到Experience Platform中的RTCDP以供激活。

## 关键术语

**受众**：一组或一系列具有命名空间以及与该命名空间相关的特定 ID 的身份。受众可以从Adobe Experience Platform和位于其顶部的应用程序(如Customer Journey Analytics)中传输。 受众可以包含混合的命名空间。

**过滤器**：一组规则，通过某个时段的一组数据评估这组规则时会生成一个数据子集。与其他支持服务结合使用时，可在创建受众的过程中使用过滤器。筛选器是在Customer Journey Analytics中定义和维护的。

**筛选器** 对比 **区段**：Customer Journey Analytics不使用“区段”的概念，而是使用“过滤器”。 虽然两者都是一组可能包含相似逻辑的规则，但它们会生成不同的输出。过滤器用于缩小数据集以用于分析用途。区段用于生成可用于激活的身份列表。区段会在实时客户档案中生成受众，而（仅凭）过滤器不会。Customer Journey Analytics受众发布是我们使用Customer Journey Analytics过滤器创建可被实时客户档案使用的受众的过程。

## 权限

* 管理员在 Adobe Admin Console 中被自动授予&#x200B;**[!UICONTROL 受众发布]**&#x200B;权限。

* 管理员可以将此权限授予个人用户。

* 管理员还需要 Adobe Experience Platform 中的&#x200B;**[!UICONTROL 管理个人资料]**&#x200B;权限。

## 数据治理和同意

在Customer Journey Analytics中发布受众时，将记录附加到受众中使用的字段的数据治理标签和策略。  在任何 Adobe Experience 应用程序中激活受众后，所有相关的数据治理标签和策略都可供该受众使用，并且可以应用适当的强制执行。[进一步了解同意](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=zh-Hans#consent-policy)。

## 后续步骤

* [创建并发布受众](/help/components/audiences/publish.md)
* [管理受众](/help/components/audiences/manage.md)
