---
title: 虚拟报告包、数据视图、Adobe Experience Platform沙盒和Analytics Source Connector
description: 了解虚拟报告环境和沙盒环境。
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
feature: CJA Basics
source-git-commit: edbad9c9d3dc0b48db5334828a18ef652d4a38aa
workflow-type: tm+mt
source-wordcount: '768'
ht-degree: 62%

---

# 虚拟报告包、数据视图、Adobe Experience Platform沙盒和Analytics Source Connector

Adobe 提供了多种方法来创建虚拟报告环境和沙盒环境。了解以下功能之间的异同以及这些功能与[ Analytics Source Connector ](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)的关系非常有用：

* Adobe Analytics 虚拟报告包
* Customer Journey Analytics数据视图
* Adobe Experience Platform沙盒

## Adobe Analytics 虚拟报告包 (VRS)

有关更多信息，请参阅：[虚拟报告包概述](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hans)。

虚拟报告包：

* 可以基于 Adobe Analytics 区段。
* 能够以无损的方式应用于历史数据和新数据。
* 允许您在 Adobe Analytics 报告包上创建一个或多个虚拟视图，以供不同的业务团队使用。
* 可用于控制 Adobe Analytics 中不同用户对不同类型数据的访问和管理。
* 为 Adobe Analytics 提供可选的[报告时处理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hans)功能。在这种情况下，VRS 可用于创建对“访问”的自定义。
* 在报告运行时应用，类似于区段评估。这会在收集数据并将其存储在 Adobe Analytics 中&#x200B;_之后_&#x200B;进行。
* 在 Adobe Analytics 中进行[跨设备分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hans)时需要。
* 提供与标准分析报告包相同数量的变量（250 个 eVar、250 个道具、1000 个事件），但是 VRS 管理功能可以限制用户可以看到哪些变量。
* 支持自定义日程表选项。

虚拟报告包不是：

* 组合报告包的方法。
* 在 Adobe Analytics Data Warehouse 中提供。
* 可用作通过Analytics Source Connector流入Adobe Experience Platform的数据流的源。 只有完整的（非虚拟）报告包可用于 Analytics Source Connector 。


## Customer Journey Analytics数据视图

有关更多信息，请参阅[数据视图概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hans)。

数据视图：

* 可以基于Customer Journey Analytics过滤器。
* 能够以无损的方式应用于历史数据和新数据。
* 允许您在Customer Journey Analytics连接上创建一个或多个虚拟视图，以供不同的业务团队使用。
* 可用于控制Customer Journey Analytics中不同用户对不同类型数据的访问和管理。
* 提供强大的非破坏性选项，用于转换和增强通过Customer Journey Analytics连接进入Customer Journey Analytics的数据。
* 基于Customer Journey Analytics的报告时间处理功能。
* 允许用户创建对“会话”的自定义。
* 在报告运行时应用，类似于过滤器评估。这是 _之后_ 源连接器(Adobe Analytics或其他)已将数据写入Adobe Experience Platform数据湖中的数据集，并且 _之后_ 数据已通过Customer Journey Analytics连接引入Customer Journey Analytics。
* 允许无限数量的变量，但是管理功能可以限制用户可以看到哪些变量
* 允许对自定义事件、会话和人员容器的命名。
* 支持自定义日程表选项。

数据视图不会：

* 直接提供组合报告包或其他数据集的方法。相反，数据集会在Customer Journey Analytics连接中进行组合。 来自Customer Journey Analytics连接的组合数据可用于基于该连接的所有数据视图。

## Adobe Experience Platform沙盒

有关更多信息，请参阅：[沙盒概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hans)。

Adobe Experience Platform沙盒：

* 提供了一种将单个Adobe Experience Platform实例分区为单独虚拟环境（开发、测试、暂存、生产等）的方法 帮助开发和发展数字体验应用程序。
* 可以将其视为一个容器，其中包含给定环境的所有数据和应用程序。

Adobe Experience Platform沙盒不会：

* 提供与虚拟报表包、Customer Journey Analytics连接或数据视图类似的功能。
* 无论是否带有数据集，单独将报告包进行合并。但是，沙盒中的数据集可以在Customer Journey Analytics连接中进行组合。

注意：

* 来自不同沙盒的数据不能在Customer Journey Analytics中合并。
* Analytics Source Connector 将报告包数据发送&#x200B;_到_&#x200B;特定的沙盒中。每个报告包均可以配置为单个沙盒的来源。有关更多详细信息，请参阅 [Analytics Source Connector 文档](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans)。
