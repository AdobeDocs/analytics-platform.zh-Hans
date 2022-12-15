---
title: Analytics Source Connector 的处理规则、VISTA 和分类与数据准备
description: 了解使用处理规则和 VISTA 与通过准备数据来进行数据转换的异同
exl-id: 049ad97e-0b4f-4163-a022-32661e48bf13
source-git-commit: 6b7b8e8f1c1e88644961dd5e1b3d2ff7ec07951e
workflow-type: ht
source-wordcount: '611'
ht-degree: 100%

---

# 处理规则、VISTA 和分类与数据准备

Adobe Analytics [处理规则和 VISTA 规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=zh-Hans)提供了转换和操作传递到 Adobe Analytics [数据收集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=zh-Hans)中的数据的方法。在将数据存储在 Adobe Analytics 中用于报告和分析之前，这些转换是 Adobe 数据处理的一部分。

[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans)是一种工具，可用于将基于行的映射和转换应用到 [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=zh-Hans) 中的数据。随后，这些数据可用于 Experience Platform 应用程序，包括 CJA 和其他应用程序。数据准备已与许多 Platform [源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=zh-Hans)以及[ Analytics Source Connector ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)集成。此连接器提供了一种将 Adobe Analytics 中的报告包数据摄取到 Platform 中的方法。

## 使用数据准备进一步转换 {#data-prep}

Adobe Analytics 收集并存储的数据可以通过处理规则或 VISTA 规则或同时使用两者进行转换。但随后通过 Analytics Source Connector 转发到 Platform 的报告包可能会再次使用数据准备进行转换。这可以用于许多目的：

* **解决 CJA 和/或 RTCDP 中使用的报告包之间的架构差异**。例如，假设报告包 A 将 `eVar1` 定义为“搜索项”，报告包 B 将 `eVar2` 定义为“搜索项”。您可以使用数据准备将两个不同的 eVar 映射到一个公共字段中，该字段包含来自两个 eVar 的数据。这使得在 [CJA 连接](/help/connections/overview.md)中或在 [Real-time Customer Data Platform](https://experienceleague.adobe.com/docs/platform-learn/tutorials/application-services/rtcdp/understanding-the-real-time-customer-data-platform.html?lang=zh-Hans) 中能够[合并具有不同架构的报告包](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=zh-Hans)。
* **将字段`eVars`映射到语义上有意义的名称**。通过 Analytics Source Connector 的 `eVars` 和 `props` 被映射到 _\_experience.analytics.customDimensions.eVars.eVar1_ 等字段。数据准备可用于将 `eVar` 和 `prop` 字段映射到名称对用户更有意义或与来自其他数据源的名称相匹配的新字段。（这也可以通过其他方式实现，例如重命名 [CJA 数据视图](/help/data-views/create-dataview.md)中的字段。）
* **通常转换数据**。数据准备有数百个映射函数，可用于根据通过 Analytics Source Connector 获得的数据计算新字段。您可以将分隔字段拆分为单独的字段。您可以合并字段。您可以操纵字符串。您可以基于正则表达式从字段中提取信息，等等。

## 数据准备和分类 {#classifications}

在某些情况下，数据准备与[分类](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=zh-Hans)有所交叉。

例如，在分隔字段中，您可以使用数据准备将该字段拆分为多个单独的字段，而无需使用分类。通常，分类是通过上传在传入分析点击流之外提供的查找文件来向字段添加元数据的一种方法。

例如，您可以上传一个分类文件，将 SKU 分为“大小”、“品牌”、“颜色”等。分类和数据准备之间的另一个区别是，分类适用于&#x200B;_历史和未来的数据_。另一方面，从创建映射时起，数据准备的映射就会&#x200B;_向前_&#x200B;应用于数据。
