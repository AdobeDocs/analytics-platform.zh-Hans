---
title: 内容分析手动配置
description: 如何手动配置内容分析
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: 6d23203468032510446711ff5a874fd149531a9a
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 100%

---

# 内容分析手动配置

本文详细介绍了要启动或停止 Content Analytics 配置的数据收集或者要编辑 Content Analytics 实施所需的手动操作。

可以使用以下手动配置操作：

## 开始数据收集

要为已实施的 Content Analytics 配置开始收集数据：

1. 按照[发布流程](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview){target="_blank"}操作。成功发布包含 Content Analytics 配置的标记属性库。

1. 在开发、暂存或发布环境的页面元素中[安装](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/environments/environments#installation)嵌入代码`<head>`，取决于 Content Analytics。


## 停止数据收集

要为已实施的 Content Analytics 配置停止收集数据：

1. 在开发、暂存或生成环境的页面元素中移除[嵌入代码](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/environments/environments)`<head>`，取决于 Content Analytics。
1. [删除](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview) Content Analytics 配置的相关标记属性。



## 更改数据收集

您可以使用[引导式配置向导](guided.md)对已实施的配置进行一些细微的更改。例如，更改数据视图，或者启用或禁用体验。

您可以使用与 Content Analytics 配置相关联的标记属性中的 [Adobe Content Analytics 扩展](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview)来更改以下构件：

* [沙盒和数据流](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-datastreams){target="_blank"}。

  >[!CAUTION]
  >
  >验证您在 Adobe Content Analytics 扩展中配置的沙盒和数据流是否已在某个早期阶段使用[引导式配置](guided.md)为 Content Analytics 进行了配置。此配置可确保所有必需的构件均可用。<br/><br/>还应验证沙盒或数据流的更新不会干扰为使用相同沙盒或数据流而进行的另一个 Content Analytics 配置。
  >

* [体验捕捉和定义](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview?lang=en#configure-experience-capture-and-definition)

  您可以启用或禁用体验，并编辑正则表达式与查询参数的一些组合来确定如何在您的网站上呈现内容。

* [事件分段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/extensions/client/content-analytics/overview#configure-event-segmenting){target="_blank"}

  您可以编辑正则表达式来更改页面和资产的分段方式。


在 Adobe Content Analytics 扩展中进行更改后，请确保使用[发布流程](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview){target="_blank"}，以根据这些更改开始收集数据。



>[!MORELIKETHIS]
>
>[引导式配置](guided.md)
>[数据收集标记发布概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview)
>


## 版本控制

如果您想收集 Content Analytics 体验，您应该考虑实施版本控制，以确保正确收集新的体验（网页的变化）。

要实施版本控制，您可以在您想要分析的体验的页面上添加一个全局`adobe.getContentExperienceVersion`函数。

`adobe.getContentExperienceVersion` 函数的返回值应是一个由您选择的可识别版本的任何字符串。该版本被附加到[体验 ID URL](/help/content-analytics/report/components.md#experience-metadata)。

如果该函数不存在或者函数不返回任何值，则应使用 `NoVersion` 作为默认值。

### 示例

```
window.adobe = window.adobe || {};
window.adobe.getContentExperienceVersion = () => {
  return "1.0";
};
```
