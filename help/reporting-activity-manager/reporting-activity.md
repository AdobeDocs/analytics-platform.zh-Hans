---
title: 在报告活动管理器中查看报告活动
description: 了解如何使用报告活动管理器诊断和修复在报告高峰期出现的容量问题。
solution: Customer Journey Analytics
feature: Basics
exl-id: 1f5b2a42-162e-45a7-9fd4-8c1557f48bb8
source-git-commit: c343a729de4cb13473a7acc04e837b5e5f69809b
workflow-type: tm+mt
source-wordcount: '1944'
ht-degree: 11%

---

# 在报告活动管理器中查看报告活动

此 [!UICONTROL 报告活动管理器] 使管理员能够在报告高峰期快速诊断和修复报告容量问题。

有关报表活动管理器的更多信息，包括主要优势和权限要求，请参阅 [报表活动管理器概述](/help/reporting-activity-manager/reporting-activity-overview.md).

## 查看所有连接的报告活动 {#view-all-report-suites}

1. 在Customer Journey Analytics中，转到 **[!UICONTROL 工具]** > **[!UICONTROL 报告活动管理器]**.

   此时将显示已启用的基本连接的列表。

   ![显示报表队列的报表活动](assets/reporting-activity1.png)

1. （可选）您可以搜索或筛选连接列表：

   * 使用搜索字段搜索特定连接。 开始键入连接名称或ID，并在键入内容时键入连接更新列表。

   * 选择 [!UICONTROL **筛选**] 图标 ![过滤器图标](assets/filter-icon.png) 以展开筛选器选项列表。 您可以按以下项过滤 [!UICONTROL **收藏夹**] 或 [!UICONTROL **状态**].

     要将连接标记为收藏，请选择连接名称左侧的星形图标。

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. 查看有关每个连接的利用率信息。 表中显示的数据表示上次加载页面时连接的报告活动。

   以下列可供使用：

   | UI 元素 | 描述 |
   | --- | --- |
   | **[!UICONTROL 连接]** | 您正在监控其报告活动的连接。 |
   | **[!UICONTROL 数据视图]** | 显示使用该连接的所有数据视图。 数据视图配置可能会增加报告请求的复杂性。 |
   | **[!UICONTROL 产能利用率]** | 实时使用的连接报告容量的百分比。 <p>**注意** 使用容量为100%并不一定表示您应立即开始取消报告请求。 如果平均等待时间合理，则100%的使用容量可能是健康的。 另一方面，如果排队的请求数量也在增加，则100%的使用容量可能会出现问题。</p> |
   | **[!UICONTROL 已排队的请求]** | 等待处理的请求数。 <!-- ??? --> |
   | **[!UICONTROL 队列等待时间]** | 开始处理请求前的平均等待时间。 <!-- ???? --> |
   | **[!UICONTROL 状态]** | 可能的状态包括： <ul><li>[!UICONTROL **活动**] （蓝色）：过去2小时内已在该连接上运行报告。 表中显示的数据表示上次加载页面时连接的报告容量。</li><li>[!UICONTROL **不活动**] （灰色）：过去2小时内未对连接运行任何报告，因此未显示连接的数据。</li></ul> |

   {style="table-layout:auto"}

## 查看单个连接的报告活动

1. 在Customer Journey Analytics中，选择 [!UICONTROL **工具**] > [!UICONTROL **报告活动管理器**].

1. 选择要查看其详细信息的连接的链接标题。

   将显示您选择的连接的报表活动数据。

1. （可选）当连接首次在报表活动管理器中加载时，显示的数据表示当前的利用率量度。 要在初始加载后查看更新的量度，请选择 [!UICONTROL **刷新**] 按钮以手动刷新页面。

   <!-- Need to update this screenshot: ![connection](assets/indiv-report-ste.png) -->

