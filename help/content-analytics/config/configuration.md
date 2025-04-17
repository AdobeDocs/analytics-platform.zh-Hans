---
title: 配置内容分析
description: 有关如何配置内容分析的概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 3ea46223-c7d0-4b1f-bc84-4f35494f13a0
source-git-commit: 981cd0c01d775acbd71cada7efed4911b4bcb157
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 3%

---

# 配置内容分析

{{release-limited-testing}}


Content Analytics的配置包括以下步骤：

内容分析的![配置](../assets/aca-configuration.svg){zoomable="yes"}

1. 使用Content Analytics [引导式配置](guided.md)向导引导您完成设置Content Analytics配置的先决条件所需的所有步骤。 您可以随时保存配置并稍后返回。
1. 在对配置值感到满意后，您可以实施配置。 此实施会根据您在向导中配置的内容，创建所有必需的工件。
1. 仅当[手动发布](manual.md) Tags属性时，您的Content Analytics配置才会有效部署并启动数据收集。

1. 您只能使用[引导式配置](guided.md)向导对已实施的配置进行一些细微更改。 例如，更改[数据视图](/help/data-views/data-views.md)。
1. 您可以在关联的Tags属性中使用[Adobe Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)对已实施的配置进行其他更改。
1. 仅当[手动重新发布](manual.md) Tags属性时，配置修改才会有效部署，并且根据您的更改开始数据收集。


## 先决条件

在配置Content Analytics之前，请确保满足以下先决条件：

* 您已将Content Analytics中使用的功能服务的用户代理和IP地址添加到允许列表。 要配置的用户代理字符串为： <code>AdobeFeaturization/1.0</code>。
* 如果您已使用JavaScript](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/web-sdk/install/library){target="_blank"}实施[Web SDK以进行常规行为数据收集，请确保使用默认名称<code>alloy</code> 用于JavaScript库。
* 您具有Customer Journey Analytics产品管理员角色，该角色具有管理连接和管理数据视图的附加权限。
* 如果您考虑收集Content Analytics体验，请确保根据您网页上的更改来设置和更新[Content Analytics版本控制](manual.md#versioning)。
* 您必须具有数据收集](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions){target="_blank"}的[权限：
   * [Experience Platform权限](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-permissions){target="_blank"}
   * [Experience Platform数据收集权限](https://experienceleague.adobe.com/en/docs/experience-platform/collection/permissions#adobe-experience-platform-data-collection-permissions){target="_blank"}
* 您仔细考虑了以下重要配置选项：

   * 您的网站适合体验报告。 只有在满足以下条件时，才可能生成正确的体验报表：
      * 必须使用页面URL重现网站上的页面。
      * 任何给定用户看到的文本内容都可以使用页面URL重现，并且不依赖于Cookie或其他个性化机制。
   * 您已清楚地了解要捕获哪些页面的内容参与分析和见解。
   * 您已清楚地了解要捕获内容参与分析和见解的资产（类型）。


## 访问控制

>[!IMPORTANT]
>
>无法配置用于启用或禁用单个用户或用户组的Content Analytics访问的Content Analytics权限。
>

要提供用户或用户组对Content Analytics的访问权限，您必须提供用户或用户组对为Content Analytics](guided.md#data-view)配置的一个或多个[数据视图的访问权限。

此访问权限意味着：

1. 启用了Content Analytics的数据视图包含在特定Customer Journey Analytics产品配置文件的数据视图权限中。
1. 该特定的Customer Journey Analytics产品配置文件是分配给用户或用户组的产品配置文件之一。

>[!MORELIKETHIS]
>
>* [引导式配置](guided.md)
>* [手动配置](manual.md)
>* [访问控制](/help/technotes/access-control.md)
>
