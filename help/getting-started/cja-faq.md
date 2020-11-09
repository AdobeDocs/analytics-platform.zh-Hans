---
title: Customer Journey Analytics 常见问题解答
description: Customer Journey Analytics - 常见问题解答。
translation-type: tm+mt
source-git-commit: 1f8526e0b48e334a62776eb2ca4fbf09febf4dd4
workflow-type: tm+mt
source-wordcount: '1296'
ht-degree: 41%

---


# 常见问题解答

## 先决条件

| 问题 | 回答 |
| --- | --- |
| 我需要吗 [!UICONTROL 专用设备图] 或 [!UICONTROL 设备合作伙伴] for [!UICONTROL Customer Journey Analytics]? | 不， [!UICONTROL 专用设备图] 或 [!UICONTROL 设备合作伙伴] 不是 [!UICONTROL Customer Journey Analytics]. 事实上，目前还不支持这两个功能。 |
| 我需要吗 [!UICONTROL Experience CloudID] (ECID) [!UICONTROL Customer Journey Analytics]? | 不需要，[!UICONTROL Customer Journey Analytics] 支持数据集中的任何 ID，无论该 ID 是 ECID 还是您选择的任何其他 ID。 |
| 如果我需要在之前对数据进行ETL（提取、转换、加载），该怎么办 [!UICONTROL Customer Journey Analytics]? | 现在，如果在将数据放入 AEP 之前需要对数据进行转换，则需要与 ETL 合作伙伴（Unifi 或 Informatica）合作。如果您在数据已被收录后需要ETL, [!UICONTROL Adobe Experience Platform查询服务] 提供一些有限的选项。 |

## 拼接数据

| 问题 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] 是否可以跨设备或跨数据集进行“拼合”？ | 是的。[!UICONTROL Customer Journey Analytics] 是一个“自带 ID”分析系统。我们于2020年11月发布了一款拼接解决方案。 了解更多. |
| 是否支持从匿名行为到实名行为的拼合？ | 否，目前尚不支持。 |

## 将数据载入 [!UICONTROL Customer Journey Analytics]

