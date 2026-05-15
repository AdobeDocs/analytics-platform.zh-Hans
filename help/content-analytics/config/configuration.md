---
title: 配置 Content Analytics
description: 了解如何为Web和移动渠道配置Content Analytics。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
TQID: https://experienceleague.adobe.com/a-Mu3MKfpRsUqgxx7JWP3NR4vji62VaNFi-hI5teDZI
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: d9715c3da9893e1c47b702acb4daef5e666bedd7
workflow-type: tm+mt
source-wordcount: 776
ht-degree: 76%

---


# 配置 Content Analytics

本文档以高层级的方式介绍了如何配置 Content Analytics。

在配置 Content Analytics 之前，您必须确保已满足[先决条件](#prerequisites)，具备所需的[访问控制](#access-control)，并了解相关[限制](#limitations)。


高层级步骤

![Content Analytics 的配置](../assets/aca-configuration.svg){zoomable="yes"}

1. 使用 Content Analytics [引导式配置](guided.md)向导，该向导将指导您完成设置 Content Analytics 配置的先决条件所需的所有步骤。 您可以随时保存您的配置，稍后可返回。
1. 只要您熟悉了配置值，就可以实施该配置。 此实施会根据您在向导中配置的内容创建所有必需的构件。
1. 仅当[手动发布](manual.md)时，Tags属性才是您有效部署的Content Analytics配置并启动数据收集的内容。

1. 您只能使用[引导式配置](guided.md)向导对已实施的配置进行一些细微的更改。 例如，更改[数据视图](/help/data-views/data-views.md)。
1. 您可以使用[Web](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview)或[移动设备](https://developer.adobe.com/client-sdks/solution/adobe-content-analytics/)的关联Tags属性中的Adobe Content Analytics扩展对已实施的配置进行其他更改。
1. 只有手动重新发布标记属性时，配置修改才会有效部署，数据收集才会启动。


## 先决条件

在配置 Content Analytics 之前，请确保满足以下先决条件：

### Web

* 您已将 Content Analytics 中使用的特征化服务的用户代理和 IP 地址列入允许列表。 要配置的用户代理字符串是：<code>AdobeFeaturization/1.0</code>。
* 如果您[使用 JavaScript 实施了 Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library){target="_blank"}用于定期收集行为数据，请确保您使用了默认名称 <code>alloy</code> 为 JavaScript 库。
* 您具有 Customer Journey Analytics 产品管理员角色，并具有管理连接和管理数据视图的额外权限。
* 如果您决定收集Content Analytics体验，请确保您根据对网页所做的更改来设置和更新Content Analytics版本控制。
* 您必须具有[数据收集权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/permissions){target="_blank"}：
   * [Experience Platform](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}权限。
   * [Experience Platform数据收集](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}权限。
* 您已仔细考虑了以下重要的配置选项：

   * 您的站点适合体验报告。 只有满足以下条件才可以生成正确的体验报告：
      * 网站上的页面必须能够通过页面 URL 重复出现。
      * 任何给定用户看到的文本内容都可以使用页面 URL 重复出现，并且不取决于 cookie 或其他个性化机制。
   * 您已清楚地了解要捕获哪些页面以进行内容参与分析和洞察。
   * 您清楚地了解要为哪些（类型的）资产捕获内容参与度分析和洞察。

### 移动

* 请确保为移动设备应用程序启用了[Experience Platform Edge Network](https://developer.adobe.com/client-sdks/edge/edge-network/)和[Edge Network的Experience Platform标识](https://developer.adobe.com/client-sdks/edge/identity-for-edge-network/)扩展。
* 您具有 Customer Journey Analytics 产品管理员角色，并具有管理连接和管理数据视图的额外权限。
* 您必须具有[数据收集权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/permissions){target="_blank"}：
   * [Experience Platform](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}权限。
   * [Experience Platform数据收集](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}权限。



## 访问控制

>[!IMPORTANT]
>
>没有 Content Analytics 权限可供您配置来为单个用户或用户组启用或禁用 Content Analytics 访问权限。
>

要为用户或用户组授予对 Content Analytics 的访问权限，您必须向该用户或用户组授予对一个或多个[为 Content Analytics 配置的数据视图](guided.md#data-view)的访问权限。

此访问权限表示：

1. 启用了 Content Analytics 的数据视图包含在某个特定 Customer Journey Analytics 产品轮廓的数据视图权限中。
1. 此特定的 Customer Journey Analytics 产品轮廓是分配给该用户或用户组的产品轮廓之一。

## 限制

Content Analytics 事件数据所使用的架构由系统所有。 系统所有的架构不可修改，这意味着：

* 您无法通过添加字段组来支持诸如地理位置、机器人检测或设备查询等功能。
* 您无法添加特定标识符以支持[基于字段的拼接](/help/stitching/fbs.md)。

>[!MORELIKETHIS]
>
>* [引导式配置](guided.md)
>* [手动配置](manual.md)
>* [访问控制](/help/technotes/access-control.md)
>
