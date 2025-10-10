---
title: Customer Journey Analytics 常见问题解答
description: Customer Journey Analytics - 常见问题解答。
exl-id: 778ed2de-bc04-4b09-865e-59e386227e06
solution: Customer Journey Analytics
feature: FAQ
role: User
source-git-commit: 220ebd7dbc3fa75d221690cd6e5828bd94395434
workflow-type: tm+mt
source-wordcount: '2580'
ht-degree: 100%

---

# 常见问题解答

Adobe Customer Journey Analytics 是下一代分析产品。本文提供有关 Customer Journey Analytics 的常见问题解答。有关更多信息，请查阅 [Customer Journey Analytics 功能支持](/help/getting-started/aa-vs-cja/cja-aa.md)。

## &#x200B;1. 先决条件 {#prerequisites}

+++**[!UICONTROL Customer Journey Analytics] 是否需要 [!UICONTROL 专用设备图形] 或 [!UICONTROL 设备协作]？**

不需要，[!UICONTROL Customer Journey Analytics] 不需要[!UICONTROL 专用设备图形]或[!UICONTROL 设备协作]。事实上，目前还不支持这两个功能。

+++


+++**[!UICONTROL Customer Journey Analytics] 是否需要 [!UICONTROL Experience Cloud ID] (ECID)？**

不需要，[!UICONTROL Customer Journey Analytics] 支持数据集内的任何 ID，无论该 ID 是 [!UICONTROL ECID] 还是您选择的任何其他 ID。

+++


+++**如果在执行 [!UICONTROL Customer Journey Analytics] 之前需要对数据进行 ETL（提取、转换、加载）操作，该怎么办？**

