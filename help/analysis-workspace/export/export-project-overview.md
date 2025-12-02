---
description: 了解从 Analysis Workspace 导出数据的可用方法。
keywords: Analysis Workspace
title: 如何导出项目数据
feature: Curate and Share
exl-id: 3d467050-4bf0-4bdb-b7d2-eba67fbd526d
role: User
source-git-commit: a133f60e66b34a851d2e8e1c0a853cdbc1f8d51f
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 100%

---

# 导出概述

您可以从 Analysis Workspace 导出（部分）Customer Journey Analytics 项目。您可能出于多种原因想要导出 Customer Journey Analytics 报告，例如在第三方工具中使用或与外部数据结合使用。

以下部分介绍了受支持的文件类型、可用于导出的各种方法以及每种方法的优点。

## 支持的文件类型

您可以将 Customer Journey Analytics 报告导出为 PDF、CSV 或 JSON 文件。

* **PDF：**&#x200B;提供一种与利益相关者共享视觉数据的简便方法。PDF 文件包含项目中所有显示（可见）的表格和可视化图表。

* **CSV：**&#x200B;允许您在电子表格应用程序中查看原始数据，例如 Excel。CSV 文件包含纯文本数据。

* **JSON：**&#x200B;提供用于共享数据的开放标准文件格式。

## 导出方法

从 Analysis Workspace 导出内容时，您可以选择多种方法。选择导出方法时，请考虑您要导出什么以及谁需要访问它。

| 导出方法 | 如果您想要执行以下操作，请使用此方法： |
|---------|----------|
| [下载至您的工作站](/help/analysis-workspace/export/download-send.md) | <li>将项目下载到您的个人工作站。</li><li>仅下载临时数据（不包含预定数据）。</li> <li>下载最多 50,000 行数据。</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [发送给其他用户](/help/analysis-workspace/export/t-schedule-report.md) | <li>通过电子邮件将导出的 Customer Journey Analytics 数据发送给您组织中的其他用户。</li><li>按需或按预定计划发送电子邮件。</li> <li>电子邮件中最多可包含 50,000 行数据。</li> <!--true?--> |
| [导出至云位置](/help/analysis-workspace/export/export-cloud.md) | <li>导出至云位置，例如： <ul><li>Adobe Experience Platform 数据登陆区</li><li>Google Cloud Platform</li><li>Microsoft Azure</li><li>Amazon S3</li><li>Snowflake</li></ul></li><li>按需或按预定计划导出数据。</li><li>存储更多 Customer Journey Analytics 数据。</li><li>导出包含数千或数百万行的完整表格。<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}
