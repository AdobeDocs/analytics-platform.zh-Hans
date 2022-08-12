---
title: 什么是受限标签Report Builder
description: 描述Report Builder中受限的标签
role: Data Engineer, Data Architect, Admin, User
feature: Report Builder
type: Documentation
solution: Customer Journey Analytics
source-git-commit: 0e626b4072c68a69ae94dbfdfb53169aa34ca8ac
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 2%

---


# Report Builder中的限制标签

Customer Journey Analytics中与数据管理相关的设置通常继承自Adobe Experience Platform。 CJA与Adobe Experience Platform数据管理之间的集成允许为敏感CJA数据设置标签并强制执行隐私政策。

在CJA数据视图工作流中，可以显示在由Experience Platform使用的数据集上创建的隐私标签和策略。 这些标签可阻止或警告从敏感字段创建量度和/或维度的用户。 有关数据集的信息，请参阅 [数据集概述](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/overview.html)

此外，在从CJA导出数据（通过报表、导出、API等）时，会添加警告或标签，以通知用户报表包含需要以特定方式处理的敏感信息。

此集成使您能够更轻松地管理法规遵从性。 贵组织中的数据管理员可以设置策略以限制使用。 因此，您的CJA用户可以更自信地使用数据，因为他们知道数据符合数据管理者定义的策略。

有关更多信息，请参阅 [Customer Journey Analytics和数据管理](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-privacy/privacy-overview.html)

## 在Report Builder中查看受限数据

>[!NOTE]
>
>此功能当前正在进行[小范围测试](/help/release-notes/releases.md)。

CJA中会显示两个Adobe定义的策略，这些策略会影响报表、下载和共享：

* 强制实施Analytics策略
* 强制下载策略

受这些策略影响的组件呈灰显状态。 将鼠标悬停在已应用策略的组件上时，会显示一条注释以指示以下内容： **该领域已应用了禁止使用此数据的政策。** 有关详细信息，请参阅 [标签和策略](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-governance.html).

![](assets/rb-restricted-label.png)

## 更新包含受限数据的报表

如果用户创建的Report Builder报表包含稍后受限的数据元素，则在刷新报表时，会显示一条错误消息。

![](assets/error-restricted-data.png)
