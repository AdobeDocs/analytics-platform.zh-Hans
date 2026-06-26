---
description: 了解如何比较Customer Journey Analytics和Adobe Analytics中的数据馈送功能
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: 比较Customer Journey Analytics和Adobe Analytics中的数据馈送功能
feature: Components
hide: true
exl-id: 32b71016-7c53-409f-9ce4-521a40e2eb96
autotag-review: '2026-05-19T08:44:26.806Z'
TQID: 'https://experienceleague.adobe.com/R7c5-VutwSkyghNvwC2gZv2KUEJoa263AN0Tkdg3w4o'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: b31ae6194d30115f4d653addaf5efff5790e987c
workflow-type: tm+mt
source-wordcount: 933
ht-degree: 2%

---

# 在Customer Journey Analytics和Adobe Analytics中比较数据馈送

Customer Journey Analytics和Adobe Analytics中的数据馈送允许您向第三方平台导出原始数据。 如果您之前在Adobe Analytics中使用过数据馈送，请使用以下信息了解可用功能和概念的差异：

| **概念和配置选项** | **Customer Journey Analytics** | **Adobe Analytics** |
|---------|----------|---------|
| **数据输入**<br/>&#x200B;可以收集并包含在数据馈送中的数据类型。 | 支持跨渠道数据输入，包括Web数据、呼叫中心数据、销售点数据等。 | 主要支持Web和移动数据输入。 其他数据类型（例如呼叫中心或销售点数据）可以通过数据源摄取，但处理能力非常有限。 |
| **数据处理**<br/>&#x200B;根据您使用的产品，将在不同阶段处理数据。 | 数据在&#x200B;**报告时间**&#x200B;处理，因此许多报告功能可用于更改历史数据，如拼接、派生字段和分段。 | 数据在&#x200B;**收集时间**&#x200B;处理，因此处理规则和VISTA规则等报表功能不会影响历史数据。 |
| **提交频率**<br/>&#x200B;确定发送数据馈送的频率以及馈送中包含的时间范围。 | **每日**（数据视图时区的午夜到午夜）或&#x200B;**每小时**。 | **每日**（报告包时区的午夜到午夜）或&#x200B;**每小时**。 15分钟信息源是可能的，但默认情况下不可用。 |
| **迟到的点击**<br/>&#x200B;时间戳属于上一个投放频率窗口但在该窗口已过之后到达的点击。 <p>例如，迟到的点击可能来自在离线时缓冲事件并在重新连接时发送这些事件的移动应用程序。</p> | **处理延迟**&#x200B;设置控制系统在频率窗口关闭后等待多长时间才触发导出，为延迟数据的到达分配额外时间。 | 通过&#x200B;**迟到的点击**&#x200B;配置选项，可以&#x200B;**包含或排除**&#x200B;迟到的点击。 <p>**回看窗口**&#x200B;设置控制系统回溯多远以包含延迟数据。</p> |
| **乱序点击**<br/>&#x200B;时间戳与接收顺序不匹配的点击。 | 由于Customer Journey Analytics同时接受流数据和批量数据，因此无法保证给定人员的事件将按时间戳顺序到达。 Customer Journey Analytics在报告时按每人时间戳重新排序数据。 <p>**处理延迟**&#x200B;设置通过为批处理数据在导出之前到达提供更多的时间，有助于减少数据馈送输出中的乱序事件。 不保证投放中的事件排序。</p><p>**重要信息**：您的数据馈送数据的最终使用者必须能够按人处理乱序的时间戳，因为不保证数据馈送交付中的点击排序。</p> | Adobe Analytics要求在收集时按每位访客的顺序到达数据，但不保证数据馈送交付中的点击排序。</p> |
| **回填窗口**<br/>&#x200B;导出两个过去日期之间的历史数据。 | 仅限于连接的滚动数据窗口。 | 限制为报表包数据保留限制：默认为&#x200B;**25个月**。 |
| **Segmentation** | 区段可以通过数据视图区段和/或馈送特定的区段应用于数据馈送。 | 无法应用区段。 |
| **拼合** | 支持。 启用跨设备身份解析，将跨设备的事件链接到单个人员。 | 不支持。 无法通过Adobe Analytics数据馈送导出拼合数据。 |
| **架构**<br/>&#x200B;数据馈送架构确定哪些列可以包含在数据馈送中。 | 数据馈送架构基于数据视图配置。  可包含在数据馈送架构中的组件是数据视图配置中可用组件的子集。</p> | 约1,100多个变量的预定义静态列表。 许多列将导出为&#x200B;**预处理对和后处理对**（例如，`eVar1` / `post_eVar1`），这占列数的大部分。 |
| **查找**<br/>&#x200B;动态查找允许您在数据馈送中接收其他查找文件，否则不可用。 | 不需要，因为查找和分类都可用作直接在数据视图中管理的维度。 在数据视图中作为维度组织查找或分类时，解析的值在Parquet输出中显示为常规列，与事件数据内联，而不是作为单独的引用文件。 | 用于将数据馈送列中的数字与实际值相匹配。 特定于一组特定对象（浏览器、操作系统、移动设备，并且作为数据馈送随附的单独文件应用。） |
| **会话定义**<br/> <!--(could be included in the data processing section instead)--> | 在数据视图中定义。 | 在收藏集时定义。 |
| **计算量度**<br/> | 不可用 | 不可用 |
| **持久性模型** | 灵活。 数据视图中的持久性设置（分配和到期）在生成馈送时在报告时应用。 支持数据视图中可用的所有分配设置：**原有**、**最近**、**全部**、**第一个已知**&#x200B;和&#x200B;**最后一个已知**。 | 仅表示&#x200B;**最近（最近联系）**&#x200B;和&#x200B;**原始值（首次联系）**&#x200B;归因模型。 线性分配的处理方式与最近联系相同。 |
| **输出文件格式** | Parquet<p>本机支持复杂的嵌套和结构化数据。 产品列表表示为结构化数组/嵌套对象。 </p><p>需要Parquet感知工具才能读取，例如BigQuery、Snowflake或Apache Spark。</p> | TSV<p>平坦、可读的行。 本身不支持结构化数据；复杂字段（如产品列表）必须编码为需要自定义分析逻辑的专有分隔字符串。</p> |
| **提交目标** | Amazon S3、Azure RBAC、Azure SAS、Google云平台。 | Amazon S3、Azure RBAC、Azure SAS、Google云平台。 还支持&#x200B;**SFTP**。 |

