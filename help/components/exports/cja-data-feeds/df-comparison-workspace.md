---
description: 了解如何比较Customer Journey Analytics和Adobe Analytics中的数据馈送功能
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: 比较Customer Journey Analytics和Adobe Analytics中的数据馈送功能
feature: Components
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 7f3fb46b9c1928f8b02ce2108b4e98b5cc8da766
workflow-type: tm+mt
source-wordcount: '1140'
ht-degree: 0%
---
# 了解数据馈送和Analysis Workspace之间的数据差异

{{release-limited-testing}}

数据馈送导出中的数据并不总是与您在Analysis Workspace中看到的数据完全匹配。 本页上的信息说明了一些主要原因。

这些差异中有一些来自Workspace行为，单独在Workspace报表中很难看到这些行为，因为Workspace数据是汇总的。 数据馈送会提供事件级别的数据，因此当您将数据馈送输出与Workspace报表进行比较时，这些行为会变得明显。

## 处理窗口（数据馈送）与报表窗口(Analysis Workspace)的比较 {#processing-window}

每个数据馈送提交都使用滚动的30天处理时段。 处理窗口提供在数据馈送投放中对事件进行分类所需的历史上下文。 有关处理窗口的详细信息，包括示例，请参阅[了解处理窗口](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-window)。

从这个意义上说，处理窗口类似于Analysis Workspace中的报表窗口（您为报表选择的日期范围）。 然而，两者之间有着关键的区别。

| 主要差异 | 报表窗口(Analysis Workspace) | 处理窗口（数据馈送） |
|---------|---------|----------|
| **报告的时间范围**<br/>&#x200B;报告或信息源中包含哪些事件 | 从报告窗口开始的日历月的第一天开始，并在报告窗口结束时结束。<p>例如，报告时段为10月6日至11月5日的报告还包括10月1日至10月5日的事件。 由于Workspace数据是聚合的，因此可能很难注意到这些额外的事件。</p><!--SME CHECK: Confirm that every Workspace report includes events from the first day of the calendar month in which the reporting window starts (per Luke, Nov 5, 2026), including segment qualification for segments limited to the reporting window. Other docs (persistence.md Person Reporting Window row, analysis-workspace/attribution/models.md lookback window) don't describe this yet.--> | 与处理窗口不同。 <p>要报告的时间范围是频率窗口，它可以是一小时，也可以是处理窗口末尾的一天。</p> |
| **数据边界**<br/>&#x200B;窗口外部的数据是否包含在报表或馈送中或影响报表或馈送 | 灵活<p>报表窗口开始的日历月第一天的事件，即使它们早于报表窗口，也会包含在Workspace报表中。 有关详细信息，请参阅上面的&#x200B;**报告的时间范围**。</p><p>超出报表窗口的事件还可通过以下任意因素影响Workspace报表中的数据：</p><ul><li>**Dimension持久性**：使用会话、自定义时间或量度[过期时间](/help/data-views/component-settings/persistence.md#expiration-settings)时，持久性可能超出报告窗口。</li><li>**区段鉴别**：默认情况下，区段可以超出报表窗口。<p>在创建区段时，用户可以选择将区段限制在报告窗口内。 即使这样，区段鉴别也会考虑报告窗口开始的日历月第一天的事件。</p></li><li>**会话计算**：会话可以超出报告窗口。 </li><li>**派生字段转换**：引用容器的任何派生字段函数都使用报告窗口。<!--SME CHECK: Confirm that Session- and Person-scoped derived field functions (Deduplicate, Next or Previous, Summarize, Date Math) are limited to the reporting window in Workspace, or whether Session scope can extend beyond it like session calculation. ALSO: In the Segment qualification bullet, add a link to the new docs about limiting a segment to the reporting window.--></li></ul> | 固定<p>数据馈送中仅包含频率窗口中的事件。 有关详细信息，请参阅上面的&#x200B;**报告的时间范围**。</p><p>落在频率窗口之外但在处理窗口之内的事件可能会影响数据馈送中的数据。 通常情况下，落在处理窗口之前的事件无法运行。 处理窗口会限制以下因素：</p><ul><li>**Dimension持久性**：在使用会话、人员报告窗口或量度[过期](/help/data-views/component-settings/persistence.md#expiration-settings)时，无法保留超出处理窗口的时间。 与Workspace不同，回看不会扩展到当月的第一天。 使用自定义时间[过期](/help/data-views/component-settings/persistence.md#expiration-settings)时，在处理窗口之外（最多90天）仍然有效，与Workspace中相同。 在Workspace和数据馈送中，自定义时间回顾不会扩展到每月的第一天。<p>**注意：**&#x200B;当前，自定义时间过期时间也仅限于处理时段。 即将支持超出处理时段的自定义时间。</p></li><li>**区段鉴别**：始终限于处理窗口。 与Workspace不同，不会延长到当月的第一天。</li><li>**会话计算**：始终限于处理时段。</li><li>**派生字段转换**：引用容器的任何派生字段函数在数据馈送导出中使用处理窗口。</li></ul> |