| 问题 | 回答 |
| --- | --- |
| 能否将不同数据 [!UICONTROL Adobe Experience Platform] 一个箱子 [!UICONTROL Customer Journey Analytics] 连接？ | 不能，您不能跨沙盒访问数据。您只能合并位于同一沙盒中的数据集。[了解更多...](https://docs.adobe.com/content/help/zh-Hans/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| 预计的延迟 [!UICONTROL Customer Journey Analytics] on [!UICONTROL Adobe Experience Platform]? | <ul><li>在正常负载下：少于 60 分钟&#x200B;<br>**注意：**&#x200B;如果通过管道的数据流量异常高，则预期滞后时间可能会长达 24 小时。</li><li>回填数据（最多支持 13 个月的数据，不考虑数据大小）：少于 4 周</li></ul> |
| 如何在 [!UICONTROL Customer Journey Analytics] 中将在线数据与离线数据关联起来？ | [!UICONTROL Customer Journey Analytics] 是一个“自带 ID”分析系统。只要数据集之间的人员 ID 匹配，[!UICONTROL Customer Journey Analytics] 就可以跨数据集连接区段、归因、流量、流失等。 |
| 如何将线下数据 [!UICONTROL Customer Journey Analytics]? | 您必须先将任何数据带入Experience Platform，然后才能将其与 [!UICONTROL Customer Journey Analytics]. 如果需要，Experience Platform 的数据载入团队可以为您提供建议或咨询。 |
| 如何获得 [!UICONTROL Adobe Analytics] 数据 [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Adobe Analytics] 数据可通过Experience Platform [Adobe Analytics源连接器](https://docs.adobe.com/content/help/zh-Hans/experience-platform/sources/connectors/adobe-applications/analytics.html). 最多 [!UICONTROL Adobe Analytics] 字段以XDM格式带来，但其他字段尚不可用(如 [!UICONTROL 营销渠道] 维)。 |
| 将数据集元素组合到数据视图中需要多长时间？ | 最初只需几个小时，回填最近 13 个月的数据则需要几天的时间。 |
| 是否必须导入 PII 数据才能在数据之间建立连接？ | 否，您可以使用任何 ID，包括客户 ID 的哈希，该哈希不是 PII。 |

## 传统 [!UICONTROL Adobe Analytics] 组件

| 问题 | 回答 |
| --- | --- |
| 这对我们的传统 [!UICONTROL Adobe Analytics] product? | [!UICONTROL Customer Journey Analytics 是我们的下一代分析产品。]从我们的当前产品到 [!UICONTROL Customer Journey Analytics] 需要多年的协调。 有关更多信息，请查阅 [Customer Journey Analytics 功能支持](/help/getting-started/cja-aa.md)。 |
| 是否可以从 [!UICONTROL Customer Journey Analytics] 到AEP或其他解决方案？ | 目前不行。我们正在寻找新的创新方式来共享 [!UICONTROL Customer Journey Analytics] 在未来不会有如此长时间延迟的AEP。 也就是说，作为一种潜在的解决方法，您可以将查询服务的输出共享到统一用户档案。 |
| 我的旧 eVar 设置会发生了什么？ | 传统Adobe Analytics意义上的eVar、prop和事件在 [!UICONTROL Customer Journey Analytics]. 您有无限的架构元素（维度、量度、列表字段）。因此，您在数据收集过程中使用的所有属性设置现在都会在查询时应用。 |
| 我的所有会话和变量持久性设置现在位于何处？ | [!UICONTROL Customer Journey Analytic 在报告时应用所有这些设置，因此这些设置现在位于数据视图中。]对这些设置的更改现在具有追溯性，您可以使用多个数据视图来管理多个版本！ |
| 我们的现有区段/计算量度会发生什么？ | [!UICONTROL Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。]这意味着，任何现有区段或计算量度均与 [!UICONTROL Customer Journey Analytics]. |
| 如何 [!UICONTROL Customer Journey Analytics] 把手 `Uniques Exceeded` 限制？ | [!UICONTROL Customer Journey Analytics 没有唯一值限制，因此无需担心！] |
| 如果我是现有 [!DNL Data Workbench] 客户，是否可以立即转到 Customer Journey Analytics？ | 这依具体情况而定。如果您在很大程度上依赖统一客户流程 (UCP)，则需要等到我们实施拼合后再才能使用。如果您已经拥有高客户身份验证率，或者希望将所有数据放在一个位置或希望删除 eVar，则 Customer Journey Analytics 可能非常适合您。 |

## 删除数据组件的含义

在删除方面，我们关注6个组件：沙箱、模式、数据集、连接、视图和Workspace项目。 以下是有关删除其中任何组件的一些可能情况：

| 如果我…… | 这种情况…… |
| --- | --- |
| 删除 [!UICONTROL Adobe Experience Platform]? | 删除沙箱将停止向任何 [!UICONTROL Customer Journey Analytics] 与沙箱中数据集的连接。 当前，绑定到该沙箱的CJA中的连接不会自动删除。 |
| 删除模式 [!UICONTROL Adobe Experience Platform]，但不是与此模式关联的数据集？ | [!UICONTROL Adobe Experience Platform] 不允许删除具有一个或多个与其关联的模式集。 但是，具有相应权限集的管理员可以先删除数据集，然后删除模式。 |
| 删除 [!UICONTROL Adobe Experience Platform]? | 在AEP中删除数据集将停止数据从该数据集流向包含该数据集的任何连接。 来自该数据集的任何数据不会自动从关联的CJA连接中删除。 |
| 删除 [!UICONTROL Customer Journey Analytics]? | 当前，无法删除已保存的连接中的数据集。 您必须删除整个连接并结束开始。 (但是，您可以在 [!UICONTROL Adobe Experience Platform].) |
| 从数据集中删除批(在 [!UICONTROL Adobe Experience Platform])? | 如果从 [!UICONTROL Adobe Experience Platform] 数据集中，同一批将从包含该特定批的任何CJA连接中删除。  CJA在 [!UICONTROL Adobe Experience Platform]. |
| 删除批 **在被摄入时** 入 [!UICONTROL Customer Journey Analytics]? | 如果数据集中只有一个批，则该批中的数据或部分数据将不会显示在 [!UICONTROL Customer Journey Analytics]. 摄取将回滚。 例如，如果数据集中有5个批次，且删除数据集时已摄取其中3个批次，则这3个批次的数据将显示在 [!UICONTROL Customer Journey Analytics]. |
| 删除 [!UICONTROL Customer Journey Analytics]? | 将显示一条错误消息：<ul><li>为已删除的连接创建的任何数据视图将不再工作。</li><li> 同样，任何依赖于已删除连接中的数据视图的Workspace项目都将停止工作。</li></ul> |
| 删除视图 [!UICONTROL Customer Journey Analytics]? | 将显示一条错误消息，指示任何依赖此已删除数据视图的Workspace项目将停止工作。 |
| 删除 [!UICONTROL Customer Journey Analytics]? | 您可以重新创建项目，也可以使用补救方法恢复项目。 只需转到 [!UICONTROL “管理员”>“日志”>“使用和访问日志”]，查找已删除的项目并复制其ID。 然后打开任何Workspace项目，并使用复制的URL更新ID。 然后保存项目。 |
