---
title: 使用Analytics Data Connector将营销渠道导入CJA
description: 使用正确的Analytics Data Connector设置将营销渠道处理规则引入Adobe Experience Platform。
translation-type: tm+mt
source-git-commit: 26486c79f6d94db1aa795bf024f581cad74c25f6
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 7%

---


# 使用Analytics Data Connector将营销渠道导入CJA

如果您的组织使用[Analytics Data Connector](https://docs.adobe.com/content/help/zh-Hans/experience-platform/sources/connectors/adobe-applications/analytics.html)将报表包数据引入CJA，则可以在CJA中配置连接以报告营销渠道维度。

## 先决条件

* 必须使用[分析数据连接器](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html)将报表包数据导入Adobe Experience Platform。
* 必须已设置营销渠道处理规则。 请参阅传统的“分析组件”指南中的[营销渠道的处理规则](https://docs.adobe.com/content/help/zh-Hans/analytics/components/marketing-channels/c-rules.html)。

## 营销渠道模式元素

在所需的报表包上使用Analytics Data Connector后，将为您创建XDM模式。 此模式包含所有Analytics维度和指标作为原始数据。 此原始数据不包含归因或持久性。 相反，每次点击都会运行营销渠道处理规则，并记录其匹配的第一条规则。 在CJA中创建数据视图时，可指定属性和持久性。

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


由于第一个和最后一个触摸渠道维本质上是使用不同归因模型的同一维，因此在[创建数据视图](/help/data-views/create-dataview.md)时可以重新创建相似维。 您可以基于同一模式元素创建多个维，为它们提供不同的归因模型和持久性。

## 之间的差异

