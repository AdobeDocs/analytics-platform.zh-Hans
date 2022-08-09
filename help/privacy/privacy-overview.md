---
title: Customer Journey Analytics和数据管理
description: 介绍数据管理在Customer Journey Analytics中的工作方式。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: 2f74c10f821aed421e31ee8e14b854f2a73c11f1
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 75%

---

# Customer Journey Analytics和数据管理

通常情况下，Customer Journey Analytics中与数据管理相关的任何设置都会从Adobe Experience Platform继承。

## 数据管理

CJA支持在Adobe Experience Platform中设置的“数据管理”标签和策略。 有关更多信息，请参阅 [CJA支持Adobe Experience Platform数据管理](/help/data-views/data-governance.md).

## GDPR

Customer Journey Analytics 将不直接订阅一般数据保护条例 (GDPR) 中央服务，而是会继承在 Experience Platform 中所做的所有数据集更改。我们依赖 Platform 数据湖来执行 GDPR 删除请求，并在这些请求在 Pipeline 上完成时通知我们。我们会监听 Pipeline，并将所有更改同步到 Customer Journey Analytics 中事件数据集的受影响批次。受 GDPR 删除请求影响的配置文件和查找数据集将在每个删除请求后完全重新摄取。我们可以保证在数据湖中的删除事件发生 7 天内执行删除请求。

## CCPA

《加州消费者隐私法案》(CCPA) 加强了对美国加利福尼亚州居民的隐私权和消费者保护。这项法案将于 2020 年 1 月 1 日正式生效。CCPA 为加州居民提供了新的数据隐私权，例如，访问和删除个人数据的权利，知晓其个人数据是否被出售或披露（包括披露给谁）的权利，以及拒绝出售其个人数据的权利。为应对即将生效的 CCPA，我们的“隐私服务”将支持选择退出出售个人数据的请求。