1. 使用可用的图形和表了解连接中的报告活动。

   * [查看图形](#view-graphs)

   * [查看表](#view-table)

### 查看图形

以下图表可帮助您更好地了解连接中发生的活动。

如果图形不可见，请选择 [!UICONTROL **显示图形**] 按钮。

#### 利用率图表 {#utilization}

利用率图表显示选定连接在过去2小时内的报告利用率。

将鼠标悬停在图表上可查看该分钟使用容量百分比最高的时间点。

* **X轴**：过去2小时内的报表使用容量。
* **Y轴**：报表使用容量百分比，按分钟。

  ![利用率图](assets/utilization-graph.png)

#### 不同用户图

“不同用户”图显示选定连接在过去2小时内的报告活动。

将鼠标悬停在图表上可查看该分钟最大用户数最高的时间点。

* **X轴**：过去2小时内的报表活动。
* **Y轴**：按分钟列出已提出报表请求的用户数。

  ![不同用户图](assets/distinct-users-graph.png)

#### 请求图表

“请求”图表显示过去2小时内所选连接的已处理和已排队请求数。

将鼠标悬停在图表上可查看该分钟最大请求数最高的时间点。

* **X轴**：过去2小时时间范围内已处理和已排队请求的数目。
* **Y轴**：按分钟计算的已处理请求（绿色）和已排队请求（紫色）的数量。

  ![不同用户图](assets/requests-graph.png)

#### 排队图

排队图显示过去2小时内报告所选连接请求的平均队列等待时间（以秒为单位）。

将鼠标悬停在图表上可查看该分钟的最大平均等待时间最高的时间点。

* **X轴**：过去2小时时间范围内报告请求的平均队列等待时间。
* **Y轴**：平均等待时间（秒）。

  ![不同用户图](assets/queueing-graph.png)

### 查看表 {#view-table}

查看表时，请考虑以下事项：

* 通过选择数据表顶部的以下任一选项卡，可以选择查看数据： [!UICONTROL **请求**]， [!UICONTROL **用户**]， [!UICONTROL **项目**]，或 [!UICONTROL **应用程序**].

* 您可以搜索或筛选连接列表：

   * 使用搜索字段搜索特定连接。 开始键入连接名称或ID，并在键入内容时键入连接更新列表。

   * 选择 [!UICONTROL **筛选**] 图标 ![过滤器图标](assets/filter-icon.png) 以展开筛选器选项列表。 您可以按以下项过滤 [!UICONTROL **状态**]， [!UICONTROL **复杂性**]， [!UICONTROL **应用程序**]， [!UICONTROL **用户**]，或 [!UICONTROL **项目**].

   * 您可以选择 [!UICONTROL **隐藏图形**] 以仅显示表。

![表格选项卡](assets/report-activity-tabs.png)

#### 按请求查看数据

当您选择 [!UICONTROL **请求**] 选项卡上，表中提供了以下列：

| 栏目 | 描述 |
| --- | --- |
| [!UICONTROL **请求编号**] | 可用于故障排除的唯一ID。 要复制ID，请选择请求，然后选择选项 [!UICONTROL **复制请求Id**]. |
| [!UICONTROL **已用时间**] | 请求已运行多长时间。 |
| [!UICONTROL **开始时间**] | 请求开始处理的时间（基于管理员的本地时间）。 |
| [!UICONTROL **等待时间**] | 请求在处理之前等待了多长时间。 当有足够的容量时，该值通常为“0”。 |
| [!UICONTROL **应用程序**] | [!UICONTROL 报告活动管理器]支持的应用程序包括： <ul><li>Analysis Workspace UI</li><li>工作区计划项目</li><li>Report Builder</li><li>生成器UI：区段、计算量度、注释、受众等。</li><li>来自2.0 API的API调用</li><li>智能警报<li>完整表导出</li><li>与任何人共享链接</li><li>引导式分析</li><li>查询Analytics报表引擎的任何其他应用程序</li></li></ul><p>**注意：** 如果此列的值为 [!UICONTROL **未知**]，这意味着请求元数据对用户不可用。</p> |
| [!UICONTROL **用户**] | 发起请求的用户。 <p>**注意：** 如果此列的值为 [!UICONTROL **未知**]，这意味着请求元数据对用户不可用。</p> |
| [!UICONTROL **项目**] | 保存的工作区项目名称、API报表ID等。 （元数据可能因各种应用程序而异。）<p>**注意：** 如果此列的值为 [!UICONTROL **未知**]，这意味着项目尚未保存或请求元数据对用户不可用。</p> |
| [!UICONTROL **状态**] | 状态指示器： <ul><li>**运行中**：请求当前正在处理中。</li><li>**等待中**：请求正在等待处理。</li></ul> |
| [!UICONTROL **复杂度**] | 并非所有请求都需要相同的处理时间。 请求复杂性有助于提供有关处理请求所需时间的一般概念。 <p>可能的值包括：</p> <ul><li>[!UICONTROL **低**]</li><li>[!UICONTROL **媒介**]</li><li>[!UICONTROL **高**]</li></ul>此值受以下列中的值影响：<ul><li>[!UICONTROL **月份边界**]</li><li>[!UICONTROL **列**]</li><li>[!UICONTROL **区段**]</li></ul> |
| [!UICONTROL **月份边界**] | 请求中包含的月数。 更多的月份边界会增加请求的复杂性。 |
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
| [!UICONTROL **应用程序**] | [!UICONTROL 报告活动管理器]支持的应用程序包括： <ul><li>Analysis Workspace UI</li><li>工作区计划项目</li><li>Report Builder</li><li>生成器UI：区段、计算量度、注释、受众等。</li><li>来自2.0 API的API调用</li><li>智能警报<li>完整表导出</li><li>与任何人共享链接</li><li>引导式分析</li><li>查询Analytics报表引擎的任何其他应用程序</li></li></ul> |
| [!UICONTROL **平均复杂度**] | 用户发起的请求的平均复杂性。 <p>并非所有请求都需要相同的处理时间。 请求复杂性有助于提供有关处理请求所需时间的一般概念。</p><p>此列中的值基于由以下列中的值决定的分数：</p><ul><li>[!UICONTROL **平均月份边界**]</li><li>[!UICONTROL **平均列数**]</li><li>[!UICONTROL **平均区段数**]</li></ul> |
| [!UICONTROL **平均月份边界**] | 请求中包含的平均月数。 更多的月份边界会增加请求的复杂性。 |
| [!UICONTROL **平均列数**] | 包含的请求中的平均量度和细分数。 更多的列会增加请求的复杂性。 |
| [!UICONTROL **平均区段数**] | 应用于所包含请求的平均区段数。 更多区段会增加请求的复杂性。 |

{style="table-layout:auto"}

#### 按项目查看数据

当您选择 [!UICONTROL **项目**] 选项卡上，表中提供了以下列：

| 栏目 | 描述 |
| --- | --- |
| [!UICONTROL **项目**] | 发起请求的项目。 |
| [!UICONTROL **请求数量**] | 与项目关联的请求数。 |
| [!UICONTROL **用户数量**] | 与项目关联的用户数。 <!-- ??? --> |
| [!UICONTROL **应用程序**] | [!UICONTROL 报告活动管理器]支持的应用程序包括： <ul><li>Analysis Workspace UI</li><li>工作区计划项目</li><li>Report Builder</li><li>生成器UI：区段、计算量度、注释、受众等。</li><li>来自2.0 API的API调用</li><li>智能警报<li>完整表导出</li><li>与任何人共享链接</li><li>引导式分析</li><li>查询Analytics报表引擎的任何其他应用程序</li></li></ul> |
| [!UICONTROL **平均复杂度**] | 项目中包含的请求的平均复杂性。 <p>并非所有请求都需要相同的处理时间。 请求复杂性有助于提供有关处理请求所需时间的一般概念。</p><p>此列中的值基于由以下列中的值决定的分数：</p><ul><li>[!UICONTROL **平均月份边界**]</li><li>[!UICONTROL **平均列数**]</li><li>[!UICONTROL **平均区段数**]</li></ul> |
| [!UICONTROL **平均月份边界**] | 请求中包含的平均月数。 更多的月份边界会增加请求的复杂性。 |
| [!UICONTROL **平均列数**] | 包含的请求中的平均量度和细分数。 更多的列会增加请求的复杂性。 |
| [!UICONTROL **平均区段数**] | 应用于所包含请求的平均区段数。 更多区段会增加请求的复杂性。 |

{style="table-layout:auto"}

#### 按应用程序查看数据

当您选择 [!UICONTROL **应用程序**] 选项卡上，表中提供了以下列：

| 栏目 | 描述 |
| --- | --- |
| [!UICONTROL **应用程序**] | 发起请求的应用程序。 |
| [!UICONTROL **请求数量**] | 与应用程序关联的请求数。 |
| [!UICONTROL **用户数量**] | 与应用程序关联的用户数。 <!--???--> |
| [!UICONTROL **项目数量**] | 与应用程序关联的项目数。 <!--???--> |
| [!UICONTROL **平均复杂度**] | 与应用程序关联的请求的平均复杂性。 <p>并非所有请求都需要相同的处理时间。 请求复杂性有助于提供有关处理请求所需时间的一般概念。</p><p>此列中的值基于由以下列中的值决定的分数：</p>此列中的值基于由以下列中的值决定的分数：<ul><li>[!UICONTROL **平均月份边界**]</li><li>[!UICONTROL **平均列数**]</li><li>[!UICONTROL **平均区段数**]</li></ul> |
| [!UICONTROL **平均月份边界**] | 请求中包含的平均月数。 更多的月份边界会增加请求的复杂性。 |
| [!UICONTROL **平均列数**] | 包含的请求中的平均量度和细分数。 更多的列会增加请求的复杂性。 |
| [!UICONTROL **平均区段数**] | 应用于所包含请求的平均区段数。 更多区段会增加请求的复杂性。 |

{style="table-layout:auto"}

<!-- 

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
| | |

{style="table-layout:auto"}

-->
