---
title: 指标去重组件设置
description: 仅计入指标在报表中第一次出现的情况。
exl-id: ced0c637-5cbe-47a4-897a-eb79961986a3
solution: Customer Journey Analytics
source-git-commit: faaf3d19ed37019ba284b41420628750cdb413b8
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 100%

---

# 指标去重组件设置

通过指标去重，可将指标配置为仅以非重复的方式计入值。

| 设置 | 描述 |
| --- | --- |
| 指标去重 | 一个复选框，通过它，可启用指标去重。默认禁用。 |
| 去重范围 | 使您可决定唯一检查回溯多远。<br>**会话**：仅计入会话第一次出现该指标的情况。<br>**人员**：仅计入报表时段中第一次出现该指标的情况。 |
| 去重 ID | 并非对指标本身应用去重，而是使您可根据维度应用指标去重。对于“购买 ID”等维度应用去重很有用。 |
