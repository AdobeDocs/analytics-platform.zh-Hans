---
title: Customer Journey Analytics 和数据管理
description: 描述数据管理在 Customer Journey Analytics 中的工作方式。
exl-id: ab2b7ff2-c638-4ab4-bc86-d1701bebcb1a
feature: Privacy
role: Admin
hold: true
autotag-review: '2026-05-19T09:18:17.400Z'
TQID: 'https://experienceleague.adobe.com/oDdNRwjtEU2vmeDvQ3DcM8w6XKQTBoTaXAIhmgjSoBk'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: eb00932f-4d46-46bc-b1d8-10de7588db8d
subfeature_v2:
  - id: ffe2fd81-0630-49b3-a33b-4b8899e89c51
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 116c169326e98f4e3d649c2fe72dbff44eaa0225
workflow-type: tm+mt
source-wordcount: 560
ht-degree: 88%

---

# Adobe Customer Journey Analytics 和数据治理

通常情况下，Customer Journey Analytics 中的任何数据管理相关设置都是从 Adobe Experience Platform 继承来的。

## 数据管理

Adobe Customer Journey Analytics 和 [Adobe Experience Platform 数据治理](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html)之间的集成允许标记敏感的 Customer Journey Analytics 数据和实施隐私政策。

在 Experience Platform 使用的数据集上创建的隐私标签和政策可以在 Customer Journey Analytics 数据视图工作流中显示。 这些标签阻止或警告从敏感字段创建量度和/或维度的用户。

此外，从 Customer Journey Analytics 导出数据时（通过报告、导出、API 等），将添加其他警告或标签，以通知用户报告包含需要以特定方式处理的敏感信息。

此集成允许您更轻松地管理合规性。 组织中的数据管理员可以设置策略以限制使用。 因此，您的 Customer Journey Analytics 用户可以更自信地使用数据，因为他们知道此等数据使用符合数据管理员定义的策略。

[了解详情](/help/data-views/data-governance.md)

## 同意报告和筛选

Customer Journey Analytics可以在Experience Platform配置文件数据集中使用同意策略成员资格数据来报告访客同意，并可以选择在摄取非同意访客的数据之前排除这些访客。 同意报表将同意策略作为Analysis Workspace中的组件提供，并且同意筛选会根据您配置的营销操作在摄取时排除非同意访客。

[了解详情](/help/connections/consent-reporting-filtering/consent-overview.md)

## 隐私请求

Adobe 会根据适用的本地和国际法律处理隐私请求。

由于 Customer Journey Analytics 使用的是 Adobe Experience Platform 中的数据，Adobe 提供了[Adobe Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=zh-Hans)，用于提交数据访问和删除请求。 这些请求同时适用于原始数据集和已重新生成键值的数据集。

## GDPR

Customer Journey Analytics 将不直接订阅一般数据保护条例 (GDPR) 中央服务，而是会继承在 Experience Platform 中所做的所有数据集更改。 Customer Journey Analytics 依赖于 Platform 数据湖来执行 GDPR 删除请求，并会在请求完成时通知 Customer Journey Analytics。 Customer Journey Analytics 中事件数据集受影响批次的所有更改都会与 Platform 数据同步。 受 GDPR 删除请求影响的轮廓和查找数据集将在每个删除请求后完全重新摄取。 在数据湖中，删除请求通常会在删除事件发生后的 7 天内完成处理。

## CCPA

《加州消费者隐私法案》(CCPA) 加强了对美国加利福尼亚州居民的隐私权和消费者保护。 此法案已于 2020 年 1 月 1 日生效。CCPA 为加州居民提供了新的数据隐私权，例如，访问和删除个人数据的权利，知晓其个人数据是否被出售或披露（包括披露给谁）的权利，以及拒绝出售其个人数据的权利。依照 CCPA，隐私服务将支持选择退出出售个人数据的请求。

>[!MORELIKETHIS]
>
>* [博客：如何在 Adobe Customer Journey Analytics 中保持有效治理](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/bg-p/adobe-analytics-blogs/page/4)
