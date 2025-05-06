---
title: 构建用于 Customer Journey Analytics 的架构
description: 了解从 Adobe Analytics 升级到 Customer Journey Analytics 时的推荐路径
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: f932110a-ca9d-40d1-9459-064ef9cd23da
source-git-commit: 33e962bc3834d6b7d0a49bea9aa06c67547351c1
workflow-type: ht
source-wordcount: '487'
ht-degree: 100%

---

# 构建用于 Customer Journey Analytics 的架构 {#upgrade-schema-architect}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-schema-architect"
>title="架建架构"
>abstract="在您的组织内讨论数据收集的要求，并确定如何生成用于 Adobe Experience Platform 的架构。出现此步骤是因为您想要使用一个为您的组织定制的架构的使用推荐过程。正确执行此步骤至关重要，因为组织内所有团队都遵循一个架构可以使数据摄取变得更加容易。<br><br>将组织中的所有相关方聚集在一起以遵循一个统一架构的预计时间为 1-2 个月。这个时间范围在很大程度上取决于需要协调的团队数量以及需要统一的维度 + 量度的数量。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

Adobe 建议在从 Adobe Analytics 升级到 Customer Journey Analytics 时创建自定义体验数据模型 (XDM) 架构，以与 Web SDK 一起使用。或者，您可以使用默认的 Adobe Analytics 架构，该架构使用 Adobe Analytics ExperienceEvent 字段组。

自定义 XDM 架构允许根据您组织的需求和您使用的特定 Platform 应用程序定制简化的架构。与使用 Adobe Analytics ExperienceEvent 字段组的默认 Adobe Analytics 架构不同，当需要更改自定义 XDM 架构时，您不必筛选数千个未使用的字段来查找需要更新的字段。

有关这些架构选项的更多信息，请参阅[为 Customer Journey Analytics 选择架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-existing.md)。

在开始构建 XDM 架构时，请查看以下部分。

## 避开 XDM 架构中的 Adobe Analytics 限制

 Customer Journey Analytics 的底层架构比 Adobe Analytics 提供了更大的灵活性。创建新的 XDM 架构是实现这种灵活性的关键方法。升级到 Customer Journey Analytics 时，请确保避免将不必要的 Adobe Analytics 限制带入您的架构中。

>[!NOTE]
>
>以下信息尚未完成。它将很快完成。

| Adobe Analytics 数据架构 | XDM 模式架构 |
|---------|----------|
| 将单个量度添加到 Analytics 数据架构中。<br/>例如，在 Adobe Analytics 中，每个事件都有不同的 eVar。 | 在数据视图中而不是在 XDM 架构中创建单独的量度。如果您以后需要进行更改，这样做可以提供更大的灵活性。<br/>例如，在 Customer Journey Analytics 中，您在架构中有一个单一事件，并在数据视图中使用创建事件。 |
| 创建自定义变量需要 Props 和 eVar。 |  |

## 确定您的数据团队以及整个组织内的其他利益相关者

>[!NOTE]
>
>此信息尚不可用。它将很快提供。

## 考虑您的组织中使用的其他 Adobe Experience Platform 应用程序

>[!NOTE]
>
>此信息尚不可用。它将很快提供。
