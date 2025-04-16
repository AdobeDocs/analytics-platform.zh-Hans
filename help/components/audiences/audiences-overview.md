---
title: 了解 Customer Journey Analytics 受众发布概述
description: 了解 Customer Journey Analytics 中的受众发布的概念
exl-id: 30404bfc-0ee7-4f01-842c-7e6156dc0b45
feature: Audiences
role: User, Admin
source-git-commit: 9393be88ab7320adb5bd046701667f638673af5e
workflow-type: tm+mt
source-wordcount: '404'
ht-degree: 87%

---

# 受众发布概述

您现在可以在 Adobe Experience Platform 中创建并将在 Customer Journey Analytics 中发现的受众发布到[实时客户轮廓](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)，以实现客户定位和个性化。

通过发布受众可以提供一种明确的方式来激活 Customer Journey Analytics 中发现的洞察并采取行动。这些行动可能包括：

* 在 Adobe Journey Optimizer 中将受众用于历程。
* 通过 Experience Platform 目标将受众导出到第三方。
* 使用从 Customer Journey Analytics 中基于事件的数据派生出的有用属性丰富实时客户轮廓。
* 在发布受众后可以最低的延迟完成所有这些操作。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-components/audiences/publish.html#latency)
* 发布一次性受众或定期受众。

您在 Customer Journey Analytics 中创建的受众不必基于为轮廓启用的数据集。您可以将历史数据导入 Experience Platform，而无需为轮廓启用关联的数据集和架构。然后使用这些数据集在 Customer Journey Analytics 中发现相关受众，并将这些受众发布到 Experience Platform 中的实时客户轮廓，以进行激活。

## 关键术语

**受众**：一组或一系列具有命名空间以及与该命名空间相关的特定 ID 的身份标识。受众可从 Adobe Experience Platform 及其之上的应用程序（例如 Customer Journey Analytics）中传输。受众可以包含混合的命名空间。

**区段**：一组规则，通过某个时段的一组数据评估这组规则时会生成一个数据子集。 与其他支持服务结合使用时，区段可用于创建受众的过程。 区段是在Customer Journey Analytics中定义和维护的。

## 权限

* 管理员在 Adobe Admin Console 中会被自动授予&#x200B;**[!UICONTROL 受众发布]**&#x200B;权限。

* 管理员和产品轮廓管理员可以向个人用户授予&#x200B;**[!UICONTROL 受众创建]**&#x200B;和&#x200B;**[!UICONTROL 受众查看]**&#x200B;权限。请参阅[用户级别的访问控制](/help/technotes/access-control.md#user-level-access)，了解更多信息。

* 管理员还需要 Adobe Experience Platform 中的&#x200B;**[!UICONTROL 管理轮廓]**&#x200B;权限。

## 数据治理和同意

当您在 Customer Journey Analytics 中发布受众时，将会记录附加到受众中使用的字段的数据治理标签和策略。在任何 Adobe Experience 应用程序中激活受众后，所有相关的数据治理标签和策略都可供该受众使用，并且可以应用适当的强制执行。[进一步了解同意](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/user-guide.html#consent-policy)。

## 后续步骤

* [创建并发布受众](/help/components/audiences/publish.md)
* [管理受众](/help/components/audiences/manage.md)
