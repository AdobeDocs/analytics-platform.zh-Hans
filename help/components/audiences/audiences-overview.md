---
title: CJA受众发布概述
description: 了解Customer Journey Analytics中受众发布的概念
source-git-commit: ba98ee1372c4ce396af3f41aeb98bc42ee6d02ce
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 3%

---


# CJA受众发布概述

>[!NOTE]
>
>此功能当前位于 [有限测试](/help/release-notes/releases.md).

您现在可以创建并发布在Customer Journey Analytics(CJA)中发现的受众，以 [实时客户资料](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=cn) ，用于客户定位和个性化。 通过实时客户资料，您可以通过合并来自多个渠道（包括在线、离线、CRM和第三方）的数据，来全面了解每个客户。 利用用户档案，可将客户数据整合到统一视图中，为每次客户互动提供一个加盖时间戳的可操作帐户。

发布受众为对CJA中的分析采取操作提供了一种清晰的方法。 这些操作可能包括：

* 向此受众发送电子邮件。
* 向此受众发送推送消息。
* 在Adobe Journey Optimizer中使用受众进行旅程。
* 通过Experience Platform目标将受众导出到第三方。

## 关键术语

**受众**:一组标识或一组标识，其中既具有命名空间，又具有与该命名空间相关的特定ID。 受众可从Adobe Experience Platform及其顶部的应用程序（如CJA）传输。 受众可以包含混合命名空间。

**过滤器**:一组规则，在一段时间内对一组数据进行评估后，会生成一个数据子集。 当与其他支持服务结合时，在创建受众的过程中可以使用过滤器。 过滤器在CJA中定义和维护。

**过滤器** 与 **区段**:CJA不使用“区段”的概念，而是使用“过滤器”。 虽然这两种规则都是一组可以包含相似逻辑的规则，但它们会产生不同的输出。 过滤器用于缩小数据集以便进行分析。 区段用于生成可用于激活的身份列表。 区段会在实时客户资料中生成受众，而过滤器（单独）则不会。 CJA Audience Publishing是我们使用CJA过滤器创建受众的过程，供实时客户资料使用。

## 权限

管理员会自动 [!UICONTROL 受众发布] 在Adobe Admin Console。 他们可以向个人用户授予此权限。

## 后续步骤

* [创建和发布受众](/help/components/audiences/publish.md)
* [管理受众](/help/components/audiences/manage.md)


