---
description: 了解如何比较Customer Journey Analytics和Adobe Analytics中的数据馈送功能
keywords: 点击流;数据馈送;数据馈送;数据馈送
title: 比较Customer Journey Analytics和Adobe Analytics中的数据馈送功能
feature: Components
hide: true
source-git-commit: 7fe885e928c495a2518038645ec841229d1f1852
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 0%

---

# 了解数据馈送和Analysis Workspace之间的数据差异

{{release-limited-testing}}

数据馈送导出中的数据并不总是与您在Analysis Workspace中看到的数据完全匹配。 本页上的信息说明了一些主要原因。

## 回顾日期范围（数据馈送）与报表日期范围(Analysis Workspace)

数据馈送中的回顾日期范围决定在查找符合数据馈送交付条件的事件时，Customer Journey Analytics回顾的时间范围。 有关回顾日期范围的详细信息，包括示例，请参阅[了解回顾日期范围](/help/components/exports/cja-data-feeds/create-feed.md#understand-the-lookback-date-range)。

从这个意义上说，回顾日期范围类似于Analysis Workspace中的报表日期范围。 然而，两者之间有着关键的区别。

| 主要差异 | 报表日期范围(Analysis Workspace) | 回顾日期范围（数据馈送） |
|---------|---------|----------|
| **数据边界**<br/>&#x200B;数据是否包含在报表或馈送中 | 灵活<p>如果事件受以下任何因素影响，则超出报表日期范围的事件仍可包含在Workspace报表中：</p><ul><li>**Dimension持久性**：使用会话、自定义时间或量度[过期时间](/help/data-views/component-settings/persistence.md#expiration-settings)时，持久性可能超出报表日期范围。 与使用人员报告窗口[到期](/help/data-views/component-settings/persistence.md#expiration-settings)时的报告日期范围相同。 数据会被聚合。</li><li>**区段鉴别**：默认情况下，区段可以超出报表日期范围。<p>用户在创建区段时，可以选择将区段限制为报告日期范围。<!--add link to new docs--></p></li><li>**会话计算**：会话可以超出报告日期范围。 </li><li>**派生字段转换**</li></ul> | 固定<p>不在回顾日期范围内的事件绝不会包含在数据馈送中，无论它们是否受以下因素影响：</p></p><ul><li>**Dimension持久性**：在回看日期范围之外无法持续存在，无论[过期设置](/help/data-views/component-settings/persistence.md#expiration-settings)如何。 数据不会聚合。</li><li>**区段鉴别**：始终限于回顾日期范围。</li><li>**会话计算**：始终限于回顾日期范围。</li><li>**派生字段转换**：引用容器的任何派生字段函数在数据馈送导出中使用回顾日期范围。</li></ul><p>有关配置回顾日期范围的详细信息，请参阅[创建数据馈送](/help/components/exports/cja-data-feeds/create-feed.md#create-and-configure-a-data-feed)。</p> |
| **报告窗口**<br/>&#x200B;报告的时间范围 | 与报告时段（要报告的时间范围）相同。 | 与要报告的时间范围不同。 <p>要报告的时间范围是“频率”窗口，可以是1小时或1天。</p> |

>[!BEGINSHADEBOX]

**示例**

以下示例说明了报表日期范围和回顾日期范围之间的差异如何导致Workspace报表和数据馈送交付之间存在数据差异。

事件A发生在85天之前，它位于具有90天持久性设置的维度上（例如，营销活动点击归因窗口）。 事件包含在Analysis Workspace报表中，而不包含在数据馈送交付中。

![工作区和数据馈送之间的数据差异](assets/data-feed-data-differences.png)


>[!ENDSHADEBOX]

## 拼接重播

每次运行拼接重放时，历史身份数据都会进行追溯更新。

数据馈送和Analysis Workspace对拼接重播的处理方式不同，如下所示：

* **数据馈送**：仅在导出时反映拼接的标识。 重放结果不会逆向应用于导出的文件。

* **Analysis Workspace**：显示最新拼接数据，每次重放运行时都会追溯更新。 每次重放后历史数据都会发生更改，因此Workspace始终反映最新的身份分辨率。

## 迟到的事件

在数据馈送中，事件可能会在数据馈送导出窗口关闭后到达。

数据馈送和Analysis Workspace对于过去事件的功能有所不同，如下所示：

* **数据馈送**：根据收到事件的时间，导出固定时间范围内的数据。

  在窗口关闭后到达的事件可能不包括在导出中。 这受您选择的[回顾日期范围](#lookback-date-range-data-feeds-vs-reporting-date-range-analysis-workspace)的影响。

* **Analysis Workspace**：在报告时处理数据，因此事件包含在报告中，而不管它们是在何时收到的。

## 数据批处理

有时，数据会以跨越较长时段的批处理提交。

数据馈送和Analysis Workspace在批量数据方面的功能有所不同，如下所示：

* **数据馈送**：根据原始时间戳，在每天或每小时分发批处理数据。 例如，包含30天数据的批次会分布在30天的导出中，因此在任何单个导出中只显示一小部分。

* **Analysis Workspace**：在批处理完全处理完毕后立即显示批处理中的所有数据，而不考虑批处理中包含的时间范围。

