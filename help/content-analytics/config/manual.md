---
title: Content Analytics手动配置
description: 如何手动配置内容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 20767a4672319602d35435aeedb76749a245e691
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 0%

---

# Content Analytics手动配置

{{draft-aca}}

{{release-limited-testing}}

本文详细介绍启动或停止Content Analytics配置的数据收集或编辑Content Analytics实施所需的手动操作。

可以使用以下手动配置操作：

## 开始数据收集

要为已实施的Content Analytics配置启动数据收集，请执行以下操作：

1. 遵循[发布流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}。 成功发布包含Content Analytics配置的Tags属性的库。

1. [安装](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation)您的开发、暂存或发布环境中页面的`<head>`元素中的嵌入代码，遵循Content Analytics。


## 停止数据收集

要停止为已实施的Content Analytics配置收集数据，请执行以下操作：

1. 从开发、暂存或生产环境中的页面的`<head>`元素中删除[嵌入代码](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments)，具体情况受Content Analytics限制。
1. [删除](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)与Content Analytics配置关联的Tags属性。



## 修改数据收集

您可以使用[引导式配置向导](guided.md)对已实施的配置进行一些细微更改。 例如，更改数据视图，或者启用或禁用体验。

在与Adobe Content Analytics配置关联的Tags属性中使用[Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)对以下工件进行更改：

* [沙盒和数据流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >验证在早期阶段已使用[引导式配置](guided.md)为Content Analytics配置了在Adobe Content Analytics扩展中配置的沙盒和数据流。 此配置可确保所有必需的工件均可用。<br/><br/>同时验证沙盒或数据流的更新不会干扰另一个配置为使用同一沙盒或数据流的Content Analytics配置。
  >

* [体验捕获和定义](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  您可以启用或禁用体验，并编辑正则表达式和查询参数的组合，以确定内容在网站上的呈现方式。

* [事件筛选](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  您可以编辑正则表达式，以修改筛选页面和资产的方式。


在Adobe Content Analytics扩展中进行更改后，请确保使用[发布流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}来根据所做的更改启动数据收集。



>[!MORELIKETHIS]
>
>[引导式配置](guided.md)
>[数据收集标记发布概述](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## 版本控制

如果您需要对Content Analytics体验进行版本控制，则必须在您认为要分析的体验的页面上添加全局`adobe.getContentExperienceVersion`函数。

`adobe.getContentExperienceVersion`函数应返回一个字符串作为值，该值可以是您选择的任何内容，以标识版本。 该版本已附加到[Experience ID URL](/help/content-analytics/report/components.md#experience-metadata)。

如果函数不存在或函数未返回任何值，则使用值`NoVersion`作为默认值。

### 示例

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
