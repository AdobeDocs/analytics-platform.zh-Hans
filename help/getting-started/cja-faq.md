---
title: Customer Journey Analytics 常见问题解答
description: Customer Journey Analytics - 常见问题解答。
translation-type: ht
source-git-commit: d700146427505e464df4006204f730751e315524
workflow-type: ht
source-wordcount: '824'
ht-degree: 100%

---


# 常见问题解答

## 先决条件

| 问题 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] 是否需要设备图形或设备协助？ | 不需要，[!UICONTROL Customer Journey Analytics] 不需要专用设备图形或设备协作。事实上，目前还不支持这两个功能。 |
| [!UICONTROL Customer Journey Analytics] 是否需要 Experience Cloud ID (ECID)？ | 不需要，[!UICONTROL Customer Journey Analytics] 支持数据集中的任何 ID，无论该 ID 是 ECID 还是您选择的任何其他 ID。 |
| 如果在执行 Customer Journey Analytics 之前需要对数据进行 ETL（提取、转换、加载）操作，该怎么办？ | 现在，如果在将数据放入 AEP 之前需要对数据进行转换，则需要与 ETL 合作伙伴（Unifi 或 Informatica）合作。如果在摄取数据后需要执行 ETL 操作，AEP 查询服务将为您提供一些有限的选项。 |

## 拼合

| 问题 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] 是否可以跨设备或跨数据集进行“拼合”？ | 不可以。[!UICONTROL Customer Journey Analytics] 是一个“自带 ID”分析系统。我们正在努力策划一个良好的拼合方案。 |
| 是否支持从匿名行为到实名行为的拼合？ | 否，目前尚不支持。 |

## 将数据载入 [!UICONTROL Customer Journey Analytics]

| 问题 | 回答 |
| --- | --- |
| 能否将不同 Experience Platform 沙盒中的数据合并到一个 CJA 连接中？ | 不能，您不能跨沙盒访问数据。您只能合并位于同一沙盒中的数据集。[了解更多...](https://docs.adobe.com/content/help/zh-Hans/analytics-platform/using/cja-connections/create-connection.html#select-sandbox-and-datasets) |
| 在 [!UICONTROL Experience Platform] 上，[!UICONTROL Customer Journey Analytics] 的预期滞后时间是多少？ | <ul><li>在正常负载下：少于 60 分钟&#x200B;<br>**注意：**&#x200B;如果通过管道的数据流量异常高，则预期滞后时间可能会长达 24 小时。</li><li>回填数据（最多支持 13 个月的数据，不考虑数据大小）：少于 4 周</li></ul> |
| 如何在 [!UICONTROL Customer Journey Analytics] 中将在线数据与离线数据关联起来？ | [!UICONTROL Customer Journey Analytics] 是一个“自带 ID”分析系统。只要数据集之间的人员 ID 匹配，[!UICONTROL Customer Journey Analytics] 就可以跨数据集连接区段、归因、流量、流失等。 |
| 如何将离线数据导入 Customer Journey Analytics？ | 客户必须先将数据导入到 Experience Platform，然后才能在 Customer Journey Analytics 中使用。如果需要，Experience Platform 的数据载入团队可以为您提供建议或咨询。 |
| 如何将 Analytics 数据载入到 Customer Journey Analytics 中？ | Analytics 数据可以通过 [Analytics Data Connector](https://docs.adobe.com/content/help/zh-Hans/experience-platform/sources/connectors/adobe-applications/analytics.html) 连接到 Experience Platform。大多数 Analytics 字段以 XDM 格式提供，但其他字段尚不可用（如“营销渠道”维度）。 |
| 将数据集元素组合到数据视图中需要多长时间？ | 最初只需几个小时，回填最近 13 个月的数据则需要几天的时间。 |
| 是否必须导入 PII 数据才能在数据之间建立连接？ | 否，您可以使用任何 ID，包括客户 ID 的哈希，该哈希不是 PII。 |

## 传统 Analytics 组件

| 问题 | 回答 |
| --- | --- |
| 这对我们的传统 Adobe Analytics 产品意味着什么？ | Customer Journey Analytics 是我们的下一代分析产品。从当前的产品演变到 Customer Journey Analytics，需要经年累月的时间以及从事大量的协调工作。有关更多信息，请查阅 [Customer Journey Analytics 功能支持](/help/getting-started/cja-aa.md)。 |
| 我是否可以将区段从 Customer Journey Analytics 共享到 AEP 或其他解决方案？ | 目前不行。我们正在寻找新的创新方式，以便将来将区段从 Customer Journey Analytics 共享到 AEP，并且不会有这么长的延迟。也就是说，作为一种潜在的解决方法，您可以将查询服务的输出共享到统一用户档案。 |
| 我的旧 eVar 设置会发生了什么？ | 传统 Adobe Analytics 中的 eVar、prop 和事件在 Customer Journey Analytics 中已不复存在。您有无限的架构元素（维度、量度、列表字段）。因此，您在数据收集过程中使用的所有属性设置现在都会在查询时应用。 |
| 我的所有会话和变量持久性设置现在位于何处？ | Customer Journey Analytic 在报告时应用所有这些设置，因此这些设置现在位于数据视图中。对这些设置的更改现在具有追溯性，您可以使用多个数据视图来管理多个版本！ |
| 我们的现有区段/计算量度会发生什么？ | Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。这意味着，任何现有区段或计算量度都与 Customer Journey Analytics 不兼容。 |
| Customer Journey Analytics 如何处理 `Uniques Exceeded` 限制？ | Customer Journey Analytics 没有唯一值限制，因此无需担心！ |
| 如果我是现有 [!DNL Data Workbench] 客户，是否可以立即转到 Customer Journey Analytics？ | 这依具体情况而定。如果您在很大程度上依赖统一客户流程 (UCP)，则需要等到我们实施拼合后再才能使用。如果您已经拥有高客户身份验证率，或者希望将所有数据放在一个位置或希望删除 eVar，则 Customer Journey Analytics 可能非常适合您。 |
