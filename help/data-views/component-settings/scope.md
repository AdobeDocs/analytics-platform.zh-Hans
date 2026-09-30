---
title: 范围组件设置
description: 配置组件如何设定总人口报告的范围。
solution: Customer Journey Analytics
feature: Data Views
role: Admin
hide: true
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: b3197353-f189-4932-8378-3f3bc40e6071
    internal-label: Data management
subfeature_v2:
  - id: e1471301-a189-438e-8d48-264a8db508a6
    internal-label: Data views
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 19%
---

# 范围组件设置 {#scope-component-settings}

>[!CONTEXTUALHELP]
>id="dataview_component_metric_scope"
>title="范围"
>abstract="确定组件在报告中使用时的范围。 您可以选择基于事件、基于轮廓或基于总计。"

量度组件的范围确定如何在报表中使用组件。

| 范围 | 描述 |
|---|---|
| 基于事件 | 量度组件的范围基于事件。 |
| 基于轮廓 | 量度组件的范围基于配置文件。 在报表中使用组件时，无论应用于面板的日期范围如何，量度都会从配置文件数据中返回群体。 日期过滤器和日期范围比较不会影响此量度的报表。 |
| 基于总计 | 量度组件的范围基于配置文件和事件。 在报表中使用组件时，无论应用于面板的日期范围如何，量度都会从您的配置文件和事件数据返回群体。 日期过滤器和日期范围比较不会影响此量度的报表。 |

