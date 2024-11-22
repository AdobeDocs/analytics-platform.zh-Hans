---
title: 架构您的架构以用于Customer Journey Analytics
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 59089146b8e56db3b0b4084615f99dc65899b74f
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 0%

---

# 架构您的架构以用于Customer Journey Analytics

>[!NOTE]
> 
>只有在完成所有先前的升级步骤后，才应执行本页上的步骤。 您可以按照[推荐的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)进行操作，也可以按照[Adobe Analytics为您的组织动态生成的升级步骤来Customer Journey Analytics升级调查表](https://gigazelle.github.io/cja-ttv/)。
>
>完成此页面上的步骤后，请继续执行建议的升级步骤或动态生成的升级步骤。

Adobe建议在升级到Customer Journey Analytics时创建Experience Data Model (XDM)架构。 XDM架构允许精简架构，根据您的组织和您使用的特定Platform应用程序的需求量身定制。 当需要对架构进行更改时，您不必在数千个未使用的字段中进行筛选，即可找到需要更新的字段。

在开始设计XDM架构时，请查看以下部分。

## 避免XDM架构中的Adobe Analytics限制

与Adobe Analytics相比，Customer Journey Analytics的底层架构提供了更大的灵活性。 创建新的XDM架构是解锁这种灵活性的关键方法。 升级到Customer Journey Analytics时，请确保避免在架构中沿用不必要的Adobe Analytics限制。

| Adobe Analytics数据架构 | XDM架构架构 |
|---------|----------|
| 单个量度将会添加到Analytics数据架构中。<br/>例如，在Adobe Analytics中，每个事件的eVar各不相同。 | 在数据视图而不是XDM架构中创建单个量度。 如果以后需要进行更改，这样做可以在中提供更多灵活性。<br/>例如，在Customer Journey Analytics中，您在架构中只有一个事件，并在数据视图中使用创建事件。 |
| 创建自定义变量需要prop和eVar。 | B2 |
| A3 | B3 |

## 识别您的数据团队和整个组织中的其他利益相关者


## 考虑您在组织中使用的其他Adobe Experience Platform应用程序



1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
