---
title: 从第三方分析解决方案升级到 Customer Journey Analytics
description: 了解如何从第三方分析解决方案升级到Customer Journey Analytics
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: bc79ba1a-1153-4fe8-b265-9703a323c977
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 10%

---

# 从第三方分析解决方案升级到 Customer Journey Analytics {#upgrade-from-third-party}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-third-party"
>title="非 Adobe Analytics 产品"
>abstract="为Adobe Analytics以外的产品(如Google Analytics)收集数据的实施。 选择此选项将禁用调查表中的多个选项，当从非Adobe Analytics产品升级到Customer Journey Analytics时，这些选项不适用。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note}}

建议的从Adobe Analytics以外的分析解决方案升级到Customer Journey Analytics的过程是Experience Platform Web SDK的新实施，它是Customer Journey Analytics的首选数据收集方法。 在与Web SDK结合使用时，Adobe还建议将历史数据从第三方分析解决方案提取到Adobe Experience Platform中。

<!-- After you have enough historical data using the Experience Platform Web SDK and you have fully transitioned to Customer Journey Analytics, the Analytics source connector can be turned off and the Web SDK can be used exclusively. -->

从第三方分析解决方案(如Google Analytics)迁移到Customer Journey Analytics时，请按照以下流程操作：

1. 按照[详细的建议升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#detailed-recommended-upgrade-steps)操作。

   这些步骤适用于从Adobe Analytics进行升级的组织。 执行以下步骤时，请了解以下内容：

   * 您必须创建数据流。

   * 无法从非Adobe Analytics解决方案迁移项目和组件。

   * 根据您的分析解决方案，源连接器可能可用于摄取历史数据。 有关详细信息，请参阅Experience Platform文档的[Source连接器概述](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home)中的[Analytics](https://experienceleague.adobe.com/en/docs/experience-platform/sources/home#analytics)。


如果您需要更具体的建议、指导或支持，请联系您的Adobe代表。

