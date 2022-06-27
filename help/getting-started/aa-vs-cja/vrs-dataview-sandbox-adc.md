---
title: 虚拟报表包、数据视图、AEP沙箱和Analytics源连接器
description: 了解虚拟报告环境和沙盒环境。
exl-id: 8f0358d1-85fe-4e1e-8724-8a7caa16328c
source-git-commit: 7c3bbe2829c83406b2e6824e509c34459ae00f94
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 9%

---

# 虚拟报表包、数据视图、AEP沙箱和Analytics源连接器

Adobe提供了多种创建虚拟报告环境和沙盒环境的方法。 了解以下特征之间的相似之处和差异以及这些特征与 [Analytics源连接器](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=zh-Hans):

* Adobe Analytics虚拟报表包
* CJA数据视图
* AEP沙箱

## Adobe Analytics虚拟报表包(VRS)

有关更多信息，请参阅： [虚拟报表包概述](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-about.html?lang=zh-Hans).

VRS:

* 可以基于Adobe Analytics区段。
* 可以以非破坏性方式应用于历史数据和新数据。
* 允许您在Adobe Analytics报表包上创建一个或多个虚拟视图，以供不同的业务团队使用。
* 可用于控制对Adobe Analytics中不同用户的不同类型数据的访问和管理。
* 提供可选 [报告时间处理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hans) 功能Adobe Analytics。 在这种情况下，可以使用VRS为“访问”创建自定义定义。
* 在报表运行时应用，与区段评估类似。 这是 _after_ 已在Adobe Analytics中收集和存储数据。
* 是 [跨设备分析](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hans) 在Adobe Analytics。
* 具有相同数量的变量可用作标准Analytics报表包（250个eVar、250个prop、1000个事件），不过VRS管理可以限制向用户显示的变量。
* 支持自定义日历选项。

虚拟报表包不是：

* 一种组合报表包的方法。
* 在Adobe AnalyticsData warehouse中提供。
* 可作为通过Analytics源连接器进入AEP的数据流的源。 只有完整（非虚拟）报表包才可与Analytics源连接器一起使用。


## CJA数据视图

有关更多信息，请参阅： [数据视图概述](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=zh-Hans).

数据视图：

* 可以基于CJA过滤器。
* 可以以非破坏性方式应用于历史数据和新数据。
* 允许您基于CJA连接创建一个或多个虚拟视图，以供不同的业务团队使用。
* 可用于在CJA中控制对不同用户的不同类型数据的访问和管理。
* 提供了强大的无损选项，可用于通过CJA连接转换和增强传入CJA的数据。
* 基于CJA的报告时处理功能。
* 允许用户为“session”创建自定义定义。
* 在报表运行时应用，与过滤器评估类似。 这是 _after_ 源连接器(Adobe Analytics或其他)已将数据写入AEP数据湖中的数据集，以及 _after_ 数据已通过CJA连接被摄取到CJA。
* 允许无限数量的变量，但管理可以限制向用户显示的变量
* 允许自定义命名“事件”、“会话”和“人员”容器。
* 支持自定义日历选项。

数据视图不会：

* 直接提供用于组合报表包或其他数据集的方法。 而是在CJA连接中将数据集与结合使用。 CJA连接中的组合数据可用于基于该连接的所有数据视图。

## AEP沙箱

有关更多信息，请参阅： [沙箱概述](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=zh-Hans).

AEP沙盒：

* 提供了一种将单个AEP实例分区为单独的虚拟环境（开发、测试、暂存、生产等）的方法 帮助开发和改进数字体验应用程序。
* 可以视为一个容器，其中保存给定环境的所有数据和应用程序。

AEP沙盒不会：

* 提供与虚拟报表包、CJA连接或数据视图类似的功能。
* 单独将报表包与（或不包含）其他数据集组合在一起。 但是，沙盒中的数据集可以合并到CJA连接中。

注意：

* CJA中无法合并来自不同沙箱的数据。
* Analytics源连接器发送报表包数据 _into_ 特定沙盒。 每个报表包都可以配置为单个沙盒的源。 请参阅 [Analytics源连接器文档](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html?lang=en) 以了解更多详细信息。
