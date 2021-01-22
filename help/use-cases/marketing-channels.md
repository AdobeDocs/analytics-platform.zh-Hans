---
title: 在 Adobe Experience Platform 中使用“营销渠道”维度
description: 使用 Analytics Data Connector 将“营销渠道”维度处理规则引入 Adobe Experience Platform。
translation-type: ht
source-git-commit: b5ed4c65877fa8e2de83810a3c4bd1a4048f5b31
workflow-type: ht
source-wordcount: '930'
ht-degree: 100%

---


# 在 Adobe Experience Platform 中使用“营销渠道”维度

如果您的组织使用 [Analytics Data Connector](https://docs.adobe.com/content/help/zh-Hans/experience-platform/sources/connectors/adobe-applications/analytics.html) 将报表包数据引入 CJA，则可以在 CJA 中配置连接以报告“营销渠道”维度。

## 先决条件

* 必须已使用 [Analytics Data Connector](https://docs.adobe.com/content/help/zh-Hans/experience-platform/sources/connectors/adobe-applications/analytics.html) 将报表包数据导入 Adobe Experience Platform。不支持其他数据源，因为“营销渠道”维度依赖于 Analytics 报表包中的处理规则。
* 必须已设置“营销渠道”维度处理规则。请参阅“传统 Analytics 组件”指南中的[“营销渠道”维度的处理规则](https://docs.adobe.com/content/help/zh-Hans/analytics/components/marketing-channels/c-rules.html)。

## “营销渠道”架构元素

在所需的报表包上建立 Analytics Data Connector 后，将为您创建一个 XDM 架构。此架构包含所有 Analytics 维度和量度作为原始数据。此类原始数据中不包含归因或持久性设置。相反，每个事件都通过“营销渠道”维度处理规则运行，并记录其匹配的第一个规则。可在 CJA 中创建数据视图时指定归因和持久性设置。

1. [创建连接](/help/connections/create-connection.md)，连接中包含基于 Analytics Data Connector 的数据集。
2. [创建数据视图](/help/data-views/create-dataview.md)，视图中包含以下维度：
   * **`channel.typeAtSource`**：相当于[营销渠道](https://docs.adobe.com/content/help/zh-Hans/analytics/components/dimensions/marketing-channel.html)维度。
   * **`channel._id`**：相当于[营销渠道详细信息](https://docs.adobe.com/content/help/zh-Hans/analytics/components/dimensions/marketing-detail.html)
3. 为每个维度提供所需的归因模型和持久性。如果要同时使用“首次接触”和“最后接触”维度，请将每个“营销渠道”维度多次拖动到组件区域。为每个维度提供所需的归因模型和持久性。Adobe 还建议为每个维度提供一个显示名称，以便于在 Analysis Workspace 中使用这些维度。
4. 创建数据视图。

“营销渠道”维度现在可在 Analysis Workspace 中使用。

## 处理方式和体系结构差异

>[!IMPORTANT]
>
>报表包数据与 Platform 数据之间存在一些基本数据差异。Adobe 强烈建议调整报表包中的“营销渠道”维度处理规则，以便能在 Platform 中正常收集数据。

“营销渠道”设置在 Platform 数据和报表包数据中的运行方式有所不同。在为 CJA 设置“营销渠道”维度时，请考虑以下差异：

* **为访问的首个页面**：此规则条件在多个默认“营销渠道”定义中是通用的。将在 Platform 中忽略包含此条件的任何处理规则（同一规则中的其他条件仍适用）。会话是在数据查询时而不是数据收集时确定的，这样可阻止 Platform 使用此特定规则条件。Adobe 建议从每个“营销渠道”维度处理规则中删除“为访问的首个页面”这一条件。

   ![访问的首个页面](assets/first-page-of-visit.png)

* **覆盖最后接触渠道**：营销渠道管理器中的这项设置通常会阻止某些渠道获取最后接触渠道点数。Platform 会忽略此设置，从而允许将诸如“直接”或“内部”之类的宽泛渠道以可能不太妥当的方式计入量度。Adobe 建议删除未选中“覆盖最后接触渠道”的渠道。
   * 您可以在营销渠道管理器中删除“直接”营销渠道，然后为该渠道使用 CJA 的“无值”维度项。您还可以将此维度项重命名为“直接”，或在配置数据视图时完全排除此维度项。
   * 或者，您也可以创建一个营销渠道分类，对每个值进行单独分类，但要在 CJA 中排除的渠道除外。然后，在创建数据视图时，您可以使用此分类维度，而不是 `channel.typeAtSource`。

   ![覆盖最后接触渠道](assets/override-last-touch-channel.png)

* **营销渠道到期**：此参与期设置确定访客要在保持不活动状态多长时间后才能在报表包数据中获得新的首次接触渠道。Platform 将使用其自身的归因设置，因此，此设置将在 CJA 中完全被忽略。

   ![营销渠道到期](assets/marketing-channel-expiration.png)

## 比较 CJA 与传统 Analytics 中的数据

由于 Adobe Experience Platform 的体系结构不同于传统的 Analytics 报表包，因此，无法保证结果保持一致。但是，您可以使用以下提示来简化此比较过程：

* 确认上列体系结构差异不会影响您的比较。这包括删除不覆盖最后接触渠道的渠道，以及删除“为访问（会话）的首次点击”规则条件。
* 再次确认您的连接使用与传统 Analytics 相同的报表包。如果您的 CJA 连接包含多个报表包且每个报表包都有自己的“营销渠道”维度处理规则，则很难将其与传统 Analytics 进行比较。您需要为每个要比较数据的报表包各创建一个连接。
* 确保比较相同日期范围的数据，并且数据视图中的时区设置与报表包的时区相同。
* 在查看报表包数据时使用自定义归因模型。例如，将[营销渠道](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html)维度与使用非默认归因模型的量度结合使用。Adobe 建议不要比较默认维度[首次接触渠道](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html)或[最后接触渠道](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html)，因为它们依赖于报表包中收集的归因数据。CJA 不依赖报表包中的归因数据；相反，会在运行 CJA 报表时进行计算。
* 由于报表包数据与 Platform 数据之间存在体系结构上的差异，因此无法合理比较某些量度。例如，“访问次数”与“会话数”、“访客数”与“人员数”，以及“发生次数”与“事件数”量度。
