---
title: Content Analytics 手动配置
description: 如何手动配置 Content Analytics
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
exl-id: 2b2d1cc2-36da-4960-ab31-0a398d131ab8
source-git-commit: a3d974733eef42050b0ba8dcce4ebcccf649faa7
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 70%

---

# Content Analytics 手动配置

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
>&#x200B;>[数据收集标记发布概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview)
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

## 身份标识

Content Analytics通过以下方式处理身份：

* ECID会自动填充到Content Analytics架构的`identityMap`部分中。
* 如果您需要`identityMap`中的其他标识值，则需要在Web SDK扩展的`onBeforeEventSend`回调中设置这些值。
* 不支持基于字段的拼合，因为架构由系统拥有。 因此，您无法向架构中添加其他字段以支持基于字段的拼合


为了确保Content Analytics标识数据和Adobe Experience Platform Web SDK数据标识数据在字段级别正确拼合，您需要在事件发送[回调之前对](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/onbeforeeventsend){target="_blank"}上的Web SDK进行修改。

1. 导航到包含Adobe Experience Platform Web SDK扩展和Adobe Content Analytics扩展的&#x200B;**[!UICONTROL Tags]**&#x200B;属性。
1. 选择![插件](/help/assets/icons/Plug.svg) **[!UICONTROL 扩展]**。
1. 选择&#x200B;**[!UICONTROL Adobe Experience Platform Web SDK]**&#x200B;扩展。
1. 选择&#x200B;**[!UICONTROL 配置]**。
1. 在&#x200B;**[!UICONTROL SDK实例]**&#x200B;部分中，向下滚动到&#x200B;**[!UICONTROL 数据收集]** - **[!UICONTROL 启用，然后事件发送回调]**。

   ![在事件发送回调之前](/help/content-analytics/assets/onbeforeeventsendcallback.png)

1. 选择&#x200B;**[!UICONTROL &lt;/>在事件发送回调代码]**&#x200B;前提供。
1. 添加以下代码：

   ```javascript
   window.adobeContentAnalytics?.forwardEvent(content);
   
   content.xdm.identityMap = _satellite.getVar('identityMap');
   if ((content.xdm.eventType === "content.contentEngagement") && (_satellite.getVar('identityMap') != null)) {
      return true;
   }
   ```

   ![在事件发送回调之前](/help/content-analytics/assets/onbeforeeventsendcallbackcode.png)

1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存代码。
1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存扩展。
1. [发布](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/tags/publish/overview)标记属性的更新。





