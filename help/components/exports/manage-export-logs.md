---
description: 管理现有导出的日志
keywords: Analysis Workspace
title: 管理导出日志
feature: Components
exl-id: 6d676a0a-b117-421e-9a90-8c550f08d474
source-git-commit: 34588ccd39d7464387197a0b4bfd6a9e416bd9c0
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 6%

---

# 管理导出日志

{{release-limited-testing}}

导出日志提供有关每次导出的详细信息，并在每次将Analysis Workspace数据导出到云时生成。 (有关如何将数据导出到云的信息，请参阅 [将Customer Journey Analytics报表导出到云端](/help/analysis-workspace/export/export-cloud.md).)

对于计划的导出，日志反映发送日志时的导出设置。 无法删除日志。

## 过滤和搜索日志

要查找所需的信息，可以筛选日志列表或搜索日志。

### 筛选日志列表

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **日志**] 选项卡。

1. 选择 **筛选** 图标。

   ![筛选器信息](assets/export-log-filters.png)

   您可以按以下条件进行筛选：

   | 过滤器 | 描述 |
   |---------|----------|
   | [!UICONTROL **帐户类型**] | 与日志关联的帐户类型。 可以使用以下帐户类型： <ul><li>[!UICONTROL **Adobe Experience Platform数据登陆区**]</li><li>[!UICONTROL **Amazon S3 Role ARN**]</li><li>[!UICONTROL **Google Cloud Platform**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Snowflake**]</li></ul>。 |
   | [!UICONTROL **状态**] | 导出的状态。 可以使用以下状态： <ul><li>[!UICONTROL **待处理**]：导出的特定实例已启动，但尚未完成。<p>重新运行状态为“待定”的导出将会延迟导出过程。</p></li><li>[!UICONTROL **已完成**]：导出的特定实例已完成处理，可在导出帐户中使用。</li><li>[!UICONTROL **失败**]<p>以下情况可能会导致导出失败。 将鼠标悬停在失败状态上可查看有关失败的详细信息。 <ul><li>计划的导出过期</li><li>已达到计划导出的行限制 </li></ul> </p></li></ul> |

   {style="table-layout:auto"}

### 搜索日志

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **日志**] 选项卡。

1. 在搜索选项卡中，开始键入与要搜索的日志相关联的任何信息。 您可以从表中任何可用的列搜索数据。

<!-- removed for MVP: Retry an export You can re-run the export associated with the selected log, using the data as it was on the day the log was originally exported. This is useful when selecting a log that show a failed export or when selecting a log that was accidentally deleted. 

Retrying an export that has a status of Pending will delay the export process.

This option is not available when selecting multiple logs. -->

<!-- 1. In Customer Journey Analytics, select [!UICONTROL **Components**] > [!UICONTROL **Exports**].

1. Select the [!UICONTROL **Logs**] tab, then select a log.

1. Select [!UICONTROL **Retry**]. -->

## 编辑导出

您可以编辑与特定日志关联的导出。

选择多个日志时，此选项不可用。

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **日志**] 选项卡。

1. 找到与要编辑的导出关联的日志。

1. 选择 **编辑导出** 图标 ![导出日志图标](assets/export-icon.png) 日志旁边的。

   或

   选择日志，然后选择 [!UICONTROL **编辑导出**].

## 配置列

您可以在 [!UICONTROL 日志] 选项卡以配置要显示的信息。

选择列标题以按该列对日志进行排序。 默认情况下，日志按开始导出的日期和时间排序。

要配置上的列，请执行以下操作 [!UICONTROL 日志] 选项卡：

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **日志**] 选项卡。

1. 选择 **自定义表** 图标 ![自定义表](assets/customize-table-icon.png) 右上角的 [!UICONTROL 日志] 页面。

   以下列可供使用：

   | 可用列 | 描述 |
   |---------|----------|
   | 导出名称 | 导出的名称。 用户在创建导出时为其命名，如中所述 [将Customer Journey Analytics报表导出到云端](/help/analysis-workspace/export/export-cloud.md). |
   | 导出 ID | 创建导出时自动为其分配的ID。 <!-- True? --> |
   | 实例 ID | Customer Journey Analytics实例的ID。 <!-- True? --> |
   | 数据视图名称 | 与导出关联的数据视图的名称。 用户可以在创建导出时选择数据视图，如中所述 [将Customer Journey Analytics报表导出到云端](/help/analysis-workspace/export/export-cloud.md). |
   | 文件数 | 导出中包含的文件数。 |
   | 大小 | 导出的大小。<p>文件大小以1024为基数计算，有时表示为KIB和MIB。 如果您的云提供商计算的大小基数为1000，这可能会导致您的云提供商中显示的大小与此处显示的大小略有不同。</p> |
   | 位置 | 帐户上导出数据的位置。 |
   | 帐户 | 从中导出数据的帐户。 |
   | 状态 | 导出的状态。 可用状态包括 [!UICONTROL 待处理]， [!UICONTROL 已投放]、和 [!UICONTROL 失败]. |
   | 投放日期 | 导出日期。 |
   | 帐户类型 | 从中导出数据的云帐户的类型。 可用的帐户类型包括 [!UICONTROL Amazon S3角色ARN]， [!UICONTROL Google Cloud平台]， [!UICONTROL Azure SAS]， [!UICONTROL Azure RBAC]， [!UICONTROL Snowflake]、和 [!UICONTROL Adobe Experience Platform]. |
   | 行数 | 导出表中包括的行数。 |

   {style="table-layout:auto"}

1. 确保选定您要显示的任何列。 选定的列显示在 [!UICONTROL 日志] 页面并显示相关信息。

## 查看审核日志

全表导出也会在 [Customer Journey Analytics审核日志](/help/privacy/audit-log.md). <!-- Need to see what the Component Type for full-table export will be and add it here. Also, under "Event type captured by audit logs" there would be a new event type called "Full-table export". 4 actions would be "Create, Delete, Edit, Export" and "API_Request"? Also information about the locations. Probably have a different component for the location credentials.-->
