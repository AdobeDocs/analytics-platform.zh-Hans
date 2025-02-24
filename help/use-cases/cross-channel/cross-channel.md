---
title: 跨渠道历程分析
description: 分析客户历程中的客户交互并从中提炼见解。
exl-id: 285532b1-eb37-4984-9559-054a18515ddf
solution: Customer Journey Analytics
feature: Use Cases, Cross-Channel Analysis
role: User
source-git-commit: 5e80e68c6b5d3dca19dae21c6719b040b28afaf9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 64%

---

# 跨渠道分析 {#cross-channel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-additional-datasets"
>title="将其他数据集添加到您的连接"
>abstract="将数据添加到Adobe Experience Platform中的数据集后，可将该数据集添加到Customer Journey Analytics中的连接。 确保从其他渠道添加数据时，它们符合您的组织使用的架构。<br><br>添加的每个数据集都需要大量工作，特别是要确保每个事件都有唯一标识符，并确保总体数据结构符合组织的自定义架构。建立此工作流程需要组织内多个团队之间数月时间进行协调。"

<!-- markdownlint-enable MD034 -->

跨渠道分析通过将各种Web、移动和离线资产中的数据统一起来，支持跨各种渠道的客户行为的单个综合视图。 例如，可使用此综合视图分析桌面和移动设备上的客户交互，从而了解客户行为并提炼见解以优化数字客户体验。还可分析各渠道（包括数字和线下渠道）的客户交互（如支持交互和店内购买）以更好地了解和优化客户历程。

## 实施步骤

![此部分所述的实施步骤流程。](../assets/cca-architecture.png)

1. 为要引入的数据[创建架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hans)。
1. 为要引入的数据[创建数据集](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/create-datasets-and-ingest-data.html)。
1. [将数据摄取到Experience Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/understanding-data-ingestion.html)：
   1. 通过Edge Network或Analytics源连接器从网站或移动设备应用程序获取基于事件的数据![event](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Events_18_N.svg)。
   2. 配置文件数据![配置文件](https://spectrum.adobe.com/static/icons/workflow_18/Smock_User_18_N.svg)（例如，来自CRM系统、呼叫中心应用程序、忠诚度应用程序）。
   3. 查找数据![查找](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)（例如，产品信息系统中的产品名称和类别）。

1. 跨数据集使用通用命名空间ID。 使用[拼接](../../stitching/overview.md)提升任何基于事件的数据集![数据刷新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataRefresh_18_N.svg)，以便在每行提供通用ID。 注意，Customer Journey Analytics 当前不使用 Experience Platform 轮廓或身份标识服务进行拼接。
1. 执行任何自定义数据准备，以确保将一个在时序数据集间公用的键引入 Customer Journey Analytics。
1. 为查找数据给予一个主 ID，后者可连接到事件数据中的某个字段。在许可中计为行。
1. 为轮廓数据设置同一主 ID 作为事件数据的主 ID。
1. [创建连接](../../connections/overview.md)以将相关数据集从Experience Platform摄取到Customer Journey Analytics。
1. 在连接上[创建数据视图](/help/data-views/create-dataview.md)以选择要包括在该视图中的特定维度和指标。还在该数据视图中配置归因和分配设置。在报告时计算这些设置。
1. [创建项目](/help/analysis-workspace/home.md)以在Analysis Workspace中配置功能板和报表。

## 注意事项

在建立此工作流程时，请确保将以下几点考虑在内。

* 跨通道分析数据要求每条记录上的 ID 命名空间都相同。
* 将不同的数据集统一在一起的合并过程需要一个在数据集间公用的人员/实体主键。
* 当前不支持基于辅助键的合并。
* 拼接过程允许根据共享相同永久ID的记录中的临时ID（例如身份验证ID）信息重新生成行中标识的键。这允许将不同的记录解析为单个拼接ID，以供在人员级别，而不是设备或Cookie级别进行分析。
* 同一 XDM 字段的对象和属性合并为 Customer Journey Analytics 中的一个维度。要将多个来自不同数据集的属性合并为同一个 Customer Journey Analytics 维度，这些数据集应引用相同的 XDM 字段或架构。

