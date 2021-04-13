---
title: 如何将Google Analytics数据导入Adobe Experience Platform以在Customer Journey Analytics(CJA)中进行分析
description: '解释如何利用Customer Journey Analytics(CJA)将Google Analytics和火库数据引入Adobe Experience Platform。 '
exl-id: 314378c5-b1d7-4c74-a241-786198fa0218
translation-type: tm+mt
source-git-commit: 793b2ce4ec8a487f6c4290fe2eff00879fcca13d
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 2%

---


# 将Google Analytics数据收录到Adobe Experience Platform

此用例重点介绍如何将Google Analytics数据作为数据集收录到Adobe Experience Platform。 （这同时适用于历史和实时数据。） 完成后，您可以组合这两个数据集来实现用户旅程的跨设备视图。

Experience Platform中的数据集由两部分组成：模式和数据集中的实际记录。 模式（简称“体验数据模型”或XDM）与数据集的列类似，与描述数据本身的蓝图或规则类似。 在平台内，Adobe提供2种模式:

* 开箱即用的模式，您可以将Google Analytics数据自动映射到(称为体验事件模式)
* 您可以创建并轻松地将模式Google Analytics数据映射到

Adobe数据模型最强大的方面之一是，它允许您将所有客户交互模式标准化为一个通用 — 这使得在CJA中将数据拼接在一起变得容易得多。

## 先决条件

要完成这些任务，您需要以下访问权限：

* 访问Adobe Experience Platform
* 访问通用Google Analytics(Google Analytics360版本)或Google Analytics4(免费版本或Google Analytics360版本)
* 访问Customer Journey Analytics及其[管理权限](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=zh-Hans#admin-access-permissions)。

如何将Google Analytics数据引入Adobe Experience Platform取决于您使用的Google Analytics版本：

| 如果您使用... | 您还需要这个许可证…… | 然后…… |
| --- | --- | --- |
| **通用Google Analytics** | Google Analytics360 | 执行下面说明步骤1 - 5 |
| **Google Analytics4** | 免费的GA版本或Google Analytics360 | 执行下面说明的步骤1和3-5。 无需步骤2。 |

## 1.将Google Analytics数据连接到BigQuery

请注意，以下说明基于通用Google Analytics。

请参阅[这些说明](https://support.google.com/analytics/answer/3416092?hl=en)。

## 2.将Google Analytics会话转换为BigQuery中的事件

>[!IMPORTANT]
>
>此步骤仅适用于Universal Analytics客户

GA数据将每个记录作为用户会话存储在其数据中，而不是单独事件。 转换数据可使数据与Adobe Experience Platform兼容。

请参阅[这些说明](https://support.google.com/analytics/answer/3437618?hl=en)。

您需要创建SQL查询，以将Universal Analytics数据转换为符合Experience Platform规范的格式。 视图此视频，以获取说明：

>[!VIDEO](https://video.tv.adobe.com/v/332634)

## 3.将JSON格式的Google Analytics事件导出到Google Cloud存储，并将它们保存到存储桶

请参阅[这些说明](https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)。

## 4.将来自Google Cloud存储的数据导入Experience Platform

视图此视频，以获取说明：

>[!VIDEO](https://video.tv.adobe.com/v/332641)

## 5.将GCS事件导入Adobe Experience Platform并映射到XDM模式

BigQuery导出模式(https://support.google.com/analytics/answer/3437719?hl=en&amp;ref_topic=3416089)
