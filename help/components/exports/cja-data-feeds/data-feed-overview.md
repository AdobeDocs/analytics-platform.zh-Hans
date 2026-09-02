---
description: 了解如何使用数据馈送从Customer Journey Analytics中获取原始数据。 了解使用数据馈送的前提条件以及下一步该怎么做。
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: Analytics 数据馈送概述
feature: Components
hide: true
exl-id: 991a7861-cbde-4d55-935c-d56c8031853e
autotag-review: '2026-05-19T08:45:11.428Z'
TQID: 'https://experienceleague.adobe.com/TO8lEW8-GE-sIGj3vmm0X1zCgpg-0VpS1wjs0-HQjg8'
product_v2: id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2: id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2: id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 4872f0078640fbd358a60a6d7baeb3ea575d3559
workflow-type: tm+mt
source-wordcount: 252
ht-degree: 18%

---

# 数据馈送概述

{{release-limited-testing}}

数据馈送是从Customer Journey Analytics中获取原始数据的有效方法。 您可以根据贵组织的决定，在Adobe以外的其他平台中使用此原始数据。 数据会在每小时结束时按小时批次交付，或者在每天结束时按天批次交付。

有关数据馈送与其他Customer Journey Analytics导出方法（如完全表导出）的比较，请参阅[Analytics产品比较](/help/getting-started/analytics-product-comparison.md)。

## 先决条件

在使用数据馈送之前，请确保您满足以下所有要求：

* 包含被摄取到Adobe Customer Journey Analytics <!-- For more information, see Data ingestion overview - add link -->中的数据的有效实现
* 您的帐户是Analytics产品管理员，或者属于有权访问数据馈送<!--???-->的产品配置文件
* 在[!DNL Amazon S3]、[!DNL Google Cloud Platform]、[!DNL Azure RBAC]或[!DNL Azure SAS]上配置的分段

## 快速入门

要开始在Customer Journey Analytics中使用数据馈送，请首先了解Customer Journey Analytics中的数据馈送与Adobe Analytics中的数据馈送有何不同。 了解这些差异后，您可以将Adobe Analytics数据馈送映射到Customer Journey Analytics，然后开始创建数据馈送。

1. [了解Customer Journey Analytics和Adobe Analytics中的数据馈送之间的差异](/help/components/exports/cja-data-feeds/df-comparison.md)。

1. [了解数据馈送与Analysis Workspace之间的数据差异](/help/components/exports/cja-data-feeds/df-comparison-workspace.md)。

1. [将Adobe Analytics数据馈送列映射到Customer Journey Analytics](/help/components/exports/cja-data-feeds/aa-cja-column-reference.md)。

1. [创建数据馈送](/help/components/exports/cja-data-feeds/create-feed.md)。

