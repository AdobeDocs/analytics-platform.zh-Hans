---
description: 了解Customer Journey Analytics中的实时报表功能。
title: 实时报表概述
feature: Real-time Reporting
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta 版"
exl-id: 12fbb760-936d-4e30-958f-764febca5ae7
source-git-commit: b833914e7066fa660f856737d6b8a6392aae2feb
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 3%

---

# 实时报表概述

Customer Journey Analytics中的实时报表可实时显示和更新Analysis Workspace中一个或多个面板的数据和可视化图表。

{{release-limited-testing}}

{{ultimate-package}}

## 用例

此部分概述了有价值和不那么有价值的典型用例。 以及何时不考虑实时报表的信息。

* 实时报表最有价值的用例是关于主要销售、促销或产品发布。
在该启动项中，您想了解：

   * 与上一次销售相比，销售情况如何？
   * 与上次产品发布相比，本次产品发布情况如何？
   * 您为这一重要日子或活动举行的促销活动是否真的有效？

* 实时报表的相关用例（但价值较低的用例）是验证用例。
例如，您要验证：

   * 您最近启动的活动历程是否实际有效？
   * 新产品页面上线时，您是否从该页面收集客户数据？
   * 您的直播媒体活动是否正常？

对于操作监控用例，请勿考虑实时报告。 例如，回答站点是否正常运行的问题。 由于[实时刷新切换开关](use-real-time.md)会在30分钟后自动禁用并且实时报表停止刷新，因此您不应将实时报表用作这些用例的可靠源。


## 定义

Customer Journey Analytics实时报表的实时方面被定义为从通过关联连接摄取基础数据之日起约6.5分钟内更新的数据和可视化图表。

数据收集设置中的各种组件决定了实时报告延迟。

![实时报告](assets/real-time-reporting-latencies.svg){zoomable="yes"}

| | 描述 | 延迟 |
|:---:|---|--:|
| 1 | 通过Edge Network SDK/API收集的数据进入Edge Network。 | &lt; 500毫秒 |
| 2 | 数据从Edge Network复制到Experience Platform Hub中的数据收集和验证服务。 | &lt; 5 分钟 |
| 3 | 通过流式连接器收集的数据将收集到Experience Platform Hub的数据收集和验证服务中。 | &lt; 15分钟 |
| 4 | 通过Adobe Analytics收集并由Analytics Source Connector转发到Experience Platform中心的Source Connectors处理器的数据。 | &lt; 15分钟 |
| 5 | 通过其他源连接器收集的数据将收集到Experience Platform集线器的源连接器处理器中。 | &lt; 24小时 |
| 6 | 由实时处理器为合并的数据集处理的数据，用于实时报告。 | &lt; 90秒 |

## 限制

请注意实时报表的以下限制：

* 实时报表仅报告滚动时段24小时内的可用数据。 对于实时报表，将隐藏跨此24小时滚动时段的数据。 禁用或自动关闭报表的[实时刷新](use-real-time.md)后，报表的所有相关数据将再次可用。
* 归因、分段、计算量度等仅适用于滚动时段（24小时）内的可用数据。
* 实时报表最适用于事件和会话级别的数据，因此，在对人员级别的数据使用实时报表时应当谨慎。 <!--Need to explain this a bit better -->由于实时报表仅提供滚动的24小时周期中的事件，因此人员的事件历史记录也仅限于此时段。 选择维度和（计算）量度时，请考虑事件和会话级别数据的首选项。 当您在启用实时刷新的面板中使用划分、下一个或上一个以及更多等功能时。
* 您不能将拼合与实时报表结合使用。 <!-- Do we need to explain this in more detail, why? -->实时报表与事件和会话级别的数据有关，而与基于人员的数据不太相关。
* 除媒体开始和媒体关闭量度外，没有可用的心跳收集媒体量度。 因此，您仍然可以使用实时报表来启用媒体用例。
* 使用[下载或导出选项](/help/analysis-workspace/export/download-send.md)下载项目或从自由格式表中导出数据时，请考虑以下事项：
   * 下载的CSV项目或导出的CSV文件包含下载或导出时可用的实时数据。
   * 下载的PDF项目包含非实时数据，类似于禁用实时刷新时显示的数据。
