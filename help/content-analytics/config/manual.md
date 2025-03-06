---
title: Content Analytics手动配置
description: 如何手动配置内容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
hidefromtoc: true
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 35298dd6d18ebb07d104a608aeff06cb864ee1dc
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 1%

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

要激活新配置或对现有配置所做的更改，请执行以下操作：

1. 您需要遵循[发布流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}。 仅当您成功发布包含Content Analytics配置的Tag属性的库时，才会为您配置的域、体验和资产收集Content Analytics数据。

1. 您需要在开发、暂存或发布环境中的页面的`<head>`元素中[安装](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments#installation)嵌入代码，具体取决于内容分析。


## 停用

要取消激活收集内容分析数据，请执行以下操作：

1. 在开发、暂存或生产环境中的页面的`<head>`元素中删除[嵌入代码](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/environments/environments)，具体取决于内容分析。
1. [删除](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)与您的Content Analytics配置关联的标记属性。



## 修改

通常，您应该使用[引导式配置向导](guided.md)来更改您的实施。

或者，您可以使用与您的Adobe配置关联的Tag属性中的[Content Analytics扩展](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview)来更改以下工件：

* [沙盒和数据流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >您必须验证在Adobe Content Analytics扩展中配置的沙盒和数据流是否已在早期阶段使用[引导式配置](guided.md)为Content Analytics配置。 此配置可确保所有必需的工件均可用。<br/><br/>还必须验证沙盒或数据流的更新不会干扰配置为使用同一沙盒或数据流的其他Content Analytics配置。
  >

* [事件筛选](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-filtering){target="_blank"}

  您可以编辑正则表达式，以修改筛选页面和资产的方式。


在Adobe Content Analytics扩展中进行更改后，请确保使用[发布流](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview){target="_blank"}来激活更改。



>[!MORELIKETHIS]
>
>[引导式配置](guided.md)
>[数据收集标记发布概述](https://experienceleague.adobe.com/en/docs/experience-platform/tags/publish/overview)
>


## 版本控制

如果您需要对您的内容分析体验进行版本控制，则必须在您认为要分析的体验的页面上添加全局`adobe.getContentExperienceVersion`函数。

`adobe.getContentExperienceVersion`函数应返回一个字符串作为值，该值可以是您选择用于标识版本的任何值。 该版本将附加到Experience ID URL。

如果函数不存在或函数未返回任何值，则使用值`NoVersion`作为默认值。

### 示例

```
function adobe.getContentExperienceVersion() {
  return "1.0";
}
```
