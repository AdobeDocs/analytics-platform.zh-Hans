---
title: 架构您的架构以用于Customer Journey Analytics
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
source-git-commit: 33cfff3f675fc03c3444531e8426cb806cdf8559
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# 架构您的架构以用于Customer Journey Analytics

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

Adobe建议在升级到Customer Journey Analytics时创建Experience Data Model (XDM)架构。 XDM架构允许精简架构，根据您的组织和您使用的特定Platform应用程序的需求量身定制。 当需要对架构进行更改时，您不必在数千个未使用的字段中进行筛选，即可找到需要更新的字段。

在开始创建XDM架构之前：

1. 识别您的数据团队和整个组织中的其他利益相关者。

1. 确定贵组织适用于Customer Journey Analytics的理想架构设计，同时考虑到贵组织中使用的任何其他Adobe Experience Platform应用程序。

1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。

