---
title: 创建用于Customer Journey Analytics的架构
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 0%

---

# 创建查找数据集以对Customer Journey Analytics中的数据分类

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

与Adobe Analytics中的分类数据类似，查找数据集是在Customer Journey Analytics中对数据进行分类的方法。

使用Analytics Source Connector时，某些标准查找数据集会在报告时自动应用。 有关详细信息，请参阅[向数据集添加标准查找](/help/connections/standard-lookups.md)。

要使用Experience PlatformWeb SDK的新实施对数据进行分类，您需要为包含要分类的数据的每个维度创建一个查找数据集。

要创建在Customer Journey Analytics中使用的查找数据集，请执行以下操作：

1. 在AEP中，创建新架构。 这是一个专用于查找数据集的新架构。 无法使用现有架构。

1. 您必须创建一个用于查找的新架构类。

1. 根据这些创建查询数据集。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
