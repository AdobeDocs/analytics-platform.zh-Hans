---
title: 比较通过 Analytics Source Connector 传递的 Analytics 数据的术语
description: 一些术语差异
solution: Customer Journey Analytics
exl-id: f0f9aa1e-f9d2-4dcb-bbe9-7960412c094b
feature: Basics
role: User
TQID: https://experienceleague.adobe.com/nGTgotKQlT8vjh1BBS4TOOAbcsSRUy25O-nWIl-BkcM
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 8a3e3079823883d40e596680f860f8036a86baa2
workflow-type: tm+mt
source-wordcount: 844
ht-degree: 90%

---

# 比较通过 Analytics Source Connector 传递的 Analytics 数据的术语

Adobe Analytics、数据馈送、Analytics Source Connector/数据湖和 Customer Journey Analytics 在一些术语方面存在差异。 本专题旨在强调和澄清这些差异。

| 相关术语 | Adobe Analytics | Adobe Analytics 数据馈送 | Analytics Source Connector/数据湖 | Customer Journey Analytics | 注释 |
|---|---|---|---|---|---|
| <ul><li>[!UICONTROL 点击量]</li><li>[!UICONTROL 发生次数]</li><li>[!UICONTROL 记录]</li><li>[!UICONTROL 事件]</li></ul> | **[!UICONTROL 发生次数]**&#x200B;量度，<br><br>请参见：<ul><li>[Adobe Analytics 中使用的术语](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html)</li><li>[发生次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/occurrences.html?lang=zh-Hans)</li></ul> | 数据馈送文件中的行数（记录） | 数据集中的行数（记录），<br><br>请参见：<ul><li>[比较 Adobe Analytics 数据和 Customer Journey Analytics 数据](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=zh-Hans)</li></ul> | **[!UICONTROL 事件]**&#x200B;量度 | <ul><li>在 Adobe Analytics 中，“点击次数”和“发生次数”是同义词。</li><li>请参见下面的&#x200B;_自定义事件_。</li><li>某些数据在通过 Analytics Source Connector 传输到 Adobe Experience Platform 时会经过筛选。 请参阅[比较 Adobe Analytics 数据和 Customer Journey Analytics 数据](https://experienceleague.adobe.com/docs/analytics-platform/using/troubleshooting/compare.html?lang=zh-Hans) |
| <ul><li>[!UICONTROL 独特访客]</li><li>[!UICONTROL 独特设备]</li><li>[!UICONTROL 独特 Cookie]</li></ul> | **[!UICONTROL 独特访客]**&#x200B;量度，<br><br>请参见：<ul><li>[Adobe Analytics 中使用的术语](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html)</li><li>[独特访客](https://experienceleague.adobe.com/docs/analytics/components/metrics/unique-visitors.html)</li></ul> | **post\_visid\_high &amp; post\_visid\_low**&#x200B;的不同值连接在一起。<br><br>请参阅：<ul><li>[使用数据馈送计算常用量度](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html)</li></ul> | **endUserIDs的不同计数。\_experience.aaid.id** | 如果选择&#x200B;**endUserIDs.\_experience.aaid.id**&#x200B;作为人员ID，则为&#x200B;**人员**&#x200B;指标。 | <ul><li>Adobe Analytics 中的“人员”通常与“设备标识符”相关联，例如 Cookie。 AAID 是 Adobe Analytics 中的主要设备标识符，而不是 ECID。 另请参见 [AAID、ECID、AACUSTOMID 和 Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/aaid-ecid-adc.html?lang=zh-Hans)。</li><li>“访客”并不是 Customer Journey Analytics 中现成的量度。 但是，如果您选择&#x200B;**endUserIDs.\_experience.aaid.id**&#x200B;作为人员ID，则Customer Journey Analytics中的“人员”量度大致相当于Adobe Analytics中的“独特访客”。</li></ul> |
| <ul><li>[!UICONTROL 人员]</li></ul> | **人员**&#x200B;量度，<br><br>请参见：<ul><li>[人员](https://experienceleague.adobe.com/docs/analytics/components/metrics/people.html?lang=zh-Hans)</li></ul> | 不可用 | **_\&lt;path\>_.stitchedId**&#x200B;的不同计数（仅在缝合数据集中可用） | **人员量度** | <ul><li>Customer Journey Analytics 中的“人员”量度是与“个人 ID”的不同计数。 根据您在 Customer Journey Analytics 连接中选择的“个人 ID”，“人员”量度可能会表示不同的含义。</ul></li> |
| <ul><li>[!UICONTROL 访问次数]</li><li>[!UICONTROL 会话]</li></ul> | **[!UICONTROL 访客]**&#x200B;量度，<br><br>请参见：<ul><li>[Adobe Analytics 中使用的术语](https://experienceleague.adobe.com/docs/analytics/technotes/terms.html)</li><li>[访问次数](https://experienceleague.adobe.com/docs/analytics/components/metrics/visits.html?lang=zh-Hans)</li><li>[报告时处理](https://experienceleague.adobe.com/docs/analytics/components/virtual-report-suites/vrs-report-time-processing.html?lang=zh-Hans)</ul></li> | **post\_visid\_high， post\_visid\_low， visit\_num &amp; visit\_start\_time\_gmt**&#x200B;的不同值连接在一起。<br><br>请参阅：<ul><li>[使用数据馈送计算常用量度](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html)</li></ul> | 不可用 | **会话**&#x200B;量度 | <ul><li>通过 Adobe Analytics 虚拟报告包和 Customer Journey Analytics 数据视图中的报告时处理功能，可以配置访问（会话）的概念。 因此，根据应用的定义，不同环境之间的访问（会话）计数可能不同。 另请参阅[比较 Adobe Analytics 和 Customer Journey Analytics 报告功能之间的数据处理](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/data-processing-comparisons.html)和[虚拟报告包、数据视图、Adobe Experience Platform 沙盒和 Analytics Source Connector](https://experienceleague.adobe.com/docs/analytics-platform/using/compare-aa-cja/cja-aa-comparison/vrs-dataview-sandbox-adc.html)。 |
| <ul><li>自定义事件</li><li>成功事件</li></ul> | 自定义事件 1-1000 | **post\_events\_list**<br><br>，请参见：<ul><li>[使用数据馈送计算常用量度](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-calculate.html) | **\_experience.analytics.<ul>event1to100.event1 &#x200B;** 到<br>**&#x200B; event901to1000.event1000 &#x200B;**</ul> | **\_experience.analytics.<ul>event1to100.event1 &#x200B;** 到<br>**&#x200B; event901to1000.event1000 &#x200B;**</ul> | <ul><li>Adobe Analytics 中的“事件”是一个[成功事件](https://experienceleague.adobe.com/docs/analytics/components/metrics/custom-events.html?lang=zh-Hans)（自定义事件），已在 Adobe Analytics 图像请求（数据收集服务器调用）中设置。</ul> |
| <ul><li>重复事件删除</li><li>重复量度删除</ul></li> | 请参阅:<ul><li>[事件 ID 序列化](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=zh-Hans)</li></ul> | **post_events_list** 列包含已去重的事件量度。<br><br>请参阅 <ul><li>[数据列引用](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html). </ul></li> | 不可用 | 请参阅:<ul><li>[重复量度删除组件设置](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/component-settings/metric-deduplication.html?lang=zh-Hans) | <ul><li>Adobe Analytics 中的重复事件/量度删除功能与 Customer Journey Analytics 略有不同。 在 Adobe Analytics 中，重复数据删除发生在数据处理时。 在 Customer Journey Analytics 中，重复数据删除发生在报告运行时，以提供更大的灵活性。 Adobe Analytics 与 Customer Journey Analytics 中删除的重复量度可能略有不同。</li></ul> |
| <ul><li>[!UICONTROL 实例]量度</li></ul> | 请参阅:<ul><li>[实例](https://experienceleague.adobe.com/docs/analytics/components/metrics/instances.html) | “pre”变量不为空的次数（例如 eVar1）。 | “mid”变量不为null的次数（例如&#x200B;**\_experience.analytics.<br>customDimensions.eVars.eVar1&#x200B;**）。 | 可通过[从 eVar 字段创建量度](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views-usecases.html?lang=zh-Hans)而创建&#x200B;**&#x200B;实例数**&#x200B;量度。 | <ul><li>[!UICONTROL 实例数一般与 prop 和 eVar 列关联，作为一种确定已设置变量多少次的方法。] |

{style="table-layout:auto"}