>[!BEGINSHADEBOX]

**示例**

以下示例说明了报表窗口和处理窗口之间的差异如何导致Workspace报表和数据馈送交付之间存在数据差异。

* **报告的时间范围**：用户在10月1日有一个事件设置了一个维度值，并且在10月晚些时候有更多的事件设置。 具有从10月6日开始的报表窗口的Workspace报表包括10月1日事件，因为Workspace包括从该月第一天开始的事件。 10月1日设置的值还可以保留到报告窗口中的用户事件。 具有从10月6日开始的处理窗口的数据馈送投放不会考虑10月1日事件，因此它设置的值不会保留到投放中的用户事件。

* **区段鉴别**： 45天前具有人员容器且今天有事件的用户符合区段鉴别。 具有30天报告窗口的Workspace报表包含用户事件，因为默认情况下，区段可以超出报告窗口。 今天的数据馈送交付不包括事件，因为区段资格限制为30天的处理时段。

<!-- update the following graphic: ![Data differences between workspace and data feeds](assets/data-feed-data-differences.png) -->

>[!ENDSHADEBOX]

## 拼接重播

每次运行拼接重放时，历史身份数据都会进行追溯更新。

数据馈送和Analysis Workspace对拼接重播的处理方式不同，如下所示：

* **数据馈送**：仅在导出时反映拼接的标识。 重放结果不会逆向应用于导出的文件。

* **Analysis Workspace**：显示最新拼接数据，每次重放运行时都会追溯更新。 每次重放后历史数据都会发生更改，因此Workspace始终反映最新的身份分辨率。

## 迟到的事件

在数据馈送中，事件可能会在数据馈送导出窗口关闭后到达。

数据馈送和Analysis Workspace对于过去事件的功能有所不同，如下所示：

* **数据馈送**：根据事件时间戳，导出固定时间窗口（每次投放的小时或一天）内的数据。

  在处理每次投放之前，Customer Journey Analytics会等待您选择的[处理延迟](/help/components/exports/cja-data-feeds/create-feed.md#data-feed-processing-delay)。 在处理延迟期间到达的事件包含在投放中。 处理开始后到达的事件不包括在数据馈送文件中。

* **Analysis Workspace**：在报告时处理数据，因此事件包含在报告中，而不管它们是在何时收到的。

## 数据批处理

有时，数据会以跨越较长时段的批处理提交。

数据馈送和Analysis Workspace在批量数据方面的功能有所不同，如下所示：

* **数据馈送**：根据原始时间戳，在每天或每小时分发批处理数据。 例如，包含30天数据的批次会分布在30天的导出中，因此在任何单个导出中只显示一小部分。

* **Analysis Workspace**：在批处理完全处理完毕后立即显示批处理中的所有数据，而不考虑批处理中包含的时间范围。

