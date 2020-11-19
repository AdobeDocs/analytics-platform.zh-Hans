---
title: 在Adobe Experience Platform使用营销渠道维度
description: 使用Analytics Data Connector将营销渠道处理规则引入Adobe Experience Platform。
translation-type: tm+mt
source-git-commit: b5ed4c65877fa8e2de83810a3c4bd1a4048f5b31
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 3%

---


# 在Adobe Experience Platform使用营销渠道维度

如果您的组织使用[Analytics Data Connector](https://docs.adobe.com/content/help/zh-Hans/experience-platform/sources/connectors/adobe-applications/analytics.html)将报表包数据引入CJA，则可以在CJA中配置连接以报告营销渠道维度。

## 先决条件

* 必须使用[分析数据连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html)将报表包数据导入Adobe Experience Platform。 不支持其他数据源，因为营销渠道依赖Analytics报表包中的处理规则。
* 必须已设置营销渠道处理规则。 请参阅传统的“分析组件”指南中的[营销渠道的处理规则](https://docs.adobe.com/content/help/zh-Hans/analytics/components/marketing-channels/c-rules.html)。

## 营销渠道模式元素

在所需的报表包上建立Analytics Data Connector后，将为您创建XDM模式。 此模式包含所有Analytics维度和指标作为原始数据。 此原始数据不包含归因或持久性。 相反，每个事件都通过营销渠道处理规则运行，并记录其匹配的第一个规则。 在CJA中创建数据视图时，可指定属性和持久性。

1. [创建包](/help/connections/create-connection.md) 含基于Analytics Data Connector的数据集的连接。
2. [创建包含](/help/data-views/create-dataview.md) 以下维的数据视图：
   * **`channel.typeAtSource`**:与营销渠道 [维](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-channel.html) 度等效。
   * **`channel._id`**:相当于营销 [渠道详细信息](https://docs.adobe.com/content/help/en/analytics/components/dimensions/marketing-detail.html)
3. 为每个维度提供所需的归因模型和持久性。 如果要同时使用第一个和最后一个接触维，请多次将每个营销渠道维拖动到组件区域。 为每个维度提供所需的归因模型和持久性。 Adobe还建议为每个维提供一个显示名称，以便更便于在Workspace中使用。
4. 创建数据视图。

您的营销渠道维度现在可在Analysis Workspace使用。

## 处理和架构差异

>[!IMPORTANT]
>
>报表包数据与平台数据之间存在几个基本数据差异。 Adobe强烈建议调整报表包的营销渠道处理规则，以帮助在平台中正确收集数据。

营销渠道设置在平台数据和报表包数据之间的操作方式不同。 在为CJA设置营销渠道时，请考虑以下差异：

* **是访问的第一页**:此规则标准在多个默认营销渠道定义中很常见。平台中将忽略包含此条件的任何处理规则（同一规则中的其他条件仍适用）。 会话是在数据查询时而不是数据收集时确定的，从而阻止平台使用此特定规则条件。 Adobe建议从每个营销渠道处理规则中删除“是访问的第一页”条件。

   ![首页访问](assets/first-page-of-visit.png)

* **覆盖上次触摸渠道**:营销渠道管理器中的此设置通常会阻止特定渠道获得最后联系渠道信用。平台忽略此设置，允许诸如“Direct”或“Internal”之类的广泛渠道以可能不希望的方式为指标添加属性。 Adobe建议删除未选中“覆盖上次触摸渠道”的渠道。
   * 您可以在营销渠道管理器中删除“直接”营销渠道，然后依赖CJA的“无值”维度项来处理该渠道。 您还可以将此维项重命名为“直接”，或在配置数据视图时完全排除维项。
   * 或者，您也可以创建营销渠道分类，将每个值分类到自己，但要在CJA中排除的渠道除外。 然后，在创建数据视图时，可以使用此分类维，而不是`channel.typeAtSource`。

   ![覆盖上次触摸渠道](assets/override-last-touch-channel.png)

* **营销渠道到期**:此参与期设置决定访客在报告套件数据中获得新的首次接触渠道之前的不活动期。平台使用其自己的属性设置，因此在CJA中完全忽略此设置。

   ![营销渠道到期](assets/marketing-channel-expiration.png)

## 比较CJA和传统Analytics的数据

由于Adobe Experience Platform的体系结构与传统的Analytics报告套件不同，结果无法保证一致。 但是，您可以使用以下提示来简化此比较：

* 验证上面列出的体系结构差异不会影响您的比较。 这包括删除不覆盖上次触摸渠道的渠道，以及删除作为访问（会话）的首次点击的规则条件。
* 多次检查您的连接是否使用与传统Analytics相同的报表包。 如果您的CJA连接包含多个具有自己的营销渠道处理规则的报表包，则很难将其与传统Analytics进行比较。 您希望为每个报表包创建单独的连接以比较数据。
* 确保比较相同的日期范围，并且数据视图中的时区设置与报表包的时区相同。
* 在查看报表包数据时使用自定义归因模型。 例如，将[营销渠道](https://experienceleague.adobe.com/docs/analytics/components/dimensions/marketing-channel.html)维度与使用非默认归因模型的度量结合使用。 Adobe建议不要比较默认维[首次触摸渠道](https://experienceleague.adobe.com/docs/analytics/components/dimensions/first-touch-channel.html)或[上次触摸渠道](https://experienceleague.adobe.com/docs/analytics/components/dimensions/last-touch-channel.html)，因为它们依赖于在报表包中收集的属性。 CJA不依赖报表包的归因数据；而是在运行CJA报告时计算。
* 由于报告套件数据与平台数据之间的体系结构差异，某些指标没有合理的比较。 示例包括访问／会话、访客/人员和发生次数/事件。
