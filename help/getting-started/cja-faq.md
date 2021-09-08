---
title: Customer Journey Analytics 常见问题解答
description: Customer Journey Analytics — 常见问题解答。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
source-git-commit: af683f97284ed24c3285a5819217ad329d5a8067
workflow-type: tm+mt
source-wordcount: '1569'
ht-degree: 87%

---

# 常见问题解答

[!UICONTROL Customer Journey Analytics] (CJA) 是我们的新一代分析产品。以下是关于 CJA 的常见问题解答。有关更多信息，请查阅 [Customer Journey Analytics 功能支持](/help/getting-started/cja-aa.md)。

## 1. 先决条件

| 问题 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] 是否需要[!UICONTROL 专用设备图形]或[!UICONTROL 设备协作]？ | 不需要，[!UICONTROL Customer Journey Analytics] 不需要[!UICONTROL 专用设备图形]或[!UICONTROL 设备协作]。事实上，目前还不支持这两个功能。 |
| [!UICONTROL Customer Journey Analytics] 是否需要 [!UICONTROL Experience Cloud ID] (ECID)？ | 不需要，[!UICONTROL Customer Journey Analytics] 支持数据集中的任何 ID，无论该 ID 是 [!UICONTROL ECID] 还是您选择的任何其他 ID。 |
| 如果在执行 [!UICONTROL Customer Journey Analytics] 之前需要对数据进行 ETL（提取、转换、加载）操作，该怎么办？ | Customer Journey Analytics 包括[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=zh-Hans)功能，可在将数据放入 Adobe Experience Platform 数据湖之前转换数据。如果您在数据被摄取后需要 ETL，[Adobe Experience Platform 查询服务](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=zh-Hans#queries)会提供一些有限选项，但可能额外收费。 |

{style=&quot;table-layout:auto&quot;}

## 2. 拼合数据（跨渠道分析）

| 问题 | 回答 |
| --- | --- |
| [!UICONTROL Customer Journey Analytics] 是否可以跨设备或跨数据集进行“拼合”？ | 支持。[!UICONTROL Customer Journey Analytics] 具有一个称为[跨渠道分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hans) (CCA) 的拼合解决方案，该方案允许您重新键入数据集的人员 ID，实现多个数据集的无缝组合。 |
| 是否支持从匿名行为到实名行为的拼合？ | 支持。[跨渠道分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html)查看来自已通过和未通过身份验证的会话的用户数据来生成拼合 ID。 |
| CCA 中如何进行“重放”？ | CCA 根据它所掌握的唯一标识符“重放”数据。重放导致新设备连接并被拼合。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=zh-Hans#step-1%3A-live-stitching) |
| 如何在 CCA 中拼合历史数据（回填）？ | 首次启用时，Adobe 提供追溯到上月初（最多 60 天）的拼合数据的回填。为实现此回填，当时的未拼合数据中必须存在过渡 ID。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hans#enable-cross-channel-analytics) |

{style=&quot;table-layout:auto&quot;}

## 3. 将数据载入到 [!UICONTROL Customer Journey Analytics]

| 问题 | 回答 |
| --- | --- |
| 是否可以将来自不同 [!UICONTROL Adobe Experience Platform] 沙盒的数据合并到一个 [!UICONTROL Customer Journey Analytics] 连接中？ | 不能，您不能跨沙盒访问数据。您只能合并位于同一沙盒中的数据集。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans#select-sandbox-and-datasets) |
| 在 [!UICONTROL Adobe Experience Platform] 上，[!UICONTROL Customer Journey Analytics] 的预期滞后时间是多少？ | <ul><li>在正常负载下：少于 60 分钟&#x200B;<br>**注意：**&#x200B;如果通过管道的数据流量异常高，则预期滞后时间可能会长达 24 小时。</li><li>回填数据（最多支持 13 个月的数据，不考虑数据大小）：少于 4 周</li></ul> |
| 如何在 [!UICONTROL Customer Journey Analytics] 中将在线数据与离线数据关联起来？ | 只要数据集之间的人员 ID 匹配，[!UICONTROL Customer Journey Analytics] 就可以跨数据集连接筛选器、归因、流量、流失等。。 |
| 如何将离线数据导入 [!UICONTROL Customer Journey Analytics]？ | 您拥有的 Customer Journey Analytics 权利允许您将数据摄取到 Experience Platform。然后，您可以在 [!UICONTROL Customer Journey Analytics] 中创建到该数据和数据视图的连接，以在 Analysis Workspace 中报告。如果需要，Experience Platform 的数据载入团队可以为您提供建议或咨询。 |
| 如何将 [!UICONTROL Adobe Analytics] 数据载入到 [!UICONTROL Customer Journey Analytics]？ | [!UICONTROL Adobe Analytics] 数据可以通过 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 连接到 Experience Platform。大多数 [!UICONTROL Adobe Analytics] 字段以 XDM 格式转入，但其他字段尚不可用。 |
| 将数据集元素组合到数据视图中需要多长时间？ | 最初只需几个小时，回填最近 13 个月的数据则需要几天的时间。 |
| 是否必须导入 PII 数据才能在数据之间建立连接？ | 否，您可以使用任何 ID，包括客户 ID 的哈希，该哈希不是 PII。 |

{style=&quot;table-layout:auto&quot;}

## 4. 传统 [!UICONTROL Adobe Analytics] 组件

| 问题 | 回答 |
| --- | --- |
| 我能否将来自 Customer Journey Analytics 的筛选器（区段）共享/发布到 Experience Platform Unified Profile 或其他 Experience Cloud 应用程序？ | 还不能，但我们正在努力提供这种功能。 |
| 我的旧 eVar 设置发生了什么？ | 传统 Adobe Analytics 中的 eVar、prop 和事件在 [!UICONTROL Customer Journey Analytics] 中已不复存在。您有无限的架构元素（维度、量度、列表字段）。因此，您在数据收集过程中使用的所有属性设置现在都会在查询时应用。 |
| 我的所有会话和变量持久性设置现在位于何处？ | [!UICONTROL Customer Journey Analytics] 在报告时应用所有这些设置，因此这些设置现在位于数据视图中。对这些设置的更改现在具有追溯性，您可以使用多个数据视图来管理多个版本！ |
| 我们的现有区段/计算量度会发生什么？ | [!UICONTROL Customer Journey Analytics] 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。这意味着，任何现有区段或计算量度都与 [!UICONTROL Customer Journey Analytics] 不兼容。 |
| [!UICONTROL Customer Journey Analytics] 如何处理 `Uniques Exceeded` 限制？ | [!UICONTROL Customer Journey Analytics] 没有唯一值限制，因此无需担心！ |
| 如果我是现有 [!DNL Data Workbench] 客户，是否可以立即转到 [!UICONTROL Customer Journey Analytics]？ | 这取决于您的用例 - 请与您的 Adobe 客户团队合作。您的当前用例可能已经非常适合 Customer Journey Analytics！ |

{style=&quot;table-layout:auto&quot;}

## 5. 删除数据组件的后果

在数据删除方面，我们关注这 6 类组件：沙盒、架构、数据集、连接、数据视图和 Workspace 项目。下面是关于删除其中任何一个组件的一些可能情景：

| 如果您... | 产生的后果... |
| --- | --- |
| 删除 [!UICONTROL Adobe Experience Platform] 中的沙盒 | 如果删除沙盒，则将阻止数据流向与该沙盒中的数据集关联的 [!UICONTROL Customer Journey Analytics] 连接。目前，CJA 中关联被删除沙盒的连接不能自动删除。 |
| 删除 [!UICONTROL Adobe Experience Platform] 中的架构，但不删除与该架构关联的数据集 | [!UICONTROL Adobe Experience Platform] 不允许删除具有一个或多个关联数据集的架构。但是，具有相应权限集的管理员可以先删除关联数据集，然后再删除架构。 |
| 删除 [!UICONTROL Adobe Experience Platform] 数据湖中的一个数据集 | 删除 AEP 数据湖中的某个数据集将阻止数据从该数据集流向包括该数据集的任何 CJA 连接。来自该数据集的任何数据都不会自动从关联的 CJA 连接中删除。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据集 | 当前，无法删除已保存的连接中的数据集。您必须删除整个连接，然后重新开始创建连接。（但是，如果客户购买了 CJA SKU，则可以删除 [!UICONTROL Adobe Experience Platform] 用户界面中的一个数据集。） |
| 从数据集中删除批次（在 [!UICONTROL Adobe Experience Platform] 中） | 如果从 [!UICONTROL Adobe Experience Platform] 数据集中删除了某个批次，则会从包含该特定批次的所有 CJA 连接中删除该批次。CJA 会收到批次已在 [!UICONTROL Adobe Experience Platform] 中删除的通知。 |
| **批次被摄取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 的同时删除批次 | 如果数据集中只有一个批次，则该批次中只会有部分数据或没有任何数据显示在 [!UICONTROL Customer Journey Analytics] 中。系统将回滚该摄取操作。例如，如果数据集中共有 5 个批次，且在删除该数据集时已摄取其中 3 个批次，那么这 3 个批次中的数据将显示在 [!UICONTROL Customer Journey Analytics] 中。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的连接 | 将显示一条错误消息，指示：<ul><li>为已删除的连接创建的所有数据视图都将不再起作用。</li><li> 同样地，任何依赖于已删除连接中的数据视图的工作区项目都将停止运行。</li></ul> |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据视图 | 将显示一条错误消息，指示所有依赖于这个已删除数据视图的 Workspace 项目都将停止运行。 |

## 6.在CJA中合并报表包时的注意事项

如果您计划通过[Adobe Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans)摄取Adobe Analytics数据，请在合并2个或多个Adobe Analytics报表包时考虑这些后果。

| 问题 | 注意事项 |
| --- | --- |
| 变量 | 变量（如[!UICONTROL eVars]）可能无法在报表包中排列。 例如，报表包1中的eVar1可能指向&#x200B;**[!UICONTROL Page]**。 在报表包2中，eVar1可能指向&#x200B;**[!UICONTROL 内部营销活动]**，从而导致报告混合且不准确。 |
|  会话和  句点 | 报表包中的重复数据会被删除。 因此，计数可能不匹配。 |
| 量度去重 | 如果多个行具有相同的交易ID（例如，[!UICONTROL 购买ID]），则会删除量度的重复实例（例如，[!UICONTROL Orders]）。 这可防止关键量度计数过多。 因此，诸如[!UICONTROL Orders]之类的量度可能不会在报表包之间进行累加。 |
| 货币 | CJA尚不支持货币换算。 如果您尝试合并的报表包使用不同的基本货币，则可能会出现问题。 |
| [!UICONTROL 持久性] | [](/help/data-views/persistence.md) 持久性会跨报表包扩展，这会 [!UICONTROL 影响过滤器]、 [!UICONTROL 归因]等。数字可能无法正确加总。 |
| [!UICONTROL 分类] |  合并报表包时，分类不会自动删除重复项。将多个分类文件合并到单个[!UICONTROL lookup]数据集时，可能会遇到问题。 |