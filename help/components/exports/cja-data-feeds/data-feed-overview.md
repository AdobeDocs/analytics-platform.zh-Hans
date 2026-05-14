---
description: 了解如何使用数据馈送从Customer Journey Analytics中获取原始数据。 了解使用数据馈送的前提条件以及下一步该怎么做。
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: Analytics 数据馈送概述
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
source-git-commit: 5e77857ca846767e3b9e7479baa4a4b18c6e3c8f
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 21%

---

# 数据馈送概述

数据馈送是从Customer Journey Analytics中获取原始数据的有效方法。 您可以根据贵组织的决定，在Adobe以外的其他平台中使用此原始数据。 数据在每小时结束时以小时为单位分批发送，或者在每天结束时以天为单位分批发送。

## 先决条件

在使用数据馈送之前，请确保您满足以下所有要求：

* 包含被摄取到Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->中的数据的有效实现
* 您的帐户是Analytics产品管理员，或者属于有权访问数据馈送<!--???-->的产品配置文件
* 在{DNL Amazon S3}、{DNL Google Cloud Platform}、{DNL Azure RBAC}或 {DNL Azure SAS}

## 快速入门

要开始在Customer Journey Analytics中使用数据馈送，请首先了解Customer Journey Analytics中的数据馈送与Adobe Analytics中的数据馈送有何不同。 了解这些差异后，您可以将Adobe Analytics数据馈送映射到Customer Journey Analytics，然后开始创建数据馈送。

1. [了解Customer Journey Analytics和Adobe Analytics中的数据馈送之间的差异](/help/components/exports/cja-data-feeds/df-comparison.md)。

1. [将Adobe Analytics数据馈送列映射到Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)。

1. [创建数据馈送](/help/components/exports/cja-data-feeds/create-feed.md)。
