---
source-git-commit: 8943af2bc81de5ece238dc7647ff3f66b14b9776
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 4%

---
# Adobe Analytics处理规则、VISTA和分类与Analytics源连接器的数据准备

[处理规则和VISTA规则](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/processing-rules/processing-rules-configuration/processing-rule-order.html?lang=en) 提供转换和处理传递到Adobe Analytics的数据的方法 [数据收集](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/reporting-interface/overview-data-collection.html?lang=en). 在Adobe Analytics中存储Adobe以用于报告和分析之前，这些转换会作为数据处理的一部分进行。


[数据准备](https://experienceleague.adobe.com/docs/experience-platform/data-prep/home.html?lang=zh-Hans) 是一个工具，允许您将基于行的映射和转换应用于摄取到的数据 [AEP](https://experienceleague.adobe.com/docs/experience-platform.html?lang=en) 数据供AEP应用程序（包括CJA和其他应用程序）使用之前，请执行以下操作： 数据准备与许多AEP集成 [源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=en) 现在也与 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)，提供了一种将报表包数据从Adobe Analytics摄取到AEP的方法。

由Adobe Analytics收集并存储在Analytics中的数据可通过处理规则或VISTA规则进行转换，也可通过两者进行转换。 但是，随后通过Analytics源连接器转发到AEP的报表包可能会再次使用数据准备进行转换。 这对于许多目的而言可能是可取的：

* **解决报表包之间在CJA和/或RTCDP中使用的架构差异**. 例如，如果报表包A将eVar1定义为搜索词，而报表包B将eVar2定义为搜索词，则可以使用数据准备将两个不同的eVar映射到包含两个eVar数据的通用字段。 这使得 [将不同架构的报表包组合在一起](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/combine-report-suites.html?lang=en) 在CJA连接中或在RTCDP中使用。
* **将eVar字段映射到语义上有意义的名称**. 通过Analytics源连接器的eVar和prop会映射到以下字段 _\_experience.analytics.customDimensions.eVars.eVar1_.  数据准备可用于将eVar和prop字段映射到对用户具有更有意义名称的新字段，或者与来自其他数据源的名称匹配的新字段。 (尽管如此，也可以通过其他方式（例如重命名CJA数据视图中的字段）来实现此目的。)
* **通常转换数据**. 数据准备具有数百个映射函数，这些函数可用于根据通过ADC传送的数据计算和计算新字段。 您可以将分隔字段拆分为单独的字段。 您可以组合字段。 您可以操作字符串。 您可以从基于正则表达式等的字段中提取信息。


您还可能会注意到数据准备与 [分类](https://experienceleague.adobe.com/docs/analytics/components/classifications/c-classifications.html?lang=zh-Hans) 在某些情况下。 例如，如果您有一个分隔字段，则可以使用“数据准备”将该字段拆分为多个单独的字段，而无需使用分类。 但是，通常，分类是一种通过上传在传入Analytics点击流之外提供的查找文件来向字段添加元数据的方法。 例如，您可以上传一个分类文件，将SKU分组为“大小”、“品牌”、“颜色”等。 分类和数据准备的另一个区别是分类适用于历史数据和将来数据。 另一方面，数据准备映射会从创建映射时起应用到数据。