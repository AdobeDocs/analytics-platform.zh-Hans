---
title: 导入呼叫中心数据和网站数据
description: 了解如何创建数据集以关联呼叫中心数据和网站数据。
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
source-git-commit: 269c6e50f26d424df58c0803a4e49eb2fc9d3968
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 56%

---

# 导入呼叫中心数据和网站数据

Customer Journey Analytics 提供了一项非常有用的强大功能，就是将不同来源的数据合并到一个工作区项目中。使用本指南了解您的组织如何将网站数据与呼叫中心数据相结合。例如，您可以了解客户采取了哪些操作、他们查看了哪些内容，以及他们在联系客户支持之前搜索的术语。 然后，您可以确定要改进的内容和自助服务工具，以便客户能够更好地自行解决问题，而无需呼叫。

## 先决条件

* 合并这两个数据集所需的最为重要的组件是每个数据源之间通用的标识符。通用标识符的示例包括客户 ID、经过哈希处理的电子邮件、登录用户名或电话号码。
* 对 Adobe Experience Platform 和 Customer Journey Analytics 的访问权限
* 如果您的数据集包含来自交互式语音应答系统的日志，Adobe 建议先对此类数据进行处理以使其仅包含即时交互，然后再将其导入 Platform。
* 如果您的数据集包含通话日志，则 Adobe 建议包括以下列：
   * 通话开始的日期/时间
   * 来电原因
   * 呼叫中心 ID
   * 呼叫中心代理 ID
   * 通话持续时间
   * 通话结果
   * 通话费用（如果有）
   * 贵组织希望包含的任何其他通话元数据

## 将网站数据和呼叫中心数据导入 Platform

