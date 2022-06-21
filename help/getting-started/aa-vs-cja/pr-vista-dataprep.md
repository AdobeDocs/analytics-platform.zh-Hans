---
title: 处理规则、VISTA和分类与Analytics源连接器的数据准备
description: 了解使用处理规则和VISTA与使用数据准备的数据转换
source-git-commit: f6b8c5f1e8e82d0eb856b5cfed63b72c7ecfe3db
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 6%

---


# 处理规则、VISTA和分类与数据准备

Adobe Analytics [处理规则和VISTA规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) 提供转换和处理传递到Adobe Analytics的数据的方法 [数据收集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). 在Adobe Analytics中存储Adobe以用于报告和分析之前，这些转换会作为数据处理的一部分进行。

[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans) 是一个工具，允许您将基于行的映射和转换应用到摄取到的数据 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en). 随后，该数据便可用于Experience Platform应用程序，包括CJA和其他应用程序。 数据准备与许多平台集成 [源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en)，以及 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans). 此连接器提供了一种将报表包数据从Adobe Analytics摄取到Platform的方法。

## 使用数据准备进行进一步转换 {#data-prep}

由Adobe Analytics收集并存储在Analytics中的数据可通过处理规则或VISTA规则进行转换，也可通过两者进行转换。 但是，随后通过Analytics源连接器转发到平台的报表包可能会再次使用数据准备进行转换。 这可以用于多种目的：

* **解决报表包之间在CJA和/或RTCDP中使用的架构差异**. 例如，假设报表包A定义了 `eVar1` “搜索词”和报表包B定义 `eVar2` 作为“搜索词”。 您可以使用数据准备将两个不同的eVar映射到包含两个eVar数据的公用字段中。 这使得 [将不同架构的报表包组合在一起](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) 在 [CJA连接](/help/connections/overview.md) 或用于 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=zh-Hans).
* **映射 `eVars` 用于语义上有意义名称的字段**. `eVars` 和 `props` 通过Analytics源连接器会映射到 _\_experience.analytics.customDimensions.eVars.eVar1_. 数据准备可用于映射 `eVar` 和 `prop` 字段，用于指定对用户具有更有意义名称的新字段，或匹配来自其他数据源的名称的新字段。 (这也可以通过其他方式实现，例如重命名 [CJA数据视图](/help/data-views/create-dataview.md).)
* **通常转换数据**. 数据准备具有数百个映射函数，可用于根据通过Analytics源连接器获得的数据计算和计算新字段。 您可以将分隔字段拆分为单独的字段。 您可以组合字段。 您可以操作字符串。 您可以从基于正则表达式等的字段中提取信息。

## 数据准备和分类 {#classifications}

数据准备与 [分类](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=zh-Hans) 在某些情况下。

例如，在分隔字段中，您可以使用数据准备将该字段拆分为多个单独的字段，而无需使用分类。 通常，分类是一种通过上载在传入Analytics点击流之外提供的查找文件来向字段添加元数据的方法。

例如，您可以上传一个分类文件，将SKU分组为“大小”、“品牌”、“颜色”等。 分类和数据准备的另一个区别是分类适用于数据 _历史和未来_. 另一方面，会应用数据准备映射 _forward_ 从创建映射时开始的数据。

