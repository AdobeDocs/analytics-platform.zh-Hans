---
title: Report Builder 中受到限制的标签是什么
description: 描述 Report Builder 中受到限制的标签
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
exl-id: 99c3c66e-928e-4363-a6a9-bbcab792337a
source-git-commit: e7e3affbc710ec4fc8d6b1d14d17feb8c556befc
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 60%

---

# Report Builder 中受到限制的标签

通常，Customer Journey Analytics 中与数据治理相关的设置继承自 Adobe Experience Platform。Customer Journey Analytics与Adobe Experience Platform数据管理之间的集成允许标记敏感Customer Journey Analytics数据并执行隐私政策。

在Experience Platform使用的数据集上创建的隐私标签和策略可以在Customer Journey Analytics数据视图工作流中显示。 这些标签会阻止或警告从敏感字段创建量度和/或维度的用户。有关数据集的更多信息，请参阅[数据集概述](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html?lang=zh_Hans)。

此外，从Customer Journey Analytics（通过报表、导出、API等）导出数据时，还会添加警告或标签，以通知用户报表包含需要以特定方式处理的敏感信息。

此集成允许您更轻松地管理合规性。 组织中的数据管理员可以设置策略以限制使用。 因此，您的Customer Journey Analytics用户可以更自信地使用数据，因为他们知道数据使用符合数据管理员定义的策略。

有关更多信息，请参阅[ Customer Journey Analytics 和数据治理](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)。

## 查看 Report Builder 中受到限制的标签

Customer Journey Analytics中出现了两个Adobe定义的策略，这些策略影响报表、下载和共享：

* 强制分析策略
* 强制下载策略

受这些策略影响的组件将以灰色显示。当您将鼠标悬停在应用了策略的组件上时，将会显示一条注释，以指示以下内容：**相关策略已应用于此字段，因此禁止使用此数据。**&#x200B;有关更多信息，请参阅[标签和政策](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html)。

![](assets/rb-restricted-label.png)

## 更新包含受限数据的报告

如果用户创建的 Report Builder 报告中的数据元素后来受到限制，则在刷新报告时，会显示一条错误消息。

![](assets/error-restricted-data.png)
