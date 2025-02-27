---
title: 构建用于 Customer Journey Analytics 的架构
description: 了解从Adobe Analytics升级到Customer Journey Analytics时推荐的路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 1ae4be09a07bd4991342daa43cc23fb966b68aaf
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 28%

---

# 构建用于 Customer Journey Analytics 的架构 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="架建架构"
>abstract="在您的组织内讨论数据收集的要求，并确定如何生成用于 Adobe Experience Platform 的架构。出现此步骤是因为您想要使用一个为您的组织定制的架构的使用推荐过程。正确执行此步骤至关重要，因为组织内所有团队都遵循一个架构可以使数据摄取变得更加容易。<br><br>将组织中的所有相关方聚集在一起以遵循一个统一架构的预计时间为 1-2 个月。这个时间范围在很大程度上取决于需要协调的团队数量以及需要统一的维度 + 量度的数量。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

从Adobe Analytics升级到Customer Journey Analytics时，Adobe建议创建一个要与Web SDK一起使用的自定义Experience Data Model (XDM)架构。 或者，您可以使用默认的Adobe Analytics架构，该架构使用Adobe Analytics ExperienceEvent字段组。

自定义XDM架构允许精简架构，根据您的组织和您使用的特定Platform应用程序的需求量身定制。 与使用Adobe Analytics ExperienceEvent字段组的默认Adobe Analytics架构不同，当需要对自定义XDM架构进行更改时，您不必在数千个未使用的字段中进行筛选来查找需要更新的字段。

有关这些架构选项的更多信息，请参阅[选择您的Customer Journey Analytics架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)。

在开始设计XDM架构时，请查看以下部分。

## 避免XDM架构中的Adobe Analytics限制

Customer Journey Analytics的底层架构提供了比Adobe Analytics更大的灵活性。 创建新的XDM架构是解锁这种灵活性的关键方法。 当您升级到Customer Journey Analytics时，请确保避免在架构中沿用不必要的Adobe Analytics限制。

| Adobe Analytics数据架构 | XDM架构架构 |
|---------|----------|
| 单个量度将会添加到Analytics数据架构中。<br/>例如，在Adobe Analytics中，您对每个事件都有一个不同的eVar。 | 在数据视图而不是XDM架构中创建单个量度。 如果以后需要进行更改，这样做可以在中提供更多灵活性。<br/>例如，在Customer Journey Analytics中，您在架构中只有一个事件，并在数据视图中使用创建事件。 |
| 创建自定义变量需要prop和eVar。 | B2 |
| A3 | B3 |

## 识别您的数据团队和整个组织中的其他利益相关者


## 考虑您在组织中使用的其他Adobe Experience Platform应用程序



1. 继续执行[建议的升级步骤](/help/getting-started/cja-upgrade/cja-upgrade-recommendations.md#recommended-upgrade-steps-for-most-organizations)或[动态生成的升级步骤](https://gigazelle.github.io/cja-ttv/)。
