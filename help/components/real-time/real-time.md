---
description: 了解Customer Journey Analytics中的实时报表功能。
title: 实时报表概述
feature: Filters, Segments
hide: true
hidefromtoc: true
role: User
badgePremium: label="Beta 版"
source-git-commit: 24834f6a1424a885c6f7b3dcf0ad84375e21b462
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

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

* 真实报表的相关但价值较低的用例是验证用例。
例如，您要验证：

   * 您最近启动的活动历程是否真的有效？
   * 您的新产品页面是否已经启用，并且您是否正在从该页面收集客户数据？
   * 您的直播媒体活动是否正常？

对于操作监控用例，请勿考虑实时报告。 例如，回答您的网站是否实际正常运行的问题？


## 定义

Customer Journey Analytics实时报表的实时方面被定义为从通过关联连接摄取基础数据之日起约5分钟内更新的数据和可视化图表。

## 限制

您应了解实时报表的以下限制：

* 实时报表仅报告滚动时段24小时内的可用数据。 超过此滚动24小时期间的数据不可用。
* 归因、分段、计算量度等仅适用于滚动时段（24小时）内的可用数据。
* 实时报表最适用于事件和会话级别的数据，您应该谨慎对人员级别的数据使用实时报表。 <!--Need to explain this a bit better -->选择维度、（计算）量度时，请考虑事件和会话级别数据的偏好设置。 当您在启用实时刷新的面板中使用划分、下一版本或上一版本等功能时。
* 您不能将拼合与实时报表结合使用。 <!-- Do we need to explain this in more detail, why? -->如上所述，实时报告涉及的是事件和会话级别的数据，而不是基于人员的数据。
* 除媒体开始和媒体关闭量度外，没有可用的心跳收集媒体量度。 因此，您仍然可以使用实时报表来启用媒体用例。
