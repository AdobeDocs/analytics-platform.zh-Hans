---
title: Content Analytics手动配置
description: 如何手动配置内容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 0cd9cd508d474df3dff176bca4596d0379ac86b4
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 0%

---

# Content Analytics手动配置

>[!WARNING]
>
>本文是即将发布的最终版本的初步非官方草稿版本，是内容分析文档的一部分。 所有内容可能会发生更改，并且本条当前版本不承担任何法律义务。
>

{{release-limited-testing}}

本文详细介绍激活或取消激活Content Analytics配置或编辑您的Content Analytics实施所需的手动操作。

可以使用以下手动配置操作：

## 激活

要激活新配置或对现有配置所做的更改，您需要[发布](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}关联的标记属性。 仅当您发布Content Analytics标记属性时，才会为您配置的域、体验和资产收集Content Analytics数据。


## 停用

要取消激活收集内容分析数据，请[取消发布](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}与您的Content Analytics配置关联的标记属性。



## 修改

通常，您应该使用[引导式配置向导](guided.md)来更改您的实施。

或者，您可以使用与您的Adobe配置关联的Tag属性中的Content Analytics扩展，对以下工件进行更改：

* [沙盒和数据流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >您必须验证在Adobe Content Analytics扩展中配置的沙盒和数据流是否已在早期阶段使用[引导式配置](guided.md)为Content Analytics配置。 此配置可确保所有必需的工件均可用。<br/><br/>还必须验证沙盒或数据流的更新不会干扰配置为使用同一沙盒或数据流的其他Content Analytics配置。
  >

* [事件筛选](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}。

  您可以编辑正则表达式，以修改筛选页面和资产的方式。


在Adobe Content Analytics扩展中进行更改后，请确保您[激活](#activate)所做的更改。



>[!MORELIKETHIS]
>
>[引导式配置](guided.md)
>[数据收集标记发布概述](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>