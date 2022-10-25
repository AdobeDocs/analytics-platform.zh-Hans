---
title: CJA 受众发布概述
description: 了解 Customer Journey Analytics 中的受众发布的概念
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
source-git-commit: eba2eb71ca434e0306c018b80209caf52266ee15
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 83%

---

# CJA 受众发布概述

您现在可以在 Adobe Experience Platform 中创建并将在 Customer Journey Analytics (CJA) 中发现的受众发布到[实时客户个人资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=zh-Hans) (RTCP)，以实现客户定位和个性化。

通过发布受众可以提供一种明确的方式来激活 CJA 中发现的洞察并采取行动。这些行动可能包括：

* 在 Adobe Journey Optimizer 中将受众用于历程。
* 通过 Experience Platform 目标将受众导出到第三方。
* 使用从 CJA 中基于事件的数据派生出的有用属性丰富实时客户个人资料。
* 在发布受众后可以最低的延迟完成所有这些操作（几分钟）
* 发布一次性受众或定期受众

## 关键术语

**受众**：一组或一系列具有命名空间以及与该命名空间相关的特定 ID 的身份。受众可从 Adobe Experience Platform 及其之上的应用程序（例如 CJA）中传输。受众可以包含混合的命名空间。

**过滤器**：一组规则，通过某个时段的一组数据评估这组规则时会生成一个数据子集。与其他支持服务结合使用时，可在创建受众的过程中使用过滤器。过滤器在 CJA 中定义和维护。

**过滤器**&#x200B;与&#x200B;**区段**：CJA 不使用“区段”的概念，而是使用“过滤器”。虽然两者都是一组可能包含相似逻辑的规则，但它们会生成不同的输出。过滤器用于缩小数据集以用于分析用途。区段用于生成可用于激活的身份列表。区段会在实时客户档案中生成受众，而（仅凭）过滤器不会。CJA 受众发布是我们使用 CJA 过滤器创建可被实时客户档案使用的受众的过程。

## 权限

* 管理员在 Adobe Admin Console 中被自动授予&#x200B;**[!UICONTROL 受众发布]**&#x200B;权限。

* 管理员可以将此权限授予个人用户。

* 管理员还需要 Adobe Experience Platform 中的&#x200B;**[!UICONTROL 管理个人资料]**&#x200B;权限。

## 数据管理和同意

在CJA中发布受众时，会记录附加到受众中所用字段的数据管理标签和策略。  在任何Adobe Experience App中激活受众后，所有关联的“数据管理”标签和策略都可用于该受众，并且可以应用适当的强制实施。 [进一步了解同意](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html?lang=en#consent-policy).

## 后续步骤

* [创建并发布受众](/help/components/audiences/publish.md)
* [管理受众](/help/components/audiences/manage.md)
