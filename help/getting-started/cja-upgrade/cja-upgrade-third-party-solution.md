---
title: 从第三方分析解决方案升级到 Customer Journey Analytics
description: 了解如何从第三方分析解决方案升级到 Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '238'
ht-degree: 100%

---

# 从第三方分析解决方案升级到 Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="非 Adobe Analytics 产品"
>abstract="为 Adobe Analytics 以外的产品（如 Google Analytics）收集数据的实施。从非 Adobe Analytics 产品升级到 Customer Journey Analytics 时，选择此选项将禁用升级指南中不适用的几个选项。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

不是从 Adobe Analytics，而是从一个分析解决方案升级到 Customer Journey Analytics 的推荐流程是对 Experience Platform Web SDK 进行新的实施，这是 Customer Journey Analytics 的首选数据收集方法。结合 Web SDK，Adobe 还建议将第三方分析解决方案的历史数据导入 Adobe Experience Platform。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

从第三方分析解决方案（如 Google Analytics）迁移到 Customer Journey Analytics 时，请使用以下流程：

1. 按照[详细的建议升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)操作。

   这些步骤适用于从 Adobe Analytics 升级的组织。执行这些步骤时，请了解以下方面：

   * 您必须创建一个数据流。

   * 您不能从非 Adobe Analytics 解决方案迁移项目和组件。

   * 根据您的分析解决方案，可能有一个源连接器可用于摄取历史数据。有关详细信息，请参阅 Experience Platform 文档中[源连接器概述](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/home)中的[分析](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sources/home#analytics)。


如果您需要更具体的建议、指导或支持，请联系您的 Adobe 代表。

