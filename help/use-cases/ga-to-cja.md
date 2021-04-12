---
title: 在Customer Journey Analytics中设置Google Analytics报告
description: null
translation-type: tm+mt
source-git-commit: c07d32eef579432bf92f94cbbe4e99188b2de74c
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 1%

---


# 在Customer Journey Analytics中设置Google Analytics报告

设置Google Cloud存储连接器，

配置Google标签管理器

BigQuery导出模式(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)

1. 在大查询中将GA会话转换为事件
1. 将Google Analytics事件导出到Google Cloud存储
1. 将GCS事件导入Adobe Experience Platform并映射到XDM模式

## 先决条件

* 访问Adobe Experience Platform
* 访问通用Google Analytics(Google Analytics360版本)或Google Analytics4(免费版本或Google Analytics360版本)
* 访问Customer Journey Analytics

## 1.将Google Analytics数据连接到Adobe Experience Platform

如何将Google Analytics数据引入Adobe Experience Platform取决于您使用的Google Analytics版本：

| 如果您使用... | 您还需要这个许可证…… | 然后…… |
| --- | --- | --- |
| **通用Google Analytics** | Google Analytics360 | 执行下面说明步骤1 - x |
| **Google Analytics4** | 免费的GA版本或Google Analytics360 | 无需在以下说明中执行步骤x。 |

以下说明基于通用Google Analytics。

1. 将您的Google Analytics数据连接到BigQuery和
请参阅[这些说明](https://support.google.com/analytics/answer/3416092?hl=en)。
1. （仅限Universal Analytics客户）将Google Analytics会话转换为BigQuery中的事件。 这使数据与Adobe Experience Platform兼容。 请参阅[这些说明](https://support.google.com/analytics/answer/3437618?hl=en)。

   详细信息：在BigQuery中，您的GA数据将显示为表：

   ![](assets/ga-bigquery.png)
您需要创建SQL查询，以将Universal Analytics数据转换为符合Experience Platform规范的格式。
   * 视图此视频以获取说明。

1. 将JSON格式的Google Analytics事件导出到Google Cloud存储，并将它们保存到存储桶中。
请参阅[这些说明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)。
1. 将来自Google Cloud存储的数据导入Experience Platform。 （从Trevor获取Slide 10视频。）

