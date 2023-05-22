---
description: Adobe提供您可以使用的各種計算量度。 此頁面列出這些量度及其預期用途。
title: 默认计算量度
feature: Calculated Metrics
exl-id: 08d11cce-170e-42a2-806f-e0a28b70a2dc
source-git-commit: 8c8e2db9b42deee081ce3b74481d0ad82c76818f
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 50%

---

# 默认计算量度

Customer Journey Analytics提供各種計算量度，涵蓋最常見的使用案例。 這些計算量度預設可在Analysis Workspace中使用。

以下為Adobe提供的每個計算量度清單，以及其預期函式及用來計算該函式的基礎公式：

>[!NOTE]
>
>除了本頁面所述的預設計算量度外，您也可以新增其他計算量度至資料檢視。
>
>您可以:
> * 為串流媒體新增預設計算量度，如所述 [計算量度](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * 從現有量度建立自訂計算量度，如所述 [計算與進階計算（衍生）量度](/help/components/calc-metrics/cm-adv-functions.md).



| 計算量度名稱 | 函数 | 公式 |
|---------|----------|---------|
| 跳出率 | 包含單一事件的造訪次數與該頁面上的造訪次數之間的比率。 這可協助您瞭解哪些維度專案具有最高的跳出率，或檢視網站在一段時間內彙總的跳出率。 | `[Bounces] / [Entries]` |
| 收入/訪客 | 每个访问网站的单独访客产生的平均收入金额。 | `[Revenue] / [Unique Visitors]` |
| 订购/访客 | 每位訪客在網站上產生的平均訂單或交易數 | `[Orders] / [Unique Visitors]` |
| 收入/造訪 | 单次访问网站产生的平均收入金额。 | `[Revenue] / [Visits]` |
| 收入/訂單 | 网站上每笔完成的交易或订单所产生的平均收入金额。 | `[Revenue] / [Orders]` |
| 订购/访问 | 对网站的访问完成交易的百分比。 | `[Orders] / [Visits]` |
| 页面查看/访问 | 用户单次访问网站期间查看的平均页数。 | `[Page Views] / [Visits]` |
| 造訪/訪客 | 独特访客对于网站的平均访问次数。 | `[Visits] / [Unique Visitors]` |
| 重新載入/頁面檢視 | 导致重新加载或刷新页面的页面查看次数的百分比。 | `[Reloads] / [Page Views]` |
| 加权跳出率 | 函数 | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |
| 訂購協助 | 渠道或来源促成客户历程向购买推进但最终未购买的次数。 | `[Orders (Visit Participation)] - [Orders]` |
| 退出率 | 查看特定页面后离开网站的访客的百分比。 | `[Exits] / [Visits]` |
| 登录率 | 在给定页面上进入网站的访客占网站上会话总数的百分比。 | `[Entries] / [Visits]` |
| 網站平均逗留時間 | 访客在离开或导航到别处之前在网站上逗留的平均时长。 | `[Average Time Spent on Site (Seconds)]` |
| 逗留時間/使用者（州） | 訪客平均在網站上逗留於特定州的時間長度 | `[Mobile App Users] (filter)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| 使用者（行動） | 行動應用程式的使用者總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 應用程式使用者 | 行動應用程式的使用者總數 | `[Mobile App Users] (filter)`<br>`[Unique Visitors] (metric)` |
| 狀態檢視 | 應用程式不同狀態或畫面的檢視次數 | `[Mobile App Users] (filter)`<br>`[Page Views] (metric)` |
| 操作 | 應用程式中執行的動作總數 | `[Has an Action] (filter)`<br>`[Custom Link Instances] (metric)` |
| 贏取連結點按次數 | 人员点击旨在产生网站流量的链接的次数。 | `[Campaign Click-throughs]` |
| 頁面速度 | 一段內容產生的其他頁面檢視次數。 這可協助您判斷哪些內容可促進更多參與。 | `[Page Views] / [Visits]` |
| 转化率 | 执行了所需操作（如进行了购买）的访客的百分比。 | `[Orders] / [Visits]` |
| 平均工作階段長度（行動） | 单个会话期间访客在网站上逗留的平均时长。 | 空白 |
| Experience Cloud ID 覆盖 | 拥有 Experience Cloud ID 的访客的百分比。 | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| 内容周转率 | 在网站上创建和发布新内容的速度以及新内容能够多快地吸引用户参与。 | `[Page Views] / [Visits]` |
| ITP 2.1不重複訪客/不重複訪客 | 显示使用受 ITP 2.1 Cookie 限制影响的浏览器的独特访客百分比。换言之就是不使用 CNAME 实现的客户。（这适用于通过客户端 JavaScript 设置 Cookie 的客户。） | `[Unique Visitors metric with ITP Visitors filter] / [Unique Visitors]` |
| 不重複訪客/7天後回訪的不重複訪客 | 在 7 天或更长时间后回访的独特访客的百分比。 | `[Unique Visitors metric with Users returning after 7 days filter] / [Unique Visitors]` |
| 頁面檢視/不重複訪客 | 每个访问网站的独特访客查看的平均页数。 | `[Page Views] / [Unique Visitors]` |
| 访问数/访客数 | 独特访客对于网站的平均访问次数。 | `[Visits] / [Unique Visitors]` |
| 預估不重複訪客(ITP 2.1) | 若為ITP訪客（使用Safari瀏覽器的使用者），請將不重複訪客除以2或更少。 此計算量度假設您是使用使用者端JavaScript （而非使用CNAME實作）設定Cookie。 從ITP 2.1開始，使用使用者端JavaScript設定Cookie的實施會受到影響。另請參閱 [智慧型追蹤預防](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) 以取得詳細資訊。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |
| 页面查看数/估计的独特访客数 (ITP 2.1) | 估计的独特访客数 (ITP 2.1) 查看的平均页数。 | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) filter] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) filter]` |

{style="table-layout:auto"}
