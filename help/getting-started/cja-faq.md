---
title: Customer Journey Analytics 常见问题解答
description: Customer Journey Analytics - 常见问题解答。
translation-type: tm+mt
source-git-commit: 69f9154387ec11e9b1ec6f867ebab6d556451a9a

---


# 常见问题解答

| 问题 | 回答 |
|---|---|
| **先决条件** |  |
| Do you need Device Graph or Device Coop for [!UICONTROL Customer Journey Analytics]? | No, Private Device Graph or Device Coop are not required for [!UICONTROL Customer Journey Analytics]. 事实上，目前还不支持这两个功能。 |
| Do you need Experience Cloud ID (ECID) for [!UICONTROL Customer Journey Analytics]? | No, [!UICONTROL Customer Journey Analytics] supports any ID in a dataset, whether that&#39;s ECID or any other ID you choose. |
| 如果在执行 Customer Journey Analytics 之前需要对数据进行 ETL（提取、转换、加载）操作，该怎么办？ | 现在，如果在将数据放入 AEP 之前需要对数据进行转换，则需要与 ETL 合作伙伴（Unifi 或 Informatica）合作。如果在摄取数据后需要执行 ETL 操作，AEP 查询服务将为您提供一些有限的选项。 |
| **拼合** |  |
| Can [!UICONTROL Customer Journey Analytics] &quot;stitch&quot; across devices or across datasets? | 不可以。[!UICONTROL Customer Journey Analytics] 是“自带ID”分析系统。 我们正在努力策划一个良好的拼合方案。 |
| 是否支持从匿名行为到实名行为的拼合？ | 否，目前尚不支持。 |
| **将数据导入[!UICONTROL Customer Journey Analytics]** |  |
| What is the expected latency for [!UICONTROL Customer Journey Analytics] on [!UICONTROL Experience Platform]? | <ul><li>在正常负载下：少于 60 分钟 <br>**注意：**如果通过管道的数据流量异常高，可能需要 24 小时。</li><li>回填数据（最多 100 亿个事件）：少于 4 周</li></ul> |
| How do you connect online data to offline data in [!UICONTROL Customer Journey Analytics]? | [!UICONTROL Customer Journey Analytics] 是“自带ID”分析系统。 As long as the person ID matches between datasets, [!UICONTROL Customer Journey Analytics] can connect segments, attribution, flow, fallout, etc. 跨数据集。 |
| 如何将离线数据导入 Customer Journey Analytics？ | 客户必须先将任何数据引入Experience Platform，然后才能将其与客户旅程分析结合使用。 Experience Platform 的数据入门团队可以根据需要为客户提供建议或咨询。 |
| 如何将 Analytics 数据载入到 Customer Journey Analytics 中？ | 分析数据可以通过Analytics Data Connector连接到Experience Platform。 大多数 Analytics 字段以 XDM 格式提供，但其他字段尚不可用（如“营销渠道”维度）。 |
| 将数据集元素组合到数据视图中需要多长时间？ | 一开使只需几个小时，回填最近 13 个月的数据需要几天时间。 |
| 是否必须导入 PII 数据才能在数据之间建立连接？ | 否，您可以使用任何 ID，包括客户 ID 的哈希，该哈希不是 PII。 |
| **传统 Analytics 组件** |  |
| 这对我们的传统 Adobe Analytics 产品意味着什么？ | Customer Journey Analytics 是我们的下一代分析产品。从当前的产品演变到 Customer Journey Analytics，将需要数年的时间和大量的协调工作。这一版本是演变过程中的一个重要步骤。 |
| 我是否可以将区段从 Customer Journey Analytics 共享到 AEP 或其他解决方案？ | 目前不行。我们正在寻找新的创新方式，以便将来将区段从 Customer Journey Analytics 共享到 AEP，并且不会有这么长的延迟。也就是说，作为一种潜在的解决方法，您可以将查询服务的输出共享到统一用户档案。 |
| 我的旧 eVar 设置会发生了什么？ | 传统 Adobe Analytics 中的 eVar、prop 和事件在 Customer Journey Analytics 中已不复存在。您有无限的架构元素（维度、量度、列表字段）。因此，您在数据收集过程中使用的所有属性设置现在都会在查询时应用。 |
| 我的所有会话和变量持久性设置现在位于何处？ | Customer Journey Analytic 在报告时应用所有这些设置，因此这些设置现在位于数据视图中。对这些设置的更改现在具有追溯性，您可以使用多个数据视图来管理多个版本！ |
| 我们的现有区段/计算量度会发生什么？ | Customer Journey Analytics 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。这意味着，任何现有区段或计算量度都与 Customer Journey Analytics 不兼容。 |
| Customer Journey Analytics 如何处理 `Uniques Exceeded` 限制？ | Customer Journey Analytics 没有唯一值限制，因此无需担心！ |
| 如果我是现有 [!DNL Data Workbench] 客户，是否可以立即转到 Customer Journey Analytics？ | 这依具体情况而定。如果您在很大程度上依赖统一客户流程 (UCP)，则需要等到我们实施拼合后再才能使用。如果您已经拥有高客户身份验证率，或者希望将所有数据放在一个位置或希望删除 eVar，则 Customer Journey Analytics 可能非常适合您。 |

