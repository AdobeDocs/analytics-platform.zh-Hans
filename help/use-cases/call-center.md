---
title: 导入呼叫中心数据和网站数据
description: 了解如何创建数据集以关联呼叫中心数据和网站数据。
translation-type: ht
source-git-commit: dca995fc271b02a26568ed8d4a672b96f10b0a18
workflow-type: ht
source-wordcount: '679'
ht-degree: 100%

---


# 导入呼叫中心数据和网站数据

Customer Journey Analytics 提供了一项非常有用的强大功能，就是将不同来源的数据合并到一个工作区项目中。使用本指南了解您的组织如何将网站数据与呼叫中心数据相结合。

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

将您的数据导入 Adobe Experience Platform。请参阅 Adobe Experience Platform 文档中的[创建架构](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/tutorials/create-schema-ui.html)和[摄取数据](https://docs.adobe.com/content/help/zh-Hans/experience-platform/ingestion/home.html)。

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

创建连接后，可以[创建数据视图](/help/data-views/create-dataview.md)，以供在 Analysis Workspace 使用。<!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## 创建可视化图表

可使用以下可视化图表深入探查拼合的数据集。

### 数据集重叠

此可视化图表有助于您了解 CCA 进行数据拼合的效果。

1. 创建两个过滤器。这两个过滤器中使用的变量与上面提到的用于反映每个事件的数据源的变量相同。有关更多信息，请参阅[创建过滤器](/help/components/filters/create-filters.md)。
   * 数据集 ID 代表网站数据的“人员”容器
   * 数据集 ID 代表呼叫中心数据的“人员”容器
2. 在 Analysis Workspace 中，将[维恩图](/help/analysis-workspace/visualizations/venn.md)可视化图表拖到工作区画布上。
3. 将两个新创建的过滤器拖到&#x200B;**[!UICONTROL 添加筛选器]**&#x200B;区域，将“人员”量度拖到&#x200B;**[!UICONTROL 添加量度]**&#x200B;区域。

生成的维恩图可视化图表将显示数据集中同时包含网站数据和呼叫中心数据的人员数。重叠区域越大，表示成功拼合的人员越多。不重叠的区域则表示仅存在于其中一个数据集而不存在于另外一个数据集的人员。

### 将呼叫中心事件归因于网页

此自由格式表允许您查看对呼叫中心事件贡献最大的网页。首先，确保所需的维度和量度具有正确的归因模型：

1. 将包含网页名称的维度拖到一个自由格式表可视化图表上。
1. 将量度替换为要衡量转化情况的所需呼叫中心量度。
1. 单击该量度标题附近的齿轮图标。单击&#x200B;**[!UICONTROL 使用非默认的归因模型]**。
1. 设置所需的[归因模型](/help/data-views/configure-dataviews.md#Attribution-model)。

生成的报告将显示呼叫中心数据中排名最靠前的量度。<!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: 

Orrr we could also use dataset ID

### Site sections that result in a call within 30 minutes

Slide 4

Create a bunch of filters - facets to their business. Filters were used because they didn't have all of these in the same dimension, so they could create everything in this report as a single dimension (really filters)

wanted to understand when someone interacts with a facet, whats the highest percentage of people that abandon that channel to call them. not from volume perspective, but percentage perspective.

use sequential segmentation, but you lose the ability to use attribution IQ

## What to do when you've found insight -->

