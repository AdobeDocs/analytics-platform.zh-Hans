---
description: Adobe提供了各种可用的计算量度。 此页面列出了这些量度及其预期用途。
title: 默认计算量度
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 74ec307b878b77a40ef1f5dbf54f2b59d88b41fe
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 56%

---

# 默认计算量度

Customer Journey Analytics提供各种计算量度以涵盖最常见的用例。 这些计算量度默认在Analysis Workspace中可用。

以下是Adobe提供的每个计算量度的列表，以及其预期函数和用于计算该量度的基础公式：

>[!NOTE]
>
>除了此页面中描述的默认计算量度之外，您还可以向数据视图添加其他计算量度。
>
>您可以:
> * 为流媒体添加默认计算量度，如 [计算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 根据现有量度创建自定义计算量度，如 [计算量度和高级计算（派生）量度](/help/components/calc-metrics/cm-adv-functions.md).



| 计算量度名称 | 函数 | 公式 |
|---------|----------|---------|
| 跳出率 | 包含正好一次点击的访问次数与该页面上的访问次数之比。此项可帮助您了解哪些维度项的跳出率最高或查看您的网站在一段时间内合计的总跳出率。 | `[Bounces] / [Entries]` |
| 收入/访客 | 每个访问网站的单独访客产生的平均收入金额。 | `[Revenue] / [Unique Visitors]` |
| 订购/访客 | 网站每位访客生成的平均订单数或交易数 | `[Orders] / [Unique Visitors]` |
| 收入/访问量 | 单次访问网站产生的平均收入金额。 | `[Revenue] / [Visits]` |
| 收入/订单 | 网站上每笔完成的交易或订单所产生的平均收入金额。 | `[Revenue] / [Orders]` |
| 订购/访问 | 对网站的访问完成交易的百分比。 | `[Orders] / [Visits]` |
| 页面查看/访问 | 用户单次访问网站期间查看的平均页数。 | `[Page Views] / [Visits]` |
| 访问/访客 | 独特访客对于网站的平均访问次数。 | `[Visits] / [Unique Visitors]` |
| 重新载入/页面查看次数 | 导致重新加载或刷新页面的页面查看次数的百分比。 | `[Reloads] / [Page Views]` |
| 加权跳出率 | 函数 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 订购协助 | 渠道或来源促成客户历程向购买推进但最终未购买的次数。 | `[Orders (Visit Participation)] - [Orders]` |
| 退出率 | 查看特定页面后离开网站的访客的百分比。 | `[Exits] / [Visits]` |
| 登录率 | 在给定页面上进入网站的访客占网站上会话总数的百分比。 | `[Entries] / [Visits]` |
| 网站平均逗留时间 | 访客在离开或导航到别处之前在网站上逗留的平均时长。 | `[Average Time Spent on Site (Seconds)]` |
| 逗留时间/用户（状态） | 访客在网站上停留在特定州的平均时间 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 用户（移动设备） | 移动设备应用程序的用户总数 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 应用程序用户 | 移动设备应用程序的用户总数 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 州视图 | 应用程序不同状态或屏幕的查看次数 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| 操作 | 应用程序中执行的操作总数 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| 客户获取链接点击量 | 人员点击旨在产生网站流量的链接的次数。 | `[Campaign Click-throughs]` |
| 页面周转率 | 一段内容生成的其他页面查看次数。 这有助于您确定哪些内容可推动更多参与。 | `[Page Views] / [Visits]` |
| 转化率 | 执行了所需操作（如进行了购买）的访客的百分比。 | `[Orders] / [Visits]` |
| 平均会话时长（移动设备） | 单个会话期间访客在网站上逗留的平均时长。 | 空白 |
| Experience Cloud ID 覆盖 | 拥有 Experience Cloud ID 的访客的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 内容周转率 | 在网站上创建和发布新内容的速度以及新内容能够多快地吸引用户参与。 | `[Page Views] / [Visits]` |
| ITP 2.1独特访客/独特访客 | 显示使用受 ITP 2.1 Cookie 限制影响的浏览器的独特访客百分比。换言之就是不使用 CNAME 实现的客户。（这适用于通过客户端 JavaScript 设置 Cookie 的客户。） | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 独特访客/7天后回访的独特访客 | 在 7 天或更长时间后回访的独特访客的百分比。 | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| 页面查看次数/独特访客 | 每个访问网站的独特访客查看的平均页数。 | `[Page Views] / [Unique Visitors]` |
| 访问数/访客数 | 独特访客对于网站的平均访问次数。 | `[Visits] / [Unique Visitors]` |
| 估计独特访客(ITP 2.1) | 对于ITP访客（使用Safari浏览器的用户），将“独特访客”除以2或更少。 此计算量度假定您是使用客户端JavaScript（不使用CNAME实施）设置Cookie的。 从ITP 2.1开始，使用客户端JavaScript设置Cookie的实施受到影响。请参阅 [智能防跟踪](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 以了解详细信息。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| 页面查看数/估计的独特访客数 (ITP 2.1) | 估计的独特访客数 (ITP 2.1) 查看的平均页数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
