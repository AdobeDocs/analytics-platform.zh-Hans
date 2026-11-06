---
title: 使用Customer Journey Analytics数据馈送中的Parquet文件
description: 了解Customer Journey Analytics数据馈送为何提供Parquet文件、Parquet与CSV、TSV和JSON的比较以及如何查询或加载文件。
hide: true
feature: Components
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
source-git-commit: bd396cb4909d131ed60c97e7101cf85946555e38
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 0%
---
# 在数据馈送中使用Parquet文件

{{release-limited-testing}}

Customer Journey Analytics数据馈送以Parquet格式交付文件。 大多数现代数据仓库可以直接读取Parquet文件，因此在使用这些文件之前，您通常不需要转换这些文件。

使用以下信息了解为什么数据馈送使用Parquet，Parquet与其他文件格式相比有何差异，以及如何在Data Warehouse中查询或加载Parquet文件。

## 使用Parquet进行数据馈送的优势

由于以下原因，Parquet比CSV、TSV或JSON更适合数据馈送输出：

* **宽馈送**：数据馈送可以有数百列。 Parquet允许查询只读取它需要的列。

* **嵌套字段**： Parquet以本机方式表示嵌套字段，如产品列表。 CSV和TSV只能通过将它们编码为字符串来表示它们。 有关详细信息，请参阅数据馈送中的[子事件组件](/help/components/exports/cja-data-feeds/df-sub-event.md)。

* **大型导出**： Parquet通常可降低存储和传输成本。 它还可避免在加载数据时进行文本解析和类型推测。

## Parquet与CSV、TSV和JSON的比较

CSV、TSV和JSON是常见的基于文本的文件格式：

* **CSV和TSV**：每一行数据都是一行纯文本，其值由逗号(CSV)或制表符(TSV)分隔。 Adobe Analytics数据馈送提供TSV文件。 有关Customer Journey Analytics和Adobe Analytics中的数据馈送之间的其他差异，请参阅[比较Customer Journey Analytics和Adobe Analytics中的数据馈送](/help/components/exports/cja-data-feeds/df-comparison.md)。

* **JSON**：每个记录都存储为具有命名字段的文本，并且可以包含嵌套数组和对象。

下表详细列出了Parquet、CSV、TSV和JSON之间的差异：

| 特征 | Parquet | CSV或TSV | JSON |
| --- | --- | --- | --- |
| **文件大小** | 最小。 压缩内置于文件中，工具仅解压缩查询读取的列。 | 更大。 压缩（如gzip）适用于整个文件，因此工具必须解压缩整个文件才能读取它，并且通常无法并行读取。 | 最大。 字段名称在每个记录中重复。 |
| **查询速度** | 快。 查询只读取它需要的列。 | 慢点。 必须读取并解析整行。 | 慢点。 必须读取并解析整行。 |
| **数据类型** | 已键入。 架构将嵌入到文件中。 | 无类型。 所有值均为文本，加载数据时会推断其类型。 | 打字不严。 |
| **嵌套数据** | 本机支持数组和对象。 | 不支持。 数组和对象必须拼合或编码为字符串。 | 本机支持数组和对象。 |
| **可读性** | 需要诸如数据仓库、DuckDB或Python之类的工具。 | 在文本编辑器或电子表格中打开。 | 在文本编辑器中打开。 |

## 查询或加载Parquet文件

数据馈送文件将以Parquet格式传送到您[创建数据馈送](/help/components/exports/cja-data-feeds/create-feed.md)时选择的云存储位置。

您通常不会下载文件，而是将数据仓库连接到存储位置。 然后可以通过以下任一方式使用Parquet文件：

### 就地查询文件

定义指向云存储中文件的外部表。 当您运行查询时，数据仓库会读取文件。

* **Snowflake**：外部表或针对外部阶段的查询
* **数据库**：Amazon S3、Azure Data Lake Storage (ADLS)或Google Cloud Storage上的外部表
* **BigQuery**： Google云存储上的外部表
* **Amazon Redshift**： Amazon S3上的Redshift频谱

### 将文件加载到托管表中

将文件加载到受管表中是定期工作负载的常见选择。 例如：

* **Snowflake**： `COPY INTO`
* **BigQuery**：加载作业
* **数据库**： `COPY INTO`或自动加载程序

## 将Parquet数据转换为CSV或JSON

如果您的下游流程需要CSV或JSON文件，则大多数数据仓库和工具都可以在加载Parquet数据后将它导出为任一格式。 例如，在Snowflake中，您可以以CSV或JSON格式卸载包含`COPY INTO`的查询结果。
