---
title: 导入呼叫中心和Web数据
description: 了解如何创建链接呼叫中心和网站数据的数据集。
translation-type: tm+mt
source-git-commit: 8d2f70ad47dcf9b97808da3a04d32d3412a1f0c8
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 3%

---


# 导入呼叫中心和Web数据

Customer Journey Analytics提供有价值且强大的功能，可将不同来源的数据集合到单个Workspace项目中。 使用本指南了解组织如何将数据从您的网站整合到来自您呼叫中心的数据。

## 先决条件

* 组合这两组数据的最重要的组件是每个数据源之间的通用标识符。 示例包括客户ID、散列电子邮件、登录用户名或电话号码。
* 访问Adobe Experience Platform和Customer Journey Analytics
* 如果您的数据集包含来自交互式语音响应系统的日志，Adobe建议在将数据导入平台之前仅处理数据以包含提示交互。
* 如果Adobe集包含调用日志，则Adobe建议包括以下列：
   * 呼叫开始的日期／时间
   * 呼叫原因
   * 呼叫中心ID
   * 呼叫中心代理ID
   * 呼叫持续时间
   * 通话结果
   * 通话费（如果可用）
   * 您的组织希望包含的任何其他呼叫元数据

## 将Web和呼叫中心数据导入平台

开始将数据导入Adobe Experience Platform。 请参阅Adobe Experience Platform文档中的[创建模式](https://docs.adobe.com/content/help/zh-Hans/experience-platform/xdm/tutorials/create-schema-ui.html)和[摄取数据](https://docs.adobe.com/content/help/zh-Hans/experience-platform/ingestion/home.html)。

将数据导入平台时，遵循以下提示有助于在生成的报告中增加洞察力：

* 确保用于将呼叫中心和Web数据链接到一起的标识符的格式类似。
* 在每个数据集中包含数据源。 例如，在每个模式中包括`data_source`列，并将每个事件的值分别设置为`"Web"`或`"Call center"`。<!--mapper-->

## 把人ID缝在一起

CJA需要通用标识符来生成[组合数据集](../connections/combined-dataset.md)。

* 如果您的事件集在两个数据集上的每个数据集上都有一个通用标识符，您可以跳过此步骤并继续创建连接。
* 如果您的任一事件集只有某些渠道具有通用标识符，则可以使用跨分析将数据拼合在一起。 请参阅[跨渠道分析概述](/help/connections/cca/overview.md)以了解为这两个数据集启用CCA的步骤。

## 在CJA中创建连接

[在CJA中](/help/connections/create-connection.md) 创建连接。

* 如果使用CCA，则有新的拼接数据集可供您使用。 将新创建的拼合ID字段用作人员ID。
* 否则，您可以选择在连接中使用的原始Web和呼叫中心数据集。

## 创建数据视图

创建连接后，可以[创建数据视图](/help/data-views/create-dataview.md)以在Analysis Workspace使用。<!-- page dimension last touch, session persistence -->
<!-- create calls metric using call center reason (requires data views 2.0). any column that triggers once per call -->

## 创建可视化

以下可视化功能可用于从拼接数据集获得洞察。

### 数据集重叠

这个可视化功能有助于您了解CCA将数据拼接在一起的效果。

1. 创建两个过滤器。 这两个过滤器中使用的变量与上述变量相同，它反映每个事件的数据源。 有关详细信息，请参阅[创建过滤器](/help/components/filters/create-filters.md)。
   * 数据集ID等于您的Web容器的人员
   * 人员容器，数据集ID等于呼叫中心数据
2. 在Analysis Workspace，将[Venn](/help/analysis-workspace/visualizations/venn.md)可视化拖到工作区画布上。
3. 将两个新创建的过滤器拖到&#x200B;**[!UICONTROL 添加筛选器]**&#x200B;区域，将人员度量拖到&#x200B;**[!UICONTROL 添加度量]**&#x200B;区域。

生成的Venn可视化显示数据集中同时包含Web和呼叫中心数据的人数。 重叠越大，成功缝合的人就越多。 不重叠的区域代表只驻留在一个数据集或另一个数据集中的人员。

### 将呼叫中心事件归属于网页

此自由格式表格允许您查看对呼叫中心事件有贡献的顶级页。 首先，确保所需的维度和指标具有正确的归因模型：

1. 将包含网页名称的维度拖动到自由表格可视化中。
1. 将该指标替换为您要衡量转化率的所需呼叫中心指标。
1. 单击度量标题附近的齿轮图标。 单击&#x200B;**[!UICONTROL 使用非默认归因模型]**。
1. 设置所需的[归因模型](/help/data-views/configure-dataviews.md#Attribution-model)。

结果报告显示来自呼叫中心数据的顶级指标。<!-- Complement with donut visualization -->

<!-- ### Flow between web data and call center

call reason as an exit dimension, web page name for previous pages

### Histogram


### Fallout

step 1: all sessions
step 2: purchase step 1
step 3: call

another good one

step 1: all sessions
step 2: -->

<!--  use target (AB testing) to test new versions of these pages so they reduce calls (using an eVar to determine A/B?)
  filter by specific call reason using workspace dropdowns
  visualize flow of pages > call reason 
-->