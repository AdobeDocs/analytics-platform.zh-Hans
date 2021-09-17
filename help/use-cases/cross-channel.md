---
title: 跨渠道历程分析
description: 在整个客户历程中通过客户互动分析和提取洞察。
source-git-commit: a6c6620a4f4118755509e534d7d6a12bf08b4b67
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 6%

---


# 跨渠道历程分析

通过统一各种Web、移动和离线属性的数据，可以统一各种渠道中的客户行为视图。 例如，您可以使用此整合视图分析桌面和移动设备之间的客户交互情况，以了解客户行为并提取分析信息以优化数字客户体验。 您还可以分析不同渠道的客户交互，包括数字和离线渠道（如支持交互和店内购买），以便更好地了解和优化客户旅程。

## 架构

![跨渠道架构](assets/cross-channel-architecture.svg)

## 实施步骤

1. [为要](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hans) 摄取的数据创建架构。
1. [为要](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html) 摄取的数据创建数据集。
1. [将数据引入 Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html).
1. 跨数据集使用通用的命名空间ID，或使用[跨渠道分析](/help/connections/cca/overview.md)将人员链接在一起。 请注意，Customer Journey Analytics当前不使用Experience Platform配置文件或Identity服务进行拼合。
1. 执行任何自定义数据准备，以确保将时间序列数据集中的通用键摄取到Customer Journey Analytics。
1. 为查找数据提供一个可连接到事件数据中字段的主ID。 在许可中计为行。
1. 将配置文件数据的相同主ID设置为事件数据的主ID。
1. 配置数据连接，以将数据从Experience Platform摄取到Customer Journey Analytics。
1. [创建数据视](/help/data-views/create-dataview.md) 图连接以选择要包含在视图中的特定维度和量度。此外，还可以在数据视图中配置归因和分配设置。 这些设置在报告时计算。
1. 创建项目以在Analysis Workspace中配置功能板和报表。

## 注意事项

建立此工作流时，请确保考虑以下几点。

* 跨渠道分析数据需要在每个记录中使用相同的ID命名空间。
* 统一不同数据集的合并过程需要跨数据集使用通用的主人员/实体密钥。
* 当前不支持基于次密钥的联合。
* 基于字段的身份拼合过程允许根据后续的临时ID记录（如身份验证ID）为行中的身份重新生成键值。 这允许将不同的记录解析为单个ID，以便在人员级别进行分析，而不是在设备或Cookie级别进行分析。
* 同一XDM字段的对象和属性将合并到一个维度中Customer Journey Analytics。 要将不同数据集中的多个属性合并到同一Customer Journey Analytics维度中，数据集应引用相同的XDM字段或架构。
