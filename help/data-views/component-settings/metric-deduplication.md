---
title: 指标去重组件设置
description: 仅计入指标在报表中第一次出现的情况。
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
feature: Data Views
source-git-commit: e2ebda486eae7740351370f48bdf104c90494ae3
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 75%

---

# 指标去重组件设置

通过指标去重，可将指标配置为仅以非重复的方式计入值。

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 指标去重] | 一个复选框，通过它，可启用指标去重。默认禁用。 |
| [!UICONTROL 去重范围] | 使您可决定唯一检查回溯多远。<br>**会话**：仅计入会话第一次出现该指标的情况。<br>**人员**：仅计入报表时段中第一次出现该指标的情况。 |
| [!UICONTROL 去重 ID] | 并非对指标本身应用去重，而是使您可根据维度应用指标去重。对于“购买 ID”等维度应用去重很有用。 |

{style=&quot;table-layout:auto&quot;}

>[!CAUTION]
>
>   在 _人员_ 范围按UTC时间的完整月份评估。 如果部分月份报表窗口在整个月内但在报表日期之外发生，则可能不会显示所有第一个或最后一个实例。
