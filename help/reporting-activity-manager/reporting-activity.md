---
title: 在报告活动管理器中查看报告活动
description: 了解如何使用报告活动管理器诊断和修复在报告高峰期出现的容量问题。
solution: Customer Journey Analytics
feature: Basics
source-git-commit: dba42bedd14c4c6d958feab9a1ebdc137d489f32
workflow-type: tm+mt
source-wordcount: '1756'
ht-degree: 17%

---

# 在报告活动管理器中查看报告活动

{{release-limited-testing}}

此 [!UICONTROL 报告活动管理器] 使管理员能够在报告高峰期快速诊断和修复报告容量问题。

有关报表活动管理器的更多信息，包括主要优势和权限要求，请参阅 [报表活动管理器概述](/help/reporting-activity-manager/reporting-activity-overview.md).

## 查看所有连接的报告活动 {#view-all-report-suites}

1. 在Customer Journey Analytics中，转到 **[!UICONTROL 工具]** > **[!UICONTROL 报告活动管理器]**.

   此时将显示已启用的基本连接的列表。

   ![报告队列](assets/reporting-activity1.png)

1. （可选）您可以搜索或筛选连接列表：

   * 使用搜索字段搜索特定连接。 开始键入连接名称或ID，并在键入内容时键入连接更新列表。

   * 选择 [!UICONTROL **筛选**] 图标 ![过滤器图标](assets/filter-icon.png) 以展开筛选器选项列表。 您可以按以下项过滤 [!UICONTROL **收藏夹**] 或 [!UICONTROL **状态**].

     要将连接标记为收藏，请选择连接名称左侧的星形图标。

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. 查看有关每个连接的利用率信息。 您可以选择列标题来按该列对表进行排序。

   以下列可供使用：

   | UI 元素 | 描述 |
   | --- | --- |
   | **[!UICONTROL 连接]** | 您正在监控其报告活动的连接。 |
   | **[!UICONTROL 虚拟报表包]** | 显示馈送入此基础报告包的所有虚拟报告包。由于额外施加多层筛选和分段，因此虚拟报告包提高了报告请求的复杂性。所有来自虚拟报表包的请求将合并到基础报表包中。<p>例如，如果您从5个虚拟报表包收到10个请求，则基础级别报表包中有50个请求。 这样即可很快达到容量。 |
   | **[!UICONTROL 产能利用]** | 实时使用的报表包报告容量的百分比。 <p>**注意** 使用容量为100%并不一定表示您应立即开始取消报告请求。 如果平均等待时间合理，则100%的使用容量可能是健康的。 另一方面，如果排队的请求数量也在增加，则100%的使用容量可能会出现问题。</p> |
   | **[!UICONTROL 已排队的请求]** | 等待处理的请求数。 <!-- ??? --> |
   | **[!UICONTROL 队列等待时间]** | 开始处理请求前的平均等待时间。 <!-- ???? --> |
   | **[!UICONTROL 状态]** | 可能的状态包括： <ul><li>[!UICONTROL **活动**] （蓝色）：已在报表包上运行报告，并且正在监控其活动。</li><li>[!UICONTROL **不活动**] （灰色）：报表包中从未运行任何报表。 此状态仅在首次创建报表包时显示。</li></ul> |

   {style="table-layout:auto"}

## 查看单个报表包的报告活动

1. 在Customer Journey Analytics中，选择 [!UICONTROL **工具**] > [!UICONTROL **报告活动管理器**].

