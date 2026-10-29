---
description: 了解管理员如何使用数据视图或数据字典向组件添加描述。
title: 添加组件描述
feature: Components
role: Admin
exl-id: 99d531cd-50e9-4e6c-adad-a66b606fd877
TQID: 'https://experienceleague.adobe.com/yXxEhHsXsAw-l9c0oVCNDtwoCUq86UZSnyiwvidKLWA'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: df28738e-9c71-4aa8-929e-edde22340cc6
    internal-label: Data Dictionary
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b46a27ff9faca74c3c2baa7938a588b643633705
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 10%
---
# 添加组件描述

描述可帮助用户了解在Analysis Workspace中构建项目或查看报表时如何使用各种组件。

Customer Journey Analytics管理员可以在数据视图内或使用数据字典为组件（维度、量度、区段和日期范围）添加描述。

## 数据视图

您可以向已添加到数据视图的组件添加说明。 查看[组件设置](/help/data-views/component-settings/overview.md)。

## 数据词典

Analysis Workspace中的数据字典可帮助用户和管理员跟踪并更好地了解其Customer Journey Analytics环境中的组件。 数据字典允许管理员直接在Analysis Workspace中添加组件描述。

有关编辑数据字典中的组件描述的信息，请参阅[编辑数据字典中的组件条目](/help/components/data-dictionary/edit-entries-data-dictionary.md)。

有关数据字典的一般信息，请参阅[数据字典概述](/help/components/data-dictionary/data-dictionary-overview.md)。

>[!MORELIKETHIS]
>
>[数据视图组件设置](/help/data-views/component-settings/overview.md)
>[数据字典组件条目](/help/components/data-dictionary/edit-entries-data-dictionary.md)
>

## 自动生成描述

{{release-limited-testing-section}}

Customer Journey Analytics可以使用创新型人工智能来为您编写描述，而不是手动编写每个描述。 您可以为单个组件生成说明，也可以同时为多个组件生成说明。

生成的描述：

* 长度不超过3个句子。
* 以Adobe使用AI **生成的文本**&#x200B;结尾，以便用户知道已生成描述。
* 可以在生成后进行编辑。

### 先决条件

在生成描述之前，您的组织必须同意某些创新型人工智能法律条款。 如果贵组织不同意这些术语，则用于生成描述的选项将灰显。 选择选项旁边的信息图标![信息](/help/assets/icons/InfoOutline.svg)以了解如何启用该功能，或与组织的管理员或Adobe帐户团队联系。

### 描述的生成方式

生成的描述基于组件的定义以及有关如何在数据视图中使用组件的其他上下文，例如：

* 维度的排名最前的项目
* 经常与组件一起使用的组件

当计算量度或区段引用另一个区段时，生成的描述将说明引用区段的定义。

### 从各种位置生成描述

您可以在Customer Journey Analytics的以下区域中生成描述。 某些位置允许您为多个组件生成描述，而其他位置则没有。

选择一个位置以了解如何在该位置生成描述。

| 位置 | 支持的组件 | 单个组件 | 多个组件 |
| --- | --- | --- | --- |
| [数据字典](/help/components/data-dictionary/edit-entries-data-dictionary.md) | <ul><li>维度</li><li>量度</li><li>计算量度</li><li>区段</li><li>日期范围</li></ul> | 是 | 是 |
| [数据视图](/help/data-views/component-settings/overview.md) | <ul><li>维度</li><li>量度</li><li>派生字段</li><li>共享量度和维度（有关详细信息，请参阅[共享量度和维度](#generate-descriptions-for-shared-metrics-and-dimensions)。）</li></ul> | 是 | 是 |
| [区段生成器](/help/components/segments/seg-builder.md) | 区段 | 是 | 否 |
| [区段管理器](/help/components/segments/seg-manage.md#action-bar) | 区段 | 否 | 是 |
| [计算量度生成器](/help/components/calc-metrics/cm-workflow/cm-build-metrics.md) | 计算量度 | 是 | 否 |
| [计算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md#action-bar) | 计算量度 | 否 | 是 |
| [日期范围生成器](/help/components/date-ranges/create.md#date-range-builder) | 日期范围 | 是 | 否 |
| [日期范围管理器](/help/components/date-ranges/manage.md#action-bar) | 日期范围 | 否 | 是 |

{style="table-layout:auto"}

### 生成共享量度和维度的描述

您只能从数据视图中生成共享量度和维度的描述，如[从不同位置生成描述](#generate-descriptions-from-various-locations)中的表所示。 无法从[共享量度和维度管理器](/help/data-views/shared-metrics-dimensions/smd-overview.md#smd-manager)生成描述。

在数据视图中生成共享量度或维度的描述时，请考虑以下事项：

* 该描述适用于共享该组件的所有数据视图，并替换所有其他数据视图和共享量度和维度管理器中该组件的任何现有描述。

* 描述基于生成它的数据视图中的上下文（例如数据视图的顶级维度项）。


