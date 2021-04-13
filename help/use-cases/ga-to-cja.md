---
title: 在Customer Journey Analytics中设置Google Analytics报告
description: null
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 49b49f24dbc68b1d9e843e0f4522123e6792a438
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---

# 在Customer Journey Analytics中设置Google Analytics报告

此用例说明如何将Google Analytics数据导入Adobe Experience Platform，然后

## 先决条件

* 访问Adobe Experience Platform
* 访问通用Google Analytics(Google Analytics360版本)或Google Analytics4(免费版本或Google Analytics360版本)
* 访问Customer Journey Analytics

## 1.将Google Analytics数据连接到Adobe Experience Platform

如何将Google Analytics数据引入Adobe Experience Platform取决于您使用的Google Analytics版本：

| 如果您使用... | 您还需要这个许可证…… | 然后…… |
| --- | --- | --- |
| **通用Google Analytics** | Google Analytics360 | 执行下面说明步骤1 - 5 |
| **Google Analytics4** | 免费的GA版本或Google Analytics360 | 执行下面说明步骤2 - 5。 无需步骤1。 |

以下说明基于通用Google Analytics。

1. 将您的Google Analytics数据连接到BigQuery，以便您可以转换部分数据。
请参阅[这些说明](https://support.google.com/analytics/answer/3416092?hl=en)。

1. （仅限Universal Analytics客户）将Google Analytics会话转换为BigQuery中的事件。
这使数据与Adobe Experience Platform兼容。 请参阅[这些说明](https://support.google.com/analytics/answer/3437618?hl=en)。

   详细信息：在BigQuery中，您的GA数据将显示为表：

   ![](assets/ga-bigquery.png)
您需要创建SQL查询，以将Universal Analytics数据转换为符合Experience Platform规范的格式。视图此视频，以获取说明：

   >[!VIDEO](https://video.tv.adobe.com/v/332634)

1. 将JSON格式的Google Analytics事件导出到Google Cloud存储，并将它们保存到存储桶中。
请参阅[这些说明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)。

1. 将来自Google Cloud存储的数据导入Experience Platform。
视图此视频，以获取说明：

   >[!VIDEO](https://video.tv.adobe.com/v/332641)

1. 将GCS事件导入Adobe Experience Platform并映射到XDM模式

BigQuery导出模式(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