{style="table-layout:auto"}

<!-- Is this useful info to accompany the table? Not sure... **Hits**<br/>  | Only Hit 5 is in the data feed window. However, because the reporting window also includes Hit 4 and Hit 3 (which are late-arriving hits with timestamps from a previous data feed window), they are also included in the current data feed window.<p>Hits are reordered in the data feed according to their timestamp, as follows: Hit 3, Hit 4, Hit 5.</p> | Only Hit 5 is in the data feed window. However, because a lookback is configured and it includes Hit 4 and Hit 3 (which are late-arriving hits with timestamps from a previous data feed window), they are also included in the current data feed window. (If a lookback was not configured, only Hit 5 would be included in the data feed.) <p>Hits are shown in the data feed in the order they were received, as follows: Hit 4, Hit 3, Hit 5.</p> -->

<!-- Is all of this info redundant?  **Late-arriving hits**<br/> (If you send us data that is out of order per person would be if you are setting the timestamp. You can set the timestamp in 2 ways: you can have Adobe set the timestamp, based on when we received the data. Or you can set it yourself. If you're setting the timestamps and you sending us data that is out of order, it messes things up in AA. In AA, data needs to come in order per visitor. We need the right order of events. But in CJA, it doesn't matter what timestamps are on the data. CJA doesn't assign a timestamp to a hit. That is done upstream. CJA reorders the data once it arrives, so that everything is in the proper time sequence. Then we can do the report-time processing. That means you can have both streaming data and batch data. It doesn't matter. At the time it arrives, we reorder it and it becomes in order per person as a result. So in CJA we'll give you all the data we received in the last day or hour, but it's limited to the beginning of the reporting window. Most likely a huge chunk of the data you get in a day or hour belongs to that day or hour. If all you did was batch data from a call center, then that is what you would get out. In CJA, data can come in and it doesn't matter when it came in. So the data feed ustomer has to be able to handle this on their side. So wherever they're putting the data, it needs to handle the fact that timestamps could potentially be all over the place. This might be a challenge for some customers. They need to know this. Needs to be able to handle out of order data per person. It doesn't matter across people. ) Hits that should have been included in a previous data feed, but for some reason they arrived late (such as through timestamped hits or data sources). <p>These late-arriving hits are included in the current data feed at the time they arrive, even though their timestamps are within a previous data feed window. Every time a data feed processes data, it looks at any late hits that have arrived and batches them in the next data feed file that is sent.</p>  | Late-arriving hits that occur within the **[!UICONTROL Reporting window]** are always included. <p>The lookback window for these late-arriving hits is controlled through the **[!UICONTROL Reporting window]** configuration option.</p><p>Hits are automatically reordered based on timestamps; original values are persisted (no change feed).</p> | Can be included or excluded. Configurable with the **[!UICONTROL Late-arriving hits]** configuration option.<p>The lookback window for these hits is configured through the **[!UICONTROL Lookback window]** configuration option that is available for this specific purpose.</p><p>Hits are shown in the order in which they are received; they are not reordered according to timestamp.</p>   -->