将您的数据导入 Adobe Experience Platform。请参阅 Adobe Experience Platform 文档中的[创建架构](https://experienceleague.adobe.com/docs/experience-platform/xdm/tutorials/create-schema-ui.html?lang=zh-Hans)和[摄取数据](https://experienceleague.adobe.com/docs/experience-platform/ingestion/home.html?lang=zh-Hans)。

将数据导入 Platform 时，遵循以下提示将有助于在所生成的报告增加洞察信息：

* 确保用于将呼叫中心数据和网站数据进行关联的标识符采用相似的格式。
* 在每个数据集中包含数据源。例如，在每个架构中包含 `data_source` 列，并分别将每个事件的值设置为 `"Web"` 或 `"Call center"`。<!--mapper-->

## 拼合人员 ID

CJA 需要使用通用标识符来生成[合并的数据集](../connections/combined-dataset.md)。

* 如果这两个数据集都已经有适用于其所含的每个事件的通用标识符，则可以跳过此步骤并继续创建连接。
* 如果其中任一一个数据集具有仅对某些事件通用的标识符，则可以使用跨渠道分析拼合数据。有关为这两个数据集启用 CCA 的步骤，请参阅[跨渠道分析概述](/help/connections/cca/overview.md)。

## 在 CJA 中创建连接

在 CJA 中[创建连接](/help/connections/create-connection.md)。

* 如果使用 CCA，则会有新的拼合数据集可供您使用。使用新创建的拼合 ID 字段作为人员 ID。
* 否则，可以选择在连接中使用的原始网站数据集和呼叫中心数据集。

## 创建数据视图

创建连接后，可以[创建数据视图](/help/data-views/create-dataview.md)，以供在 Analysis Workspace 使用。有用的组件包括：

* 具有最近联系和会话持久性的页面维度。 您可以将呼叫中心量度与客户在呼叫前查看的最后一页连接起来。
* 使用“呼叫中心原因”架构字段增加发生次数的呼叫量度。 使用[量度重复数据删除](/help/data-views/component-settings/metric-deduplication.md) ，以便每个会话只增加一次。

## 创建可视化图表

可使用以下可视化图表深入探查拼合的数据集。

### 数据集重叠

此可视化图表有助于您了解 CCA 进行数据拼合的效果。

1. 创建两个筛选器。这两个筛选器中使用的变量与上面提到的用于反映每个事件的数据源的变量相同。有关更多信息，请参阅[创建筛选器](/help/components/filters/create-filters.md)。
   * 数据集 ID 代表网站数据的“人员”容器
   * 数据集 ID 代表呼叫中心数据的“人员”容器
2. 在 Analysis Workspace 中，将[维恩图](/help/analysis-workspace/visualizations/venn.md)可视化图表拖到工作区画布上。
3. 将两个新创建的筛选器拖到&#x200B;**[!UICONTROL 添加筛选器]**&#x200B;区域，将“人员”量度拖到&#x200B;**[!UICONTROL 添加量度]**&#x200B;区域。

生成的维恩图可视化图表将显示数据集中同时包含网站数据和呼叫中心数据的人员数。重叠区域越大，表示成功拼合的人员越多。不重叠的区域则表示仅存在于其中一个数据集而不存在于另外一个数据集的人员。

### 将呼叫中心事件归因于网页

此自由格式表允许您查看对呼叫中心事件贡献最大的网页。首先，确保所需的维度和量度具有正确的归因模型：

1. 将包含网页名称的维度拖到一个自由格式表可视化图表上。
1. 将量度替换为您要测量的所需呼叫中心量度。
1. 单击该量度标题附近的齿轮图标。单击&#x200B;**[!UICONTROL 使用非默认的归因模型]**。
1. 设置所需的[归因模型](/help/analysis-workspace/attribution/models.md)。例如，半衰期为15分钟的时间衰减模型和会话的回顾窗口。 此归因模型会将点数分配给呼叫中心之前的页面。

生成的报表显示导致呼叫中心呼叫的热门页面。<!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

您可以通过按原因或类别拆分调用来进一步增加对此表的洞察。

1. 单击组件列表中“调用原因”维度下的右V形标记。 此操作会显示单个维度值。
2. 在“调用”量度下拖动所需的维度值，该量度会根据每个调用原因过滤该量度。
3. 请重复执行您要深入查看的每个调用原因。 使用“所有会话”过滤器查看聚合总计。

<!-- screenshot -->

### 流量可视化图表

您可以在客户使用呼叫中心渠道之前，先深入了解客户尝试执行的操作。 此流量可视化图表可帮助您了解客户访问您的呼叫中心的最频繁旅程。 通过此洞察，您可以确定对网站做出的最有效改进，以便客户不太可能在中调用。

1. 单击左侧的&#x200B;**[!UICONTROL 可视化图表]**&#x200B;选项卡，然后将流量可视化图表拖到工作区画布上。
2. 单击左侧的&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡，然后找到“调用原因”维度。
3. 单击此维度旁边的右V形标记。 此操作会显示单个维度值。
4. 将所需的呼叫原因维度项目拖动到流量可视化的中心位置。
5. 流量可视化图表会自动填充先前和后续调用原因。 将之前的调用原因替换为网站页面维度。
6. 单击流量可视化图表右上角的齿轮图标，然后将流量容器更改为&#x200B;**[!UICONTROL Session]**。

### 直方图

有多少客户曾经打过一次电话、打过两次电话或打过6次以上电话？ 其中有些人从不访问网站。 使用直方图可视化图表来确定每个存储段中有多少人。 对于从未访问过该网站的用户，请看我们如何鼓励他们自助。

1. 单击左侧的&#x200B;**[!UICONTROL 可视化图表]**&#x200B;选项卡，然后将直方图可视化图表拖到工作区画布上。
2. 单击左侧的&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡，然后将调用量度拖到直方图可视化中。
3. 单击可视化中心的&#x200B;**[!UICONTROL 显示高级设置]**&#x200B;并自定义所需的存储段。
4. 单击&#x200B;**[!UICONTROL 生成]**。

<!--
### Web to call, call to web

### Fallout

Fallout sessions - session

All sessions > page views metric > calls metric

All sessions > calls metric > page views

Orrr we could also use dataset ID

step 1: all sessions
step 2: 


### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential filters, but you lose the ability to use attribution IQ

## What to do when you've found insight -->
