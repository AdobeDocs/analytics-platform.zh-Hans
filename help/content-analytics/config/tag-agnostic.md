---
title: Content Analytics Tags与配置
description: 了解如何在不使用Experience Platform数据收集标记的情况下配置Content Analytics。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin
hide: true
source-git-commit: 64b96d8b0917975f19c353e26d9e6437d1b4e5ac
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 5%

---


# Content Analytics Tags不可知配置

Adobe Content Analytics JavaScript库允许通过Experience Platform Edge Network将内容数据发送到Adobe Experience Platform，从而跟踪网站上的内容相关事件。 当您想要实施不带Adobe Experience Platform标记的Content Analytics (Launch)时，请使用此库。

>[!NOTE]
>
>本文适用于Web渠道的Content Analytics 。


>[!PREREQUISITES]
>
>在调用`initializeContentLibrary`之前，必须在页面上初始化Adobe Experience Platform Web SDK (Alloy)。

## 安装

您可以通过两种方式安装库：

### npm包

使用`npm`安装库。

1. 在命令行中，使用：

   ```bash
   npm install @adobe/content-analytics
   ```

1. 导入库：

   ```JavaScript
   import initializeContentLibrary from "@adobe/content-analytics";
   ```

### 脚本标记(CDN)

直接从CDN加载库。

1. 初始化[Web SDK JavaScript库](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library)并加载Content Analytics捆绑包：

   ```html
   <!-- 1. Load and configure Alloy first -->
   <script src="https://cdn1.adoberesources.net/alloy/2.x.x/alloy.min.js"></script>
   <script>
   alloy("configure", {
       datastreamId: "YOUR_DATASTREAM_ID",
       orgId: "YOUR_ORG_ID@AdobeOrg",
   });
   </script>
   
   <!-- 2. Load Content Analytics -->
   <script src="https://cdn1.adoberesources.net/content-analytics/1.x.x/content-analytics.min.js"></script>
   <script>
   window.contentAnalytics({
       datastreamId: "YOUR_DATASTREAM_ID",
   });
   </script>
   ```

   位置
   * `alloy/2.x.x`引用您要使用[Web SDK JavaScript库](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/install/library)的版本。
   * `content-analytics/1.x.x`是指您要使用Content Analytics SDK库的版本。

2. 独立内部版本将`window.contentAnalytics`公开为初始化函数。


## 数据流配置

`datastreamId`选项是必需的，并且必须引用具有配置了已启用Experience Platform体验事件数据集的Content Analytics服务的数据流。 确保与数据流关联的沙盒尚未与其他Content Analytics设置关联。

您可以为每个环境提供单独的数据流ID：

```javascript
initializeContentLibrary({
  datastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",          // production
  stagingDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",   // optional
  developmentDatastreamId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx", // optional
});
```

## 体验捕获与定义

启用体验跟踪并控制如何在您的网站上识别体验。 体验是通过将&#x200B;**域正则表达式**&#x200B;与可选&#x200B;**查询参数**&#x200B;组合在一起定义的，这些参数可在匹配页面中将一个体验与另一个体验区分开来。

| 选项 | 类型 | 默认 | 描述 |
|--------|------|---------|-------------|
| `includeExperiences` | 布尔值 | `false` | 启用页面/体验视图跟踪 |
| `experienceConfigurations` | 数组 | - | 按域正则表达式和查询参数定义体验 |

`experienceConfigurations`中的每个条目都接受：

| 属性 | 类型 | 描述 |
|----------|------|-------------|
| `regEx` | 字符串 | 与页面URL匹配的域正则表达式（例如`^(?!.*\b(store\|help\|admin)\b)`） |
| `queryParameters` | 数组 | 其值用于区分匹配页面上的体验的查询参数名称（例如`["outdoors", "patio", "kitchen"]`） |

### 示例

有关如何使用域正则表达式和查询参数启用体验跟踪的示例，请参见下文。

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  includeExperiences: true,
  experienceConfigurations: [
    {
      regEx: "^https://www\\.example\\.com/products",
      queryParameters: ["category", "collection"],
    },
    {
      regEx: "^https://www\\.example\\.com/blog",
      queryParameters: [],
    },
  ],
});
```

## 事件筛选

使用正则表达式控制数据收集中包含的页面URL和资产URL。 将以下模式示例用作起点，并在部署之前通过正则表达式测试器验证模式。

| 选项 | 类型 | 默认 | 描述 |
|--------|------|---------|-------------|
| `pageUrlQualifier` | 字符串（正则表达式） | - | 仅跟踪URL与此模式匹配的页面 |
| `assetUrlQualifier` | 字符串（正则表达式） | - | 仅跟踪URL与此模式匹配的资源 |
| `excludeURLsFromTracking` | 数组 | `[]` | 要从跟踪中排除的URL字符串列表 |

### 示例

有关如何从Content Analytics中排除文档页面以及仅考虑Content Analytics产品图像的示例，请参阅下文。

```javascript
initializeContentLibrary({
  datastreamId: "YOUR_DATASTREAM_ID",
  pageUrlQualifier: "^(?!.*\\/documentation).*",
  assetUrlQualifier: ".*\\/products\\/.*\\.(?:jpg|png|webp)",
  excludeURLsFromTracking: [
    "https://www.example.com/internal",
    "https://www.example.com/staging",
  ],
});
```

>[!NOTE]
>
>在[引导式配置](/help/content-analytics/config/guided.md)界面中设置Content Analytics配置后，可在该配置视图中访问特定于您配置的JavaScript设置。