Customer Journey Analytics 包括[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/api/overview.html?lang=zh-hans)功能以帮助转换您的数据，然后再将其放入 Adobe Experience Platform 数据湖。如果您在已摄取数据后需要 ETL，则 [Adobe Experience Platform Query Service](https://experienceleague.adobe.com/docs/platform-learn/tutorials/queries/understanding-query-service.html?lang=zh-hans#queries) 提供一些有限的选项，但可能额外收费。

+++


## &#x200B;2. 拼合数据 {#stitching}

+++**[!UICONTROL Customer Journey Analytics] 是否可以跨设备或跨数据集进行“拼合”？**

是的。[!UICONTROL Customer Journey Analytics ]具有[拼合](../stitching/overview.md)功能，该功能适用于数据集中经过身份验证和未经身份验证的事件。这样拼合可将完全不同的记录解析为单个经过拼合的 ID，以供在人员级别进行跨设备分析。此外，在[连接](/help/connections/overview.md)内的数据集间使用公共命名空间 ID（个人 ID）时，您可对在人员级别“拼合”的多个数据集的无缝组合运行分析。

+++


+++**是否支持从匿名行为到实名行为的拼合？**

是的。[拼合](../stitching/overview.md)时会同时考虑来自经过身份验证和未经身份验证的会话的用户数据，以生成拼合 ID。

+++


+++**拼合时如何进行“重放”？**

拼合时会根据其发现的唯一标识符“重播”数据。重播的目标是从同时已识别的设备中拼合最初未经身份验证的事件。[了解详情](../stitching/overview.md)

+++


+++**如何拼合历史数据（回填）？**

首次开启时，Adobe 会提供一个回填的拼合数据，这些数据可以追溯到您选择的时间（最多可达 25 个月，具体取决于您所享有的 Customer Journey Analytics 包）。为实现此回填，当时的未拼合数据中必须存在过渡 ID。[了解详情](../stitching/overview.md)

+++


+++**未拼合的轮廓数据集记录的预期行为是什么？**

**示例场景**：通过使用 `CRMid` 作为人员 ID，您在 Customer Journey Analytics 连接中连接两个数据集。一个是 Web 事件数据集，所有记录中都包含 `CRMid`。另一个数据集是 CRM 轮廓数据集。CRM 数据集中 40% 的数据都在 Web 事件数据集中有 `CRMid`。Web 事件数据集中不存在另外 60% - 这些记录是否出现在 Analysis Workspace 的报告中？<p> **回答**：不带关联的事件的轮廓行存储在 Customer Journey Analytics 中。但是，您无法在 Analysis Workspace 中查看它们，直到与该 ID 关联的事件出现。

+++

## &#x200B;3. 将数据载入到 [!UICONTROL Customer Journey Analytics] {#ingest}

+++**是否可以将来自不同 [!UICONTROL Adobe Experience Platform] 沙盒的数据合并到一个 [!UICONTROL Customer Journey Analytics] 连接中？**

不能，您不能跨沙盒访问数据。您只能合并位于同一沙盒中的数据集。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=zh-hans#select-sandbox-and-datasets)

+++


+++**如何在 [!UICONTROL Customer Journey Analytics] 中将在线数据与离线数据关联起来？**

只要不同数据集之间的人员 ID 一致，[!UICONTROL Customer Journey Analytics] 就可以跨数据集连接区段、归因、流量、流失等。

+++


+++**如何将离线数据导入 [!UICONTROL Customer Journey Analytics]？**

您拥有的 Customer Journey Analytics 权利允许您将数据摄取到 Experience Platform。然后，您可以在 [!UICONTROL Customer Journey Analytics] 中创建到该数据和数据视图的连接，以在 Analysis Workspace 中报告。如果需要，Experience Platform 的数据载入团队可以为您提供建议或咨询。

+++


+++**如何将 [!UICONTROL Adobe Analytics] 数据载入到 [!UICONTROL Customer Journey Analytics]？**

[!UICONTROL Adobe Analytics] 数据可以通过 [Analytics source connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html?lang=zh-hans) 连接到 Experience Platform。大多数 [!UICONTROL Adobe Analytics] 字段以 XDM 格式转入，但其他字段尚不可用。

+++


+++**将数据集元素组合到数据视图中需要多长时间？**

最初只需几个小时，回填最近 13 个月的数据则需要几天的时间。

+++


+++**是否必须导入 PII 数据才能在数据之间建立连接？**

否，您可以使用任何 ID，包括客户 ID 的哈希，该哈希不是 PII。

+++


+++**将过去或未来日期/时间戳摄取到 Customer Journey Analytics 事件数据集中有什么限制？**

* 关于过去日期/时间戳：最多存在过去十年的事件数据。
* 关于未来日期/时间戳：最多存在未来一个月的事件数据（预测）。

+++


## &#x200B;4. 延迟注意事项 {#latency}

>[!NOTE]
>
>Customer Journey Analytics 中没有固定的数据大小，因此 Adobe 无法承诺标准摄取时间。Adobe 正在积极地努力通过新的更新和摄取优化而缩短这些延迟。

* 实时数据或事件：一旦数据在 Adobe Experience Platform 中可用，将在 90 分钟内处理并导入。（批量大小 > 5000 万行：超过 90 分钟。）如果启用了拼接，导入可能需要长达 4 小时。有关详细信息，请参阅[安全防护](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/technotes/guardrails)。
* 少量回填：七天内
* 大量回填：30 天内

Adobe 最近改变了在 Customer Journey Analytics 中处理数据的方式：

* “当前”天的事件数据以实时数据的形式流入。任何事件时间早于前一天晚上 11:59:59 点（23:59:59）的数据都将被视为回填。
* 将时间戳为大于 24 小时前的任何事件数据（即使它与更新的数据属于同一批次）视为回填，并以更低的优先级摄取这些数据。

## &#x200B;5. 设置[!UICONTROL 连接]数据保留的滚动时段 {#data-retention}

通过[**[!UICONTROL 启用滚动数据时段&#x200B;]**设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#create-connection)，可将 Customer Journey Analytics 数据保留定义为按月（三个月、六个月等）计的滚动时段。在[!UICONTROL 连接]级别而非[!UICONTROL 数据集]级别设置它。数据保留基于事件数据集时间戳并且仅适用于事件数据集。由于没有适用的时间戳，因此轮廓或查找数据集没有数据保留设置。

主要好处是，您只需存储或报告适用且有用的数据，并且可删除不再有用的旧数据。它可以帮助您保持在合同限制范围内，并减少超出预期成本的风险。

## &#x200B;6. 删除数据组件的后果 {#deletion}

对于数据删除，您应关注六类组件：沙盒、架构、数据集、连接、数据视图和 Workspace 项目。下面是关于删除其中任何一个组件的一些可能情景：

| 如果您... | 产生的后果... |
| --- | --- |
| 删除 [!UICONTROL Adobe Experience Platform] 中的沙盒 | 删除沙盒将阻止数据流向任何与该沙盒中的数据集建立的 [!UICONTROL Customer Journey Analytics] 连接。与此已删除的沙盒相关的连接、数据视图、量度和维度也将被删除。 | |
| 删除 [!UICONTROL Adobe Experience Platform] 中的架构，但不删除与该架构关联的数据集 | [!UICONTROL Adobe Experience Platform] 不允许删除具有一个或多个关联 [!UICONTROL 数据集] 的 [!UICONTROL 架构]。但是，具有相应权限集的管理员可以先删除关联数据集，然后再删除架构。 |
| 删除 [!UICONTROL Adobe Experience Platform] 数据湖中的数据集 | 删除 Adobe Experience Platform 数据湖中的数据集将阻止数据从该数据集流向任何包括该数据集的 Customer Journey Analytics 连接。自动从关联的 Customer Journey Analytics 连接删除来自该数据集的任何数据。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据集 | 请联系您的 Adobe 帐户团队，以启动删除已保存连接中数据集的过程。 |
| 从数据集中删除批次（在 [!UICONTROL Adobe Experience Platform] 中） | 如果从 [!UICONTROL Adobe Experience Platform] 数据集删除了批次，则从任何包含该特定批次的 Customer Journey Analytics 连接删除同一批次。Customer Journey Analytics 会接收到批次已在 [!UICONTROL Adobe Experience Platform] 中删除的通知。 |
| **将批次摄取**&#x200B;到 [!UICONTROL Customer Journey Analytics] 中时删除该批次 | 如果数据集中只有一个批次，则没有来自该批次的数据或来自该批次的部分数据出现在 [!UICONTROL Customer Journey Analytics] 中。并且回滚该摄取。例如，如果数据集中有 5 个批次，而在删除该数据集时已摄取其中 3 个批次，则来自这 3 个批次的数据出现在 [!UICONTROL Customer Journey Analytics] 中。 |
| 删除 [!UICONTROL Customer Journey Analytics] 中的连接 | 出现错误消息，其中指示：<ul><li>任何为已删除的连接创建的数据视图都将不再起作用。</li><li> 同样地，任何依赖于已删除的连接中的数据视图的 Workspace 项目都停止运行。</li></ul> |
| 删除 [!UICONTROL Customer Journey Analytics] 中的数据视图 | 一条错误消息指示任何依赖于这个已删除的数据视图的 Workspace 项目都将停止运行。 |

## &#x200B;7. 在 Customer Journey Analytics 中合并报告包时的注意事项 {#merge-reportsuite}

如果打算通过 [Adobe Analytics 源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/analytics.html)摄取 Adobe Analytics 数据，请在合并两个或更多 Adobe Analytics 报告包时考虑以下这些后果。

| 问题 | 注意事项 |
| --- | --- |
| 变量 | [!UICONTROL eVars] 等变量在报告包间可能不一致。例如，报告包 1 中的 eVar1 可能指向 **[!UICONTROL 页面]**。在报告包 2 中，eVar1 可能指向 **[!UICONTROL 内部活动]**，导致报告变得混乱而又不准确。 |
| [!UICONTROL 会话]数和[!UICONTROL 人员]数 | 在报告包间将为其去重。因此，这些数量可能不一致。 |
| 量度去重 | 如果有多行的交易 ID（例如，[!UICONTROL 购买 ID]）相同，请为量度的实例（例如，[!UICONTROL 订单]）去重。这样可防止过度计算关键量度。因此，[!UICONTROL 订单]等量度可能不在报告包间累加。 |
| 货币 | Customer Journey Analytics 尚不支持货币换算。如果尝试合并的报告包使用不同的基础货币，则可能会出现问题。 |
| [!UICONTROL 持久性] | [持久性](../data-views/component-settings/persistence.md)作用于各个报告包，这会影响[!UICONTROL 区段]、[!UICONTROL 归因]等。数值可能无法正确地累加。 |
| [!UICONTROL 分类] | 在合并报告包时，不会自动为[!UICONTROL 分类]去重。将多个分类文件合并为一个[!UICONTROL 查找]数据集时，可能会遇到问题。 |

## &#x200B;8. [!UICONTROL Adobe Analytics] 组件

+++**我能否将来自 [!DNL Customer Journey Analytics] 的 [!UICONTROL 受众] 共享/发布到 Experience Platform Real-Time CDP 或其他 Experience Cloud 应用程序？**

您现在可以在 Adobe Experience Platform 中 [创建并将在 Customer Journey Analytics 中](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/audiences/publish) 发现的受众发布到实时客户轮廓，以实现客户目标选择和个性化。

+++

+++**我的旧 [!UICONTROL eVar] 设置发生了什么？**

[!UICONTROL Customer Journey Analytics] 中不再存在 Adobe Analytics 意义上的 [!UICONTROL eVar]、[!UICONTROL prop ]和[!UICONTROL 事件。]您有不限量的架构元素（维度、量度、列表字段）。因此，现在将在查询时应用您过去常在数据收集期间使用的所有归因设置。

+++

+++**我的所有会话和变量持久性设置现在位于何处？**

[!UICONTROL Customer Journey Analytics] 在报告时应用所有这些设置，因此这些设置现在位于数据视图中。对这些设置的更改现在具有追溯性，您可以使用多个数据视图来管理多个版本！

+++

+++**您的现有区段/计算量度发生了什么？**

[!UICONTROL Customer Journey Analytics] 不再使用 eVar、prop 或事件，改为使用任何 Adobe Experience Platform 架构。这意味着，任何现有区段或计算量度都与 [!UICONTROL Customer Journey Analytics] 不兼容。

+++

+++**[!UICONTROL Customer Journey Analytics] 如何处理 `Uniques Exceeded` 限制？**

[!UICONTROL Customer Journey Analytics] 没有唯一值限制，因此无需担心！

+++

+++**如果我是现有 [!DNL Data Workbench] 客户，是否可以立即转到 [!UICONTROL Customer Journey Analytics]？**

这取决于您的用例，请与您的 Adobe 帐户团队合作。您的当前用例可能已经非常适合 Customer Journey Analytics！

+++

## &#x200B;9. 估计连接大小 {#estimate-size}

请参阅 [连接使用情况](/help/connections/manage-connections.md#usage)。

## &#x200B;10. 关于使用过量 {#overage}

Adobe 定期监控和执行使用限制。“数据行数”表示可供在 Customer Journey Analytics 中分析的数据的每日平均行数。

例如，您的合同授权您拥有 100 万行数据。假设在使用 Customer Journey Analytics 的第 1 天，您上传了 200 万行数据。在第 2 天，您删除了 100 万行数据，并在许可期限的剩余时间将用量保持在承诺的最大值（即 100 万行数据）。根据您的合同条款，由于您超出了“数据行”许可证授权，因此您在第 1 天仍可能会收取按比例分摊的过度使用费用。

## &#x200B;11. 诊断数据差异 {#discrepancies}

您有时可能会注意到您的连接摄取的事件总数与 [!UICONTROL Adobe Experience Platform] 中数据集中的行数不同。在此示例中，“B2B Impression”数据集的行数为 7650，而该数据集在 [!UICONTROL Adobe Experience Platform] 中的行数为 3830。导致差异的原因有多种，可采取以下步骤进行诊断：

1. 按 **[!UICONTROL Platform 数据集 ID]** 划分此维度，您注意到有两个数据集的大小相同，但 **[!UICONTROL Platform 数据集 ID]** 不同。每个数据集有 3825 条记录。这意味着由于缺少人员 ID 或时间戳，[!UICONTROL Customer Journey Analytics] 忽略了五条记录：

   ![划分](assets/data-size2.png)

1. 此外，如果您签入 [!UICONTROL Adobe Experience Platform]，发现不存在 ID 为“5f21c12b732044194bffc1d0”的数据集，因此表示有人在创建初始连接后从 [!UICONTROL Adobe Experience Platform] 中删除了这个特定的数据集。不过，之后又将此数据集重新添加到 Customer Journey Analytics 中，但 [!UICONTROL Adobe Experience Platform] 生成了一个不同的 [!UICONTROL Platform 数据集 ID]。

有关更多信息，请参阅在 [!UICONTROL Customer Journey Analytics] 和 [!UICONTROL Adobe Experience Platform] 中[删除数据集和连接的后果。](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=zh-hans#implications-of-deleting-data-components)


## &#x200B;12. 地区数据收集

Adobe Experience Cloud 使用地区数据收集 (RDC)，以使您的访客与 Adobe 和非 Adobe 解决方案之间发生的交互尽可能接近您的访客。在数据收集中心（DCC，也称为边缘站点，它是 Platform 边缘网络的一部分）区域性地收集数据后，将根据您的数据流和/或事件转发的配置通过一个安全的连接将这些数据转发到相关的解决方案。

![使用边缘网络的数据流](https://experienceleague.adobe.com/docs/experience-platform/assets/collection.png)

区域数据收集过程使用以下步骤：

1. DNS 会自动将收集主机名解析为距访客最近的数据收集中心的 IP 地址。
1. 访客将数据发送到该地址。
1. 立即将数据通过一个安全的连接转发到由数据流或事件转发配置定义的解决方案。

使用区域数据收集提供了以下好处：

* **性能**：通过 RDC，访客将连接到最近的 DCC。这优化将提供最快的响应速度，从而实现更准确的跟踪和更快的加载速度。
* **冗余**：如果 DCC 与 DPC 之间出现通信中断，则 Adobe 的 RDC 基础设施会在本地保存数据，然后在通信恢复后将数据转发到 DPC。

RDC 目前包括以下位置（可能发生变化）：


| RDC 类型 | 数据收集中心 |
| --- | --- |
| 全局（默认） | 俄勒冈、弗吉尼亚、爱尔兰、巴黎、孟买、新加坡、东京、悉尼 |
| 仅限美洲 | 俄勒冈州、弗吉尼亚州 |
| 仅限欧洲 | 爱尔兰、巴黎 |
| 仅限亚太地区 | 孟买、新加坡、东京、悉尼 |

{style="table-layout:auto"}

当数据到达区域数据中心时，数据流配置决定如何进一步路由这些数据。

Customer Journey Analytics 需要来自 Adobe Experience Platform 的数据集，因此，您的数据流/事件转发配置需要 Adobe Experience Platform 服务将数据从区域数据中心路由到 Adobe Experience Platform 实例所在的数据中心。Customer Journey Analytics 及其支持服务和基础设施部署在同一个 Adobe Experience Platform 实例中。


有关在 Adobe Experience Platform Edge Network 及其区域数据中心之外收集数据的过程，请参阅[数据收集概述](https://experienceleague.adobe.com/docs/experience-platform/collection/home.html)。
