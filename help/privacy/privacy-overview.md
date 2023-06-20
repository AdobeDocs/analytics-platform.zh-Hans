---
title: Customer Journey Analytics 和数据管理
description: 描述数据管理在 Customer Journey Analytics 中的工作方式。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 68%

---

# Adobe Customer Journey Analytics和数据管理

通常情况下，Customer Journey Analytics 中的任何数据管理相关设置都是从 Adobe Experience Platform 继承来的。

## 数据管理

Adobe Customer Journey Analytics与之间的集成 [Adobe Experience Platform数据管理](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=zh-Hans) 允许标记敏感Customer Journey Analytics数据并执行隐私政策。

在Experience Platform使用的数据集上创建的隐私标签和策略可以在Customer Journey Analytics数据视图工作流中显示。 这些标签阻止或警告从敏感字段创建亮度和/或维度的用户。

此外，从Customer Journey Analytics（通过报表、导出、API等）导出数据时，还会添加警告或标签，以通知用户报表包含需要以特定方式处理的敏感信息。

此集成允许您更轻松地管理合规性。 组织中的数据管理员可以设置策略以限制使用。 因此，您的Customer Journey Analytics用户可以更自信地使用数据，因为他们知道数据使用符合数据管理员定义的策略。

[了解详情](/help/data-views/data-governance.md)

## GDPR

Customer Journey Analytics 将不直接订阅一般数据保护条例 (GDPR) 中央服务，而是会继承在 Experience Platform 中所做的所有数据集更改。我们依赖 Platform Data Lake 来执行 GDPR 删除请求，并在这些请求在 Pipeline 上完成时通知我们。我们会监听 Pipeline，并将所有更改同步到 Customer Journey Analytics 中事件数据集的受影响批次。受 GDPR 删除请求影响的配置文件和查找数据集将在每个删除请求后完全重新摄取。我们可以保证在数据湖中的删除事件发生 7 天内执行删除请求。

## CCPA

《加州消费者隐私法案》(CCPA) 加强了对美国加利福尼亚州居民的隐私权和消费者保护。此法案已于 2020 年 1 月 1 日生效。CCPA 为加州居民提供了新的数据隐私权，例如，访问和删除个人数据的权利，知晓其个人数据是否被出售或披露（包括披露给谁）的权利，以及拒绝出售其个人数据的权利。依照 CCPA，隐私服务将支持选择退出出售个人数据的请求。
