---
title: Customer Journey Analytics 隐私权概述
description: 介绍 Customer Journey Analytics 中隐私权设置的工作方式。
translation-type: tm+mt
source-git-commit: 415a4a7f7d540a0329f973042d1c6a6a285d5b1b
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 100%

---


# Customer Journey Analytics 隐私权概述

通常情况下，Customer Journey Analytics 中的任何隐私权相关设置都是从 Adobe Experience Platform 继承来的。

## GDPR

Customer Journey Analytics 将不直接订阅一般数据保护条例 (GDPR) 中央服务，而是会继承在 Experience Platform 中所做的所有数据集更改。我们依赖 Platform 数据湖来执行 GDPR 删除请求，并在这些请求在 Pipeline 上完成时通知我们。我们会监听 Pipeline，并将所有更改同步到 Customer Journey Analytics 中事件数据集的受影响批次。受 GDPR 删除请求影响的配置文件和查找数据集将在每个删除请求后完全重新摄取。我们可以保证在数据湖中的删除事件发生 7 天内执行删除请求。

## CCPA

《加州消费者隐私法案》(CCPA) 加强了对美国加利福尼亚州居民的隐私权和消费者保护。这项法案将于 2020 年 1 月 1 日正式生效。CCPA 为加州居民提供了新的数据隐私权，例如，访问和删除个人数据的权利，知晓其个人数据是否被出售或披露（包括披露给谁）的权利，以及拒绝出售其个人数据的权利。为应对即将生效的 CCPA，我们的“隐私服务”将支持选择退出出售个人数据的请求。
