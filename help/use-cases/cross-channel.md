---
title: 跨渠道历程分析
description: 分析客户历程中的客户交互并从中提炼见解。
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
source-git-commit: 68ca5b1ee9d695f53b22c821cec481cc116dcdb3
workflow-type: ht
source-wordcount: '433'
ht-degree: 100%

---

# 跨渠道历程分析

通过将各种 Web、移动和线下属性产生的数据统一起来，对于审视客户在各种渠道中的行为形成单个综合视图。例如，可使用此综合视图分析桌面和移动设备上的客户交互，从而了解客户行为并提炼见解以优化数字客户体验。还可分析各渠道（包括数字和线下渠道）的客户交互（如支持交互和店内购买）以更好地了解和优化客户历程。

## 体系结构

![跨渠道体系结构](assets/cross-channel-architecture.svg)

## 实施步骤

1. 为要引入的数据[创建架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hans)。
1. 为要引入的数据[创建数据集](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html)。
1. [将数据引入 Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html)。
1. 使用在数据集间公用的命名空间 ID 或使用[跨渠道分析](/help/connections/cca/overview.md)将人员联系在一起。注意，Customer Journey Analytics 当前不使用 Experience Platform 配置文件或标识服务进行拼接。
1. 执行任何自定义数据准备，以确保将一个在时序数据集间公用的键引入 Customer Journey Analytics。
1. 为查找数据给予一个主 ID，后者可连接到事件数据中的某个字段。在许可中计为行。
1. 为配置文件数据设置同一主 ID 作为事件数据的主 ID。
1. 配置一个数据连接以将数据从 Experience Platform 引入到 Customer Journey Analytics。
1. 在连接上[创建数据视图](/help/data-views/create-dataview.md)以选择要包括在该视图中的特定维度和指标。还在该数据视图中配置归因和分配设置。在报告时计算这些设置。
1. 在 Analysis Workspace 中创建一个项目以配置功能板和报表。

## 注意事项

在建立此工作流程时，请确保将以下几点考虑在内。

* 跨通道分析数据要求每条记录上的 ID 命名空间都相同。
* 将不同的数据集统一在一起的合并过程需要一个在数据集间公用的人员/实体主键。
* 当前不支持基于辅助键的合并。
* 通过基于字段的标识拼接过程，可根据后续的临时 ID 记录（如身份验证 ID）为行中的标识重新生成键。这样可将不同的记录解析为单个 ID，以供在人员级别而非设备或 Cookie 级别进行分析。
* 同一 XDM 字段的对象和属性合并为 Customer Journey Analytics 中的一个维度。要将多个来自不同数据集的属性合并为同一个 Customer Journey Analytics 维度，这些数据集应引用相同的 XDM 字段或架构。
