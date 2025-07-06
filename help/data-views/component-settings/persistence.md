---
title: 持久性组件设置
description: 决定维度值如何或是否从一个事件保持到下一个事件。
exl-id: b8b234c6-a7d9-40e9-8380-1db09610b941
solution: Customer Journey Analytics
feature: Data Views
role: Admin
source-git-commit: 8e10818efa7da54b0802c56e5388e6c7ef7fd8b6
workflow-type: tm+mt
source-wordcount: '1037'
ht-degree: 80%

---


# [!UICONTROL 持久性]组件设置 {#persistence-component-settings}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="dataview_component_dimension_persistence"
>title="持久性"
>abstract="配置应用于某个维度的默认分配模型。在报告中先用分配，然后用区段。"

<!-- markdownlint-enable MD034 -->



[!UICONTROL 持久性]是指某个给定的维度值能否归因于其所设置事件之外的某个量度。它使用分配和有效期限的组合。

![突出显示“持久性”选项的数据视图窗口](../assets/persistence.png)

* 通过&#x200B;**分配**&#x200B;可让您决定在一列中一次可保留多个维度项的情况下保留哪个值。

  >[!NOTE]
  >
  >如果您在报告中的某个量度上设置了[非默认归因模型](/help/data-views/component-settings/attribution.md)，则该归因模型会忽略您在同一报告的维度上设置的分配。
  >
  >但是，在执行包含多个维度的[完整表格导出](/help/analysis-workspace/export/export-cloud.md)时，归因会保留应用于每个维度的分配模型。

* 通过&#x200B;**有效期限**，可决定维度项在从中设置它的事件之外保持多久。

[!UICONTROL 持久性]仅在维度中可用，并且可追溯至应用该持久性的数据。 这一数据转换在应用分段或其他分析操作之前立即发生。

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 设置持久性] | 为维度启用持久性。如果未启用持久性，则维度仅与同一事件中存在的指标相关。默认下禁用此设置。 |
| [!UICONTROL 分配] | 指定在维度上使用用于持久性的分配模型。 选项如下：<ul><li>**[!UICONTROL 最近]**：维度中的值会一直保留，直到被后续值覆盖</li><li> **[!UICONTROL 原始]**：此维度的第一个值会持续存在，且不会被后续值覆盖</li><li>**[!UICONTROL 全部]**：同时保持此维度的所有值</li><li>**[!UICONTROL 第一个已知]**：使用此维度的第一个值，并将其应用于之前和之后的所有事件。</li><li>**[!UICONTROL 最后一个已知]**：使用此维度的最后一个值，并将其应用于之前和之后的所有事件。</li></ul> |
| [!UICONTROL 有效期限] | 指定维度的持久性窗口。 选项如下： <ul><li>**[!UICONTROL 会话]**（默认）</li><li>**[!UICONTROL 人员]**</li><li>**[!UICONTROL 自定义时间]**</li><li>**[!UICONTROL 量度]**</li></ul>。可能需要能够在购买（如内部搜索词或其他促销用例）时让维度到期。可设置的最长到期时间为90天。 如果选择[!UICONTROL 全部]分配，则仅有[!UICONTROL 会话]或[!UICONTROL 人员]有效期限可用。 |

{style="table-layout:auto"}

## [!UICONTROL 分配]设置

可用的分配设置包括：

* **[!UICONTROL 最近]**：保留维度中现在的最新（按时间戳）值。在维度的有效期内任何后续出现的值均替换以前保留的值。如果在此维度上的[无值选项](no-value-options.md)下启用了“将‘无值’视为值”，则将用空值覆盖以前保留的值。例如，请考虑下表，其中具有[!UICONTROL 最近]的分配和[!UICONTROL 会话]的有效期限：

  | 维度 | 第 1 次点击 | 第 2 次点击 | 第 3 次点击 | 第 4 次点击 | 第 5 次点击 |
  | --- | --- | --- | --- | --- | --- |
  | 数据集值 |  | C | B |  | A |
  | 最近分配 |  | C | B | B | A |

