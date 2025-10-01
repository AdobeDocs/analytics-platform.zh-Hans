---
title: 配置 Content Analytics
description: 有关如何配置 Content Analytics 的概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: f149a2bd7f184f4e8f6e67979649e2d9f609d603
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 85%

---

# 配置 Content Analytics

本文概要介绍了如何配置Content Analytics。

在配置Content Analytics之前，必须确保满足[先决条件](#prerequisites)，您确实具有所需的[访问控制](#access-control)，并且了解[限制](#limitations)。


高级步骤

![Content Analytics 的配置](../assets/aca-configuration.svg){zoomable="yes"}

1. 使用 Content Analytics [引导式配置](guided.md)向导，该向导将指导您完成设置 Content Analytics 配置的先决条件所需的所有步骤。您可以随时保存您的配置，稍后可返回。
1. 只要您熟悉了配置值，就可以实施该配置。此实施会根据您在向导中配置的内容创建所有必需的构件。
1. 只有在您 [手动发布](manual.md)标记属性后，您的 Content Analytics 配置才会有效部署并开始收集数据。

1. 您只能使用[引导式配置](guided.md)向导对已实施的配置进行一些细微的更改。例如，更改[数据视图](/help/data-views/data-views.md)。
1. 您可以在相关联标记属性中使用 [Adobe Content Analytics 扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview)对已实施的配置进行其他更改。
1. 只有在您[手动重新发布](manual.md)标记属性后，才会有效部署更改的配置，并且会根据您的更改开始收集数据。


## 先决条件

在配置 Content Analytics 之前，请确保满足以下先决条件：

* 您已将 Content Analytics 中使用的特征化服务的用户代理和 IP 地址列入允许列表。要配置的用户代理字符串是：<code>AdobeFeaturization/1.0</code>。
* 如果您[使用 JavaScript 实施了 Web SDK](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/install/library){target="_blank"}用于定期收集行为数据，请确保您使用了默认名称 <code>alloy</code> 为 JavaScript 库。
* 您具有 Customer Journey Analytics 产品管理员角色，并具有管理连接和管理数据视图的额外权限。
* 如果您考虑收集 Content Analytics 体验，请确保根据网页的更改设置并更新[ Content Analytics 版本控制](manual.md#versioning)。
* 您必须具有[数据收集权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/permissions){target="_blank"}：
   * [Experience Platform 权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Experience Platform 数据收集/权限](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* 您已仔细考虑了以下重要的配置选项：

   * 您的站点适合体验报告。只有满足以下条件才可以生成正确的体验报告：
      * 网站上的页面必须能够通过页面 URL 重复出现。
      * 任何给定用户看到的文本内容都可以使用页面 URL 重复出现，并且不取决于 cookie 或其他个性化机制。
   * 您清楚地了解要捕获哪些页面的内容参与度分析和洞察。
   * 您清楚地了解要为哪些（类型的）资产捕获内容参与度分析和洞察。


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

用于Content Analytics事件数据的架构由系统拥有。 无法修改系统拥有的架构，这意味着：

* 为支持地理位置、机器人检测或设备查找等功能，您不能包含字段组。
* 无法添加特定标识符以支持[基于字段的拼接](/help/stitching/fbs.md)。

>[!MORELIKETHIS]
>
>* [引导式配置](guided.md)
>* [手动配置](manual.md)
>* [访问控制](/help/technotes/access-control.md)
>