1. 选择要查看其详细信息的报表包的链接标题。

   系统将显示选定报表包的报表活动数据。

   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. 使用可用的图形和表了解报表包中的报表活动。

   * [查看图形](#view-graphs)

   * [查看表](#view-table)

### 查看图形

以下图表可帮助您更好地了解报表包中发生的活动。

如果图形不可见，请选择 [!UICONTROL **显示图形**] 按钮。

#### 利用率图表 {#utilization}

利用率图表显示选定报表包在过去2小时内的报表利用率。

将鼠标悬停在图表上可查看该分钟使用容量百分比最高的时间点。

* **X轴**：过去2小时内的报表使用容量。
* **Y轴**：报表使用容量百分比，按分钟。

  ![利用率图](assets/utilization-graph.png)

#### 不同用户图

独特用户图显示选定报表包在过去2小时内的报表活动。

将鼠标悬停在图表上可查看该分钟最大用户数最高的时间点。

* **X轴**：过去2小时内的报表活动。
* **Y轴**：按分钟列出已提出报表请求的用户数。

  ![不同用户图](assets/distinct-users-graph.png)

#### 请求图表

请求图形可显示过去2小时内选定报表包中已处理和已完成的请求数。

将鼠标悬停在图表上可查看该分钟最大请求数最高的时间点。

* **X轴**：过去2小时时间范围内已处理和已完成的请求数。
* **Y轴**：按分钟计算的已处理请求（紫色）和已完成的请求（绿色）的数量。

  ![不同用户图](assets/requests-graph.png)

#### 排队图

排队图显示所选报表包在过去2小时内报告请求的平均队列等待时间（秒）。

将鼠标悬停在图表上可查看该分钟的最大平均等待时间最高的时间点。

* **X轴**：过去2小时时间范围内报告请求的平均队列等待时间。
* **Y轴**：平均等待时间（秒）。

  ![不同用户图](assets/queueing-graph.png)

### 查看表 {#view-table}

通过选择数据表顶部的以下任一选项卡，可以选择查看数据： [!UICONTROL **请求**]， [!UICONTROL **用户**]， [!UICONTROL **项目**]，或 [!UICONTROL **应用程序**].

>[!TIP]
>
>您可以选择 [!UICONTROL **隐藏图形**] 以仅显示表。

![表格选项卡](assets/indiv-report-ste-table-tabs.png)

#### 按请求查看数据

当您选择 [!UICONTROL **请求**] 选项卡上，表中提供了以下列：

| 栏目 | 描述 |
| --- | --- |
| [!UICONTROL **请求编号**] | 可用于故障排除目的。 |
| [!UICONTROL **已用时间**] | 请求已运行多长时间。 |
| [!UICONTROL **开始时间**] | 请求开始处理的时间（基于管理员的本地时间）。 |
| [!UICONTROL **等待时间**] | 请求在处理之前等待了多长时间。 当有足够的容量时，该值通常为“0”。 |
| [!UICONTROL **应用程序**] | [!UICONTROL 报告活动管理器]支持的应用程序包括： <ul><li>Analysis Workspace UI</li><li>工作区计划项目</li><li>Report Builder</li><li>生成器 UI：区段、计算量度、注释、受众等。</li><li>1.4 或 2.0 API 的 API 调用</li><li>智能警报</li></ul> |
| [!UICONTROL **用户**] | 发起请求的用户。 <p>**注意：** 如果此列的值为 [!UICONTROL **无法识别**]，这意味着用户所在的登录公司您没有管理权限。</p> |
| [!UICONTROL **项目**] | 已保存的 Workspace 项目名称、API 报告 ID 等。（元数据可能因各种应用程序而异。） |
| [!UICONTROL **状态**] | 状态指示器： <ul><li>**运行中**：请求当前正在处理中。</li><li>**等待中**：请求正在等待处理。</li></ul> |
| [!UICONTROL **复杂度**] | 并非所有请求都需要相同的处理时间。 请求复杂性有助于提供有关处理请求所需时间的一般概念。 <p>可能的值包括：</p> <ul><li>[!UICONTROL **低**]</li><li>[!UICONTROL **媒介**]</li><li>[!UICONTROL **高**]</li></ul>此值受以下列中的值影响：<ul><li>[!UICONTROL **月边界**]</li><li>[!UICONTROL **列**]</li><li>[!UICONTROL **区段**]</li></ul> |
| [!UICONTROL **月边界**] | 请求中包含的月数。 更多的月份边界会增加请求的复杂性。 |
| [!UICONTROL **列**] | 请求中的量度和细分的数量。 更多的列会增加请求的复杂性。 |
| [!UICONTROL **区段**] | 应用于请求的区段数。 更多区段会增加请求的复杂性。 |

{style="table-layout:auto"}

#### 按用户查看数据

当您选择 [!UICONTROL **用户**] 选项卡上，表中提供了以下列：

| 栏目 | 描述 |
| --- | --- |
| [!UICONTROL **用户**] | 发起请求的用户。 如果此列的值为 [!UICONTROL **无法识别**]，这意味着用户所在的登录公司您没有管理权限。 |
| [!UICONTROL **请求数量**] | 用户发起的请求数。 |
| [!UICONTROL **项目数量**] | 与用户关联的项目数。 <!-- ??? --> |
| [!UICONTROL **应用程序**] | [!UICONTROL 报告活动管理器]支持的应用程序包括： <ul><li>Analysis Workspace UI</li><li>工作区计划项目</li><li>Report Builder</li><li>生成器 UI：区段、计算量度、注释、受众等。</li><li>1.4 或 2.0 API 的 API 调用</li><li>智能警报</li></ul> |
| [!UICONTROL **平均复杂性**] | 用户发起的请求的平均复杂性。 <p>并非所有请求都需要相同的处理时间。 请求复杂性有助于提供有关处理请求所需时间的一般概念。</p><p>此列中的值基于由以下列中的值决定的分数：</p><ul><li>[!UICONTROL **平均月份边界**]</li><li>[!UICONTROL **平均列数**]</li><li>[!UICONTROL **平均区段数**]</li></ul> |
| [!UICONTROL **平均月份边界**] | 请求中包含的平均月数。 更多的月份边界会增加请求的复杂性。 |
| [!UICONTROL **平均列数**] | 包含的请求中的平均量度和细分数。 更多的列会增加请求的复杂性。 |
| [!UICONTROL **平均区段数**] | 应用于所包含请求的平均区段数。 更多区段会增加请求的复杂性。 |

{style="table-layout:auto"}

#### 按项目查看数据

当您选择 [!UICONTROL **项目**] 选项卡上，表中提供了以下列：

| 栏目 | 描述 |
| --- | --- |
| [!UICONTROL **项目**] | 启动查询的项目。 |
| [!UICONTROL **请求数量**] | 与项目关联的请求数。 |
| [!UICONTROL **用户数量**] | 与项目关联的用户数。 <!-- ??? --> |
| [!UICONTROL **应用程序**] | [!UICONTROL 报告活动管理器]支持的应用程序包括： <ul><li>Analysis Workspace UI</li><li>工作区计划项目</li><li>Report Builder</li><li>生成器 UI：区段、计算量度、注释、受众等。</li><li>1.4 或 2.0 API 的 API 调用</li><li>智能警报</li></ul> |
| [!UICONTROL **平均复杂性**] | 项目中包含的请求的平均复杂性。 <p>并非所有请求都需要相同的处理时间。 请求复杂性有助于提供有关处理请求所需时间的一般概念。</p><p>此列中的值基于由以下列中的值决定的分数：</p><ul><li>[!UICONTROL **平均月份边界**]</li><li>[!UICONTROL **平均列数**]</li><li>[!UICONTROL **平均区段数**]</li></ul> |
| [!UICONTROL **平均月份边界**] | 请求中包含的平均月数。 更多的月份边界会增加请求的复杂性。 |
| [!UICONTROL **平均列数**] | 包含的请求中的平均量度和细分数。 更多的列会增加请求的复杂性。 |
| [!UICONTROL **平均区段数**] | 应用于所包含请求的平均区段数。 更多区段会增加请求的复杂性。 |

{style="table-layout:auto"}

#### 按应用程序查看数据

当您选择 [!UICONTROL **应用程序**] 选项卡上，表中提供了以下列：

| 栏目 | 描述 |
| --- | --- |
| [!UICONTROL **应用程序**] | 发起查询的应用程序。 |
| [!UICONTROL **请求数量**] | 与应用程序关联的请求数。 |
| [!UICONTROL **用户数量**] | 与应用程序关联的用户数。 <!--???--> |
| [!UICONTROL **项目数量**] | 与应用程序关联的项目数。 <!--???--> |
| [!UICONTROL **平均复杂性**] | 与应用程序关联的请求的平均复杂性。 <p>并非所有请求都需要相同的处理时间。 请求复杂性有助于提供有关处理请求所需时间的一般概念。</p><p>此列中的值基于由以下列中的值决定的分数：</p>此列中的值基于由以下列中的值决定的分数：<ul><li>[!UICONTROL **平均月份边界**]</li><li>[!UICONTROL **平均列数**]</li><li>[!UICONTROL **平均区段数**]</li></ul> |
| [!UICONTROL **平均月份边界**] | 请求中包含的平均月数。 更多的月份边界会增加请求的复杂性。 |
| [!UICONTROL **平均列数**] | 包含的请求中的平均量度和细分数。 更多的列会增加请求的复杂性。 |
| [!UICONTROL **平均区段数**] | 应用于所包含请求的平均区段数。 更多区段会增加请求的复杂性。 |

{style="table-layout:auto"}

<!--

### Filter

You can filter the table by Application (see list in the table below), by User, and by Project.

![filter](/help/admin/admin/assets/filter.png)

### Summary Numbers {#summary}

![filter](/help/admin/admin/assets/summary_numbers.png)

The Summary Numbers show the following information:

| Summary Number | Description |
| --- | --- |
| [!UICONTROL **Users**] | The number of users that are currently sending reporting requests to this report suite. |
| [!UICONTROL **Projects**] | Workspace projects, Report Builder workbooks, etc.  | 
| [!UICONTROL **Queries**] | The number of queries currently running. |
| [!UICONTROL **Average Wait Time**] | The average wait time for all running queries.  |
| [!UICONTROL **Usage Capacity**] | The current usage capacity for this report suite. |

{style="table-layout:auto"}

-->
