---
title: 导入呼叫中心数据和网站数据
description: 了解如何创建数据集以关联呼叫中心数据和网站数据。
exl-id: 48546227-029c-4cf9-9b7e-66d547769270
solution: Customer Journey Analytics
feature: Use Cases
source-git-commit: fd5d7ae51b51e6f608428a032319a4d7d1f45a97
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 100%

---

# 导入呼叫中心数据和网站数据

Customer Journey Analytics 提供了一项非常有用的强大功能，就是将不同来源的数据合并到一个工作区项目中。使用本指南了解您的组织如何能够结合使用网站数据与呼叫中心数据。例如，可了解客户在联系客户支持之前执行了什么操作、查看了什么内容以及搜索了什么词语。然后可确定要改进的内容和自助服务工具，以使客户可更方便自行解决问题而无需致电。

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

CJA 需要使用通用标识符来生成[合并的数据集](/help/connections/combined-dataset.md)。

* 如果这两个数据集都已经有适用于其所含的每个事件的通用标识符，则可以跳过此步骤并继续创建连接。
* 如果其中任一一个数据集具有仅对某些事件通用的标识符，则可以使用跨渠道分析拼合数据。有关为这两个数据集启用 CCA 的步骤，请参阅[跨渠道分析概述](/help/cca/overview.md)。

## 在 CJA 中创建连接

在 CJA 中[创建连接](/help/connections/create-connection.md)。

* 如果使用 CCA，则会有新的拼合数据集可供您使用。使用新创建的拼合 ID 字段作为人员 ID。
* 否则，可以选择在连接中使用的原始网站数据集和呼叫中心数据集。

## 创建数据视图

创建连接后，可以[创建数据视图](/help/data-views/create-dataview.md)，以供在 Analysis Workspace 使用。有用的组件包括：

* 一个页面维度，它具有最终点击和会话持久性。可将呼叫中心指标与客户在致电之前查看的最后一页联系在一起。
* 一个呼叫指标，它使用“呼叫中心原因”架构字段增加发生次数。请使用[指标去重](/help/data-views/component-settings/metric-deduplication.md)，以使其每个会话仅增加一次。

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
1. 将该指标替换为您要衡量的呼叫中心指标。
1. 单击该量度标题附近的齿轮图标。单击&#x200B;**[!UICONTROL 使用非默认的归因模型]**。
1. 设置所需的[归因模型](/help/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md)。例如，半衰期为 15 分钟的时间衰减模型和会话的回溯时段。此归因模型将作用归于引起致电您的呼叫中心的页面。

所得的报表展示促使致电您的呼叫中心的前几名的页面。<!-- use case behind what we use these pages for -->

<!-- Complement with donut visualization -->

通过按原因或类别划分致电可进一步增加见解。

1. 在组件列表中的“致电原因”维度下单击右侧的 V 形。此操作显示个别维度值。
2. 将所需的维度值拖至“致电”指标下，这样将按每个相应的致电原因筛选该指标。
3. 对要深入了解的每个致电原因都重复此操作。使用“所有会话”筛选器查看总计。

<!-- screenshot -->

### 流程可视化

对于客户在使用呼叫中心渠道之前正在尝试做什么，可获得深入的见解。此流程可视化帮助您了解客户致电呼叫中心所经历的最常见的历程。通过此见解，可确定对于网站可作出的最有效的改进，以使客户降低致电的可能性。

1. 在左侧单击&#x200B;**[!UICONTROL 可视化]**&#x200B;选项卡，然后将流程可视化拖至工作区画布上。
2. 在左侧单击&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡，并找到“致电原因”维度。
3. 单击此维度旁边的右侧 V 形符号。此操作显示个别维度值。
4. 将所需的致电原因维度项拖至流程可视化的中心位置。
5. 流程可视化自动填充上一个和下一个致电原因。将以前的致电原因替换为网站页面维度。
6. 单击流程可视化右上角的齿轮图标，并将流程容器改为&#x200B;**[!UICONTROL 会话]**。

### 直方图

有多少客户致电一次、致电两次或致电 6 次及以上？其中有些人从未访问过网站。使用直方图可视化可确定有多少人落入每个分段。对于从未访问过网站的人，请参阅我们可怎样鼓励其自助服务。

1. 在左侧单击&#x200B;**[!UICONTROL 可视化]**&#x200B;选项卡，然后将直方图可视化拖至工作区画布上。
2. 在左侧单击&#x200B;**[!UICONTROL 组件]**&#x200B;选项卡，并将致电指标拖至直方图可视化。
3. 在可视化的中心单击&#x200B;**[!UICONTROL 显示高级设置]**，并自定义所需的分段。
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
