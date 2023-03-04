---
title: Customer Journey Analytics 常见问题解答
description: Customer Journey Analytics - 常见问题解答。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
source-git-commit: dac10a1e4848514661bf06fe71d233da6f9aa878
workflow-type: tm+mt
source-wordcount: '2135'
ht-degree: 98%

---

# 常见问题解答

[!UICONTROL Customer Journey Analytics] (CJA) 是我们的新一代分析产品。以下是关于 CJA 的常见问题解答。有关更多信息，请查阅 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。

## 1. 先决条件 {#prerequisites}

+++**[!UICONTROL Customer Journey Analytics] 是否需要[!UICONTROL 专用设备图形]或[!UICONTROL 设备协作]？**

不需要，[!UICONTROL Customer Journey Analytics] 不需要[!UICONTROL 专用设备图形]或[!UICONTROL 设备协作]。事实上，目前还不支持这两个功能。

+++


+++**[!UICONTROL Customer Journey Analytics] 是否需要 [!UICONTROL Experience Cloud ID] (ECID)？**

不需要，[!UICONTROL Customer Journey Analytics] 支持数据集内的任何 ID，无论该 ID 是 [!UICONTROL ECID] 还是您选择的任何其他 ID。

+++


+++**如果在执行 [!UICONTROL Customer Journey Analytics] 之前需要对数据进行 ETL（提取、转换、加载）操作，该怎么办？**