* **[!UICONTROL 原始]**：在有效期持续时间内，按时间戳保留维度内存在的原始值。 如果此维度具有值，则在后续事件中看到不同的值时不会覆盖它。 例如，请考虑下表，其中具有[!UICONTROL 原有]的分配和[!UICONTROL 会话]的有效期限：

  | 维度 | 第 1 次点击 | 第 2 次点击 | 第 3 次点击 | 第 4 次点击 | 第 5 次点击 |
  | --- | --- | --- | --- | --- | --- |
  | 数据集值 |  | C | B |  | A |
  | 原有分配 |  | C | C | C | C |

* **[!UICONTROL 全部]**：其行为方式类似于指标的[!UICONTROL 参与率]归因模型。同等地保留所有值，以使每个值都能对报告中的指标发挥完整的作用。例如，请考虑下表，其中具有[!UICONTROL 全部]的分配和[!UICONTROL 会话]的有效期限：

  | 维度 | 第 1 次点击 | 第 2 次点击 | 第 3 次点击 | 第 4 次点击 | 第 5 次点击 |
  | --- | --- | --- | --- | --- | --- |
  | 数据集值 | A | B | C |  | A |
  | 全部分配 | A | A、B | A、B、C | A、B、C | A、B、C |

* **[!UICONTROL 第一个已知]**&#x200B;和&#x200B;**[!UICONTROL 最后一个已知]**：（2022 年 1 月 19 日）这两个分配模型满足“进入”和“退出”维度用例。它们采用指定持久性范围（会话、人员或带回溯的自定义时间段）内某个维度的第一个或最后一个观察值，并将其应用于指定范围内的所有事件。示例：

  | 维度 | 第 1 次点击 | 第 2 次点击 | 第 3 次点击 | 第 4 次点击 | 第 5 次点击 |
  | --- | --- | --- | --- | --- | --- |
  | 时间戳（分钟） | 1 | 2 | 3 | 6 | 7 |
  | 原有值 |  | C | B |  | A |
  | 第一个已知 | C | C | C | C | C |
  | 最后一个已知 | A | A | A | A | A |


## [!UICONTROL 有效期限]设置

可用的过期设置包括：

* **会话**：在给定会话后到期。默认有效期限时段。
* **人员报告期**：在报告期结束时到期。
* **全球帐户报告期** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：报告期结束时到期。
* **帐户报告期** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：报告期结束时到期。
* **机会报告期** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：报告期结束时到期。
* **购买群组报告期** [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：报告期结束时到期。
* **自定义时间**：在指定时段（最多 90 天）后过期。仅对“原有”和“最近”分配模型有此有效期限选项。在使用基于时间的有效期限时，将考虑报告时段（最长 90 天）开始之前的值。
* **量度**：当可在事件中看到此量度时，立即使维度中的持久值过期。可将任何指标用作此维度的有效期限结束。仅对“原有”和“最近”分配设置有此有效期限选项。


## [!UICONTROL 绑定维度]

一个下拉菜单，可让您将维度值的持久性绑定到另一个维度中的维度值。 有效的选项包括数据视图中包含的其他维度。

有关如何有效使用绑定维度的示例，请参阅[在Customer Journey Analytics中使用绑定维度和量度](../../use-cases/data-views/binding-dimensions-metrics.md)。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [绑定维度](https://video.tv.adobe.com/v/342694/?quality=12&learn=on){target="_blank"}以观看演示视频。

>[!ENDSHADEBOX]


## [!UICONTROL 绑定量度]

一个下拉菜单，可让您选择充当绑定触发器的量度。 有效的选项包括数据视图中包含的量度。

此设置仅在对象数组中的绑定维度低于组件时显示。当绑定量度显示在事件中时，维度值会从事件级别维度向下复制到绑定维度的较低架构级别。

有关如何有效使用绑定维度的更多信息，请参阅[在Customer Journey Analytics](../../use-cases/data-views/binding-dimensions-metrics.md)中使用绑定维度和量度下的第二个示例。
