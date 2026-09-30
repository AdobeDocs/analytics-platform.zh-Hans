---
title: Customer Journey Analytics报表API
description: 介绍如何使用报表API以编程方式检索Customer Journey Analytics数据。
solution: Customer Journey Analytics
feature: Use Cases
role: Admin
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: bf2b169f-d8b2-488a-97b9-f3bc9532e35c
    internal-label: Use cases
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: ff8dd2ce69882beaf23249929b0a3803dbec3550
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 5%
---

# 报表API

本文概述如何使用[!DNL Customer Journey Analytics Reporting API]实现以下[数据导出用例](overview.md)：

- 自定义应用程序集成

## 简介

[!DNL Customer Journey Analytics Reporting API]允许您以编程方式检索Analysis Workspace中可用的相同已处理维度和量度。 使用[!DNL Reporting API]可支持自定义应用程序、在内部工具中嵌入报表，或无需手动导出即可自动检索Customer Journey Analytics数据。

## 更多信息

[!DNL Reporting API]使用与[!DNL Adobe Analytics] [!DNL Reporting API]相同的请求和响应格式，但使用不同的端点。 如果您是从[!DNL Adobe Analytics]迁移报表集成，请参阅[快速入门指南](/help/getting-started/cja-getting-started.md)中的迁移工作流以了解更多信息。

有关身份验证、可用端点和当前请求限制，请参阅[Customer Journey Analytics API文档](https://developer.adobe.com/cja-apis/docs/)。