Customer Journey Analytics 包括[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=zh-Hans)功能，可在将数据放入 Adobe Experience Platform 数据湖之前转换数据。如果您在数据被摄取后需要 ETL，[Adobe Experience Platform 查询服务](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=zh-Hans#queries)会提供一些有限选项，但可能额外收费。

+++


## 2. 拼合数据（跨渠道分析） {#stitching}

+++**[!UICONTROL Customer Journey Analytics] 是否可以跨设备或跨数据集进行“拼合”？**

支持。[!UICONTROL Customer Journey Analytics] 具有一个称为[跨渠道分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hans) (CCA) 的拼合解决方案，通过它可重新生成数据集的人员 ID 的密钥，而这样可无缝地组合多个数据集。

+++


+++**是否支持从匿名行为到实名行为的拼合？**

支持。[跨渠道分析](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hans)查看来自已通过和未通过身份验证的会话的用户数据来生成拼合 ID。

+++


+++**CCA 中如何进行“重放”？**

CCA 根据已学到的唯一标识符“回放”数据。重放导致新设备连接并被拼合。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/replay.html?lang=zh-Hans#step-1%3A-live-stitching)

+++


+++**如何在 CCA 中拼合历史数据（回填）？**

首次启用时，Adobe 提供追溯到上月初（最多 60 天）的拼合数据的回填。为实现此回填，当时的未拼合数据中必须存在过渡 ID。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/cca/overview.html?lang=zh-Hans#enable-cross-channel-analytics)

+++


+++**未拼合的配置文件数据集记录的预期行为是什么？**

**示例场景**：使用 `CRMid` 作为人员 ID 在 CJA 连接中联接 2 个数据集。一个是 Web 事件数据集，所有记录中都包含 `CRMid`。另一个数据集是 CRM 配置文件数据集。CRM 数据集中 40% 的数据都在 Web 事件数据集中有 `CRMid`。另外 60% 的数据不在 Web 事件数据集中 - 这些记录是否显示在 Analysis Workspace 的报告中？<p> **回答**：不带关联的事件的配置文件行存储在 CJA 中。但是，您无法在 Analysis Workspace 中查看它们，直到与该 ID 关联的事件出现。

+++

## 3. 将数据载入到 [!UICONTROL Customer Journey Analytics] {#ingest}

+++**是否可以将来自不同 [!UICONTROL Adobe Experience Platform] 沙盒的数据合并到一个 [!UICONTROL Customer Journey Analytics] 连接中？**

不能，您不能跨沙盒访问数据。您只能合并位于同一沙盒中的数据集。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans#select-sandbox-and-datasets)

+++


+++**如何在 [!UICONTROL Customer Journey Analytics] 中将在线数据与离线数据关联起来？**

只要数据集之间的人员 ID 匹配，[!UICONTROL Customer Journey Analytics] 就可以跨数据集连接筛选器、归因、流量、流失等。

+++


+++**如何将离线数据导入 [!UICONTROL Customer Journey Analytics]？**

您拥有的 Customer Journey Analytics 权利允许您将数据摄取到 Experience Platform。然后，您可以在 [!UICONTROL Customer Journey Analytics] 中创建到该数据和数据视图的连接，以在 Analysis Workspace 中报告。如果需要，Experience Platform 的数据载入团队可以为您提供建议或咨询。

+++


+++**如何将 [!UICONTROL Adobe Analytics] 数据载入到 [!UICONTROL Customer Journey Analytics]？**

[!UICONTROL Adobe Analytics] 数据可以通过 [Adobe Analytics Source Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans) 连接到 Experience Platform。大多数 [!UICONTROL Adobe Analytics] 字段以 XDM 格式转入，但其他字段尚不可用。

+++


+++**将数据集元素组合到数据视图中需要多长时间？**

最初只需几个小时，回填最近 13 个月的数据则需要几天的时间。

+++


+++**是否必须导入 PII 数据才能在数据之间建立连接？**

否，您可以使用任何 ID，包括客户 ID 的哈希，该哈希不是 PII。

+++


+++**将过去或未来日期/时间戳摄取到 CJA 事件数据集内有什么限制？**

<ul><li>关于过去日期/时间戳：最多 10 年前的事件数据。</li><li>关于未来日期/时间戳（预测）：最多未来 1 个月。</li></ul>

+++


## 4. 延迟注意事项 {#latency}

>[!NOTE]
>CJA 中没有固定的数据大小，因此 Adobe 无法承诺标准摄取时间。我们正在积极地努力通过新的更新和摄取优化来缩短这些延迟。

+++**在 [!UICONTROL Adobe Experience Platform] 上，[!UICONTROL Customer Journey Analytics] 的预期滞后时间是多少？**

<ul><li>实时数据或事件：当数据在 AEP 中可用后，在 90 分钟内处理和摄取。（批次大小 &gt; 500 万行：超过 90 分钟。）</li><li>少量回填 - 例如，查找 100 万行的数据集：7 天内<li>大量回填 - 例如，5000 亿行：30 天</li></ul>

+++

## 5. 设置[!UICONTROL 连接]数据保留的时段 {#data-retention}

通过[**[!UICONTROL 启用滚动数据窗口&#x200B;]**设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-Hans#create-connection)，可将 CJA 数据保留定义为按月（3 个月、6 个月等等）计的滚动窗口。在[!UICONTROL 连接]级别而非[!UICONTROL 数据集]级别设置它。数据保留基于事件数据集时间戳并且仅适用于事件数据集。由于没有适用的时间戳，因此个人资料或查找数据集没有数据保留设置。

主要好处是，您只需存储或报告适用且有用的数据，并且可删除不再有用的旧数据。它可以帮助您保持在合同限制范围内，并减少超出预期成本的风险。

## 6. 删除数据组件的后果 {#deletion}

在数据删除方面，我们关注这 6 类组件：沙盒、架构、数据集、连接、数据视图和 Workspace 项目。下面是关于删除其中任何一个组件的一些可能情景：

| 如果您... | 产生的后果... |
| --- | --- |
| 删除 [!UICONTROL Adobe Experience Platform] 中的沙盒 | 如果删除沙盒，则将阻止数据流向与该沙盒中的数据集关联的 [!UICONTROL Customer Journey Analytics] 连接。目前，CJA 中关联被删除沙盒的[!UICONTROL 连接]不能自动删除。 |
| 删除 [!UICONTROL Adobe Experience Platform] 中的架构，但不删除与该架构关联的数据集 | [!UICONTROL Adobe Experience Platform][!UICONTROL  不允许删除具有一个或多个关联数据集的架构。]但是，具有相应权限集的管理员可以先删除关联数据集，然后再删除架构。 |
| 删除 [!UICONTROL Adobe Experience Platform] 数据湖中的一个数据集 | 删除 AEP 数据湖中的某个数据集将阻止数据从该数据集流向包括该数据集的任何 CJA 连接。来自该数据集的任何数据都会自动从关联的 CJA 连接中删除。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据集 | 请联系您的Adobe客户团队，以启动删除已保存连接中的数据集的过程。 |
| 从数据集中删除批次（在 [!UICONTROL Adobe Experience Platform] 中） | 如果从 [!UICONTROL Adobe Experience Platform] 数据集中删除了某个批次，则会从包含该特定批次的所有 CJA 连接中删除该批次。CJA 会收到批次已在 [!UICONTROL Adobe Experience Platform] 中删除的通知。 |
| **批次被摄取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 的同时删除批次 | 如果数据集中只有一个批次，则该批次中只会有部分数据或没有任何数据显示在 [!UICONTROL Customer Journey Analytics] 中。系统将回滚该摄取操作。例如，如果数据集中共有 5 个批次，且在删除该数据集时已摄取其中 3 个批次，那么这 3 个批次中的数据将显示在 [!UICONTROL Customer Journey Analytics] 中。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的连接 | 将显示一条错误消息，指示：<ul><li>为已删除的连接创建的所有数据视图都将不再起作用。</li><li> 同样地，任何依赖于已删除连接中的数据视图的工作区项目都将停止运行。</li></ul> |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据视图 | 将显示一条错误消息，指示所有依赖于这个已删除数据视图的 Workspace 项目都将停止运行。 |

## 7. 在 CJA 中合并报告包时的注意事项 {#merge-reportsuite}

如果打算通过 [Adobe Analytics 源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-Hans)引入 Adobe Analytics 数据，请在合并 2 个或更多 Adobe Analytics 报告包时考虑以下这些后果。

| 问题 | 注意事项 |
| --- | --- |
| 变量 | [!UICONTROL eVars] 等变量在报告包间可能不一致。例如，报告包 1 中的 eVar1 可能指向&#x200B;**[!UICONTROL 页面]**。在报告包 2 中，eVar1 可能指向&#x200B;**[!UICONTROL 内部活动]**，导致报告变得混乱而又不准确。 |
| [!UICONTROL 会话]数和[!UICONTROL 人员]数 | 在报告包间将为其去重。因此，这些数量可能不一致。 |
| 量度去重 | 如果有多行的交易 ID（例如，[!UICONTROL 购买 ID]）相同，请为指标的实例（例如，[!UICONTROL 订单]）去重。这样可防止过度计算关键指标。因此，[!UICONTROL 订单]等指标可能不在报告包间累加。 |
| 货币 | CJA 中尚不支持货币转换。如果尝试合并的报告包使用不同的基础货币，则可能会出现问题。 |
| [!UICONTROL 持久性] | [持久性](../data-views/component-settings/persistence.md)作用于各个报告包，它影响[!UICONTROL 筛选器]、[!UICONTROL 归因]等等。数值可能无法正确地累加。 |
| [!UICONTROL 分类] | 在合并报告包时，不会自动为[!UICONTROL 分类]去重。将多个分类文件合并为一个[!UICONTROL 查找]数据集时，可能会遇到问题。 |


## 8. 传统 [!UICONTROL Adobe Analytics] 组件


+++**我能否将来自[!UICONTROL 的]过滤器[!UICONTROL （]区段[!DNL Customer Journey Analytics]）共享/发布到 Experience Platform Unified Profile 或其他 Experience Cloud 应用程序？**

还不能，但我们正在努力提供这种功能。

+++


+++**我之前的 [!UICONTROL eVar] 设置发生了什么变化？**

[!UICONTROL Customer Journey Analytics] 中不再存在传统 Adobe Analytics 意义上的 [!UICONTROL eVar]、[!UICONTROL 属性]和[!UICONTROL 事件]。您有无限的架构元素（维度、量度、列表字段）。因此，您在数据收集过程中使用的所有属性设置现在都会在查询时应用。

+++


+++**我的所有会话和变量持久性设置现在位于何处？**

[!UICONTROL Customer Journey Analytics] 在报告时应用所有这些设置，因此这些设置现在位于数据视图中。对这些设置的更改现在具有追溯性，您可以使用多个数据视图来管理多个版本！

+++


+++**我们的现有区段/计算量度会发生什么？**

[!UICONTROL Customer Journey Analytics] 不再使用 eVar、prop 或事件，而是使用任何 AEP 架构。这意味着，任何现有区段或计算量度都与 [!UICONTROL Customer Journey Analytics] 不兼容。

+++


+++**[!UICONTROL Customer Journey Analytics] 如何处理 `Uniques Exceeded` 限制？**

[!UICONTROL Customer Journey Analytics] 没有唯一值限制，因此无需担心！

+++


+++**如果我是现有 [!DNL Data Workbench] 客户，是否可以立即转到 [!UICONTROL Customer Journey Analytics]？**

这取决于您的用例 - 请与您的 Adobe 客户团队合作。您的当前用例可能已经非常适合 Customer Journey Analytics！

+++

## 9. 估计连接大小 {#estimate-size}

请参阅[估算和管理使用情况](/help/admin/estimate-usage.md)。

## 10. 关于使用过量 {#overage}

Adobe 定期监控和执行使用限制。“数据行数”表示可供在 Customer Journey Analytics 中分析的数据的每日平均行数。

例如，假设您的合同授权您拥有 100 万行数据。假设在使用 Customer Journey Analytics 的第 1 天，您上传了 200 万行数据。在第 2 天，您会删除 100 万行，并在剩余的许可证期限内将使用量保持在承诺的最大值（即 100 万行数据）。根据您的合同条款，由于您超出了“数据行”许可证授权，因此您在第 1 天仍可能会收取按比例分摊的过度使用费用。

## 11. 诊断数据差异 {#discrepancies}

在某些情况下，您可能会注意到您的连接所摄取的事件总数与 [!UICONTROL Adobe Experience Platform] 中数据集的行数存在差异。在此示例中，“B2B Impression”数据集的行数为 7650，而该数据集在 [!UICONTROL Adobe Experience Platform] 中的行数为 3830。导致差异的原因有多种，可采取以下步骤进行诊断：

1. 按 **[!UICONTROL Platform 数据集 ID]** 划分此维度，此时，您会发现存在两个大小相同但 **[!UICONTROL Platform 数据集 ID]** 不同的数据集。每个数据集都包含 3825 条记录。这意味着由于缺少人员 ID 或缺少时间戳，[!UICONTROL Customer Journey Analytics] 忽略了 5 条记录：

   ![划分](assets/data-size2.png)

2. 此外，如果我们登入 [!UICONTROL Adobe Experience Platform]，便会发现不存在 ID 为“5f21c12b732044194bffc1d0”的数据集，这表示在最初创建连接时，从 [!UICONTROL Adobe Experience Platform] 中删除了此特定数据集。不过，之后又将此数据集重新添加到 Customer Journey Analytics 中，但 [!UICONTROL Adobe Experience Platform] 生成了一个不同的 [!UICONTROL Platform 数据集 ID]。

有关更多信息，请参阅在 [!UICONTROL Customer Journey Analytics] 和 [!UICONTROL Adobe Experience Platform] 中[删除数据集和连接的后果](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-Hans#implications-of-deleting-data-components)。
