---
description: Adobe提供各种您可以使用的计算指标。 本页列出了这些量度及其预期用途。
title: 默认计算量度
feature: Calculated Metrics
source-git-commit: 5d6942af4ac3f999c5e7fd7d6ba74a5fe7a26a9d
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 4%

---

# 默认计算量度

Customer Journey Analytics提供了各种计算量度，以涵盖最常见的用例。 默认情况下，这些计算量度在Analysis Workspace中可用。

以下是Adobe提供的每个计算指标及其目标函数以及用于计算它的基础公式的列表：

>[!NOTE]
>
>除了此页面上描述的默认计算指标之外，您还可以向报表包添加其他计算指标。
>
>您可以:
> * 为流媒体添加默认计算指标，如中所述 [计算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 从现有量度创建自定义计算量度，如中所述 [计算指标和高级计算（派生）指标](/help/components/calc-metrics/cm-adv-functions.md).



| 计算指标名称 | 函数 | 公式 |
|---------|----------|---------|
| 跳出率 | 包含一次点击的访问次数与该页面上的访问次数之间的比率。 这有助于您了解哪些维度项目的跳出率最高，或查看一段时间内网站的累计总跳出率。 | `[Bounces] / [Entries]` |
| 收入/访客 | 网站每位访客产生的平均收入金额。 | `[Revenue] / [Unique Visitors]` |
| 订购/访客 | 网站每位访客生成的平均订单数或交易数 | `[Orders] / [Unique Visitors]` |
| 收入/访问 | 单次访问网站产生的平均收入额。 | `[Revenue] / [Visits]` |
| 收入/订单 | 网站上每个已完成的交易或订单所产生的平均收入金额。 | `[Revenue] / [Orders]` |
| 订购/访问 | 导致完成交易的网站访问百分比。 | `[Orders] / [Visits]` |
| 页面查看/访问 | 用户在单次访问网站期间查看的平均页面数。 | `[Page Views] / [Visits]` |
| 访问/访客 | 独特访客访问网站的平均次数。 | `[Visits] / [Unique Visitors]` |
| 重新载入/页面查看次数 | 导致重新加载或刷新页面的页面查看次数的百分比。 | `[Reloads] / [Page Views]` |
| 加权跳出率 | 函数 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 订购协助 | 渠道或来源对客户购买历程做出了贡献，但未导致最终购买的次数。 | `[Orders (Visit Participation)] - [Orders]` |
| 退出率 | 查看特定页面后离开网站的访客百分比。 | `[Exits] / [Visits]` |
| 登录率 | 在给定页面上进入网站的访客相对于网站上会话总数的百分比。 | `[Entries] / [Visits]` |
| 网站平均逗留时间 | 访客离开或导航离开之前在网站上逗留的平均时间。 | `[Average Time Spent on Site (Seconds)]` |
| 逗留时间/用户（状态） | 访客在网站上处于某个特定状态所花费的平均时间 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 用户（移动设备） | 移动应用程序的用户总数 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 应用程序用户 | 移动应用程序的用户总数 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 状态视图 | 查看应用程序的不同状态或屏幕的次数 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| 操作 | 在应用程序中执行的操作总数 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| 客户获取链接点击次数 | 用户点击旨在提升网站流量的链接的次数。 | `[Campaign Click-throughs]` |
| 页面周转率 | 一段内容生成的其他页面查看次数。 这可以帮助您确定哪些内容可推动更多参与。 | `[Page Views] / [Visits]` |
| 转化率 | 执行所需操作（例如购买）的访客百分比。 | `[Orders] / [Visits]` |
| 平均会话时长（移动设备） | 在一次会话期间，访客在网站上逗留的平均时间。 | 空白 |
| Experience CloudID覆盖 | 具有Experience CloudID的访客所占的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 内容周转率 | 在网站上创建和发布新内容的速度以及它生成用户参与度的速度。 | `[Page Views] / [Visits]` |
| ITP 2.1独特访客/独特访客 | 使用浏览器且受ITP 2.1 Cookie限制影响的独特访客百分比。 换言之，客户不使用CNAME实施。 （这适用于通过客户端JavaScript设置Cookie的客户。） | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 7天后回访的独特访客/独特访客 | 在7天或更长时间后回访的独特访客的百分比。 | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| 页面查看次数/独特访客 | 网站每位独特访客查看的平均页面数。 | `[Page Views] / [Unique Visitors]` |
| 访问/访客 | 独特访客对网站的平均访问次数。 | `[Visits] / [Unique Visitors]` |
| 预计独特访客(ITP 2.1) | 对于ITP访客（使用Safari浏览器的用户），将独特访客数除以2或更少。 此计算量度假定您是使用客户端JavaScript（而不是使用CNAME实施）设置的Cookie。 从ITP 2.1开始，使用客户端JavaScript设置Cookie的实施受到了影响。参见 [智能防跟踪](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 了解详细信息。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| 页面查看次数/预计独特访客(ITP 2.1) | “预计独特访客”(ITP 2.1)的平均查看页面数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
