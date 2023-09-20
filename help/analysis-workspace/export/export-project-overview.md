---
description: 了解可从Analysis Workspace导出的各种方法。
keywords: Analysis Workspace
title: 导出项目数据概述
feature: Curate and Share
hide: true
hidefromtoc: true
source-git-commit: bcbd7ebb075a0d25b566fa8be164d6817bedf2e5
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# 导出概述

您可以从Analysis Workspace导出Customer Journey Analytics数据。 出于多种原因，您可能希望导出Customer Journey Analytics数据，例如，存储大量历史数据或在第三方工具中分析原始数据。

以下各节介绍了支持的文件类型、可用于导出的各种方法以及每种方法的优势。

## 支持的文件类型

您可以将Customer Journey Analytics数据导出为PDF或CSV文件。

* **PDF：** 提供了一种与利益相关者共享可视化数据的简单方法。 PDF文件包含项目中所有显示（可见）的表格和可视化图表。

* **CSV：** 允许您在电子表格应用程序（如Excel）中查看原始数据。 CSV文件包含纯文本数据。

## 导出方法

从Analysis Workspace导出时，可以使用多种方法。 在选择导出方法时，请考虑要导出的内容以及需要访问导出方法的用户。

| 导出方法 | 优势 |
|---------|----------|
| [下载到您的工作站](/help/analysis-workspace/export/download-send.md) | 如果您想要： <ul><li>将项目下载到您的个人工作站。</li><li>仅临时下载（无法计划）。</li> <li>下载共50,000行。</li> <!--true? Are there 2 different options to download to your workstation?--> <!-- is this emailing it? --> |
| [发送给其他用户](/help/analysis-workspace/export/t-schedule-report.md) | 如果您想要： <ul><li>通过电子邮件将导出的Customer Journey Analytics数据发送给组织中的其他用户。</li><li>可以是临时的，也可以是按计划进行的。</li> <li>总共50,000行。</li> <!--true?--> |
| [发送到云应用程序](/help/analysis-workspace/export/export-cloud.md) | 如果您想要： <ul><li>导出到共享位置，如Google Cloud Platform、Microsoft Azure、Amazon S3、Snowflake或Adobe Experience Platform。</li><li>可以是临时的，也可以是按计划进行的。</li><li>存储大量历史Customer Journey Analytics数据。</br>此类数据可用于检测长期趋势，以获取业务情报，最终做出更好的业务决策。</li><li>导出包含数千行或数百万行的完整表。<!-- What other things? Wiki talks about things that aren't even possible in Data Warehouse. What are they? --> </li> |

{style="table-layout:auto"}

