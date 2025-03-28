---
title: 内容分析概述
description: Content Analytics概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 1acb6ee56ec3d1c5ae21bb857205a0b9cc66cea0
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 0%

---

# 内容分析概述

{{release-limited-testing}}

内容分析可帮助营销人员了解内容如何影响企业定义的关键绩效指标。 除了行为数据之外，Content Analytics还收集有关如何使用内容以及内容如何推动影响的数据。 例如，客户对特定语调、特定调色板或特定主题的响应是否更好？ 此信息，以及特别设计的报表工作流和模板，可帮助您在Customer Journey Analytics中执行更好的分析并更深入地了解客户历程数据。

Content Analytics使用基于AI和机器学习的&#x200B;**特征化服务**&#x200B;将内容划分为组件和属性。 通过在您的所有内容上创建结构化元数据配置文件，您可以分析哪些内容以及该内容的哪些属性驱动了业务成果。

除了创建此结构化元数据配置文件之外，Content Analytics还提供使用单个标识符标识资产和体验的&#x200B;**标识服务**。 Identity Service可以识别同一资产何时出现在多个位置。 发生这种情况时，会将此资源的实例视为相同的资源，从而更全面地查看内容的使用和使用。

## 值

内容分析的价值确实在不断增长：

1. 内容&#x200B;**使用情况**：通过Content Analytics，您可以深入了解哪些资产会收到展示次数，以及哪些资产会收到展示次数。 这些见解可帮助您查看资产在Web资产上是否未被充分利用或过度使用。
1. 内容&#x200B;**参与**： Content Analytics可以提供参与见解，例如具有某些属性的资产的平均点进率。 这些见解可帮助您确定特定类型的体验是否仍然有效。
1. 内容&#x200B;**历程**：此外，在与Experience Platform中的所有其他可用数据结合使用时，您可以获得有关内容历程的其他见解。 例如，在参与度之外，特定内容是否会导致转化。 利用这些知识，您可以确定内容类型的ROI。
1. 内容&#x200B;**个性化**：最终，Content Analytics允许您根据见解采取行动，并使用这些见解确定如何花钱购买内容。 例如，我应该将特定类型的内容发送给特定受众吗？ 哪些内容为我提供了高度个性化的机会？

## 术语

Content Analytics使用以下关键术语：

![Assets和体验](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **体验**：体验是网页上的所有文本，可以使用访问网页的初始用户使用的URL重现这些文本。 每个体验都获得一个唯一标识符。 对页面所做的更改将导致对页面的HTML所做的更改从而产生新的体验。
* **资源**：资源是个别且唯一的内容，如图像。 每个资产还会获取一个唯一标识符和一个可感知ID。 可感知ID是与视觉上相同的资产共享的标识符。 可感知ID可帮助删除重复资产，这些资产可能具有不同的资产URL，因此具有不同的资产ID，但在感知上相同。
* **属性**：属性是与体验或资源关联的描述性元数据元素。 属性的示例包括：摄影样式、可读性、说服策略、对象颜色、背景颜色。

## 工作原理

Content Analytics使用在Experience Platform的事件数据集中收集的Web图像视图数据。 可以通过各种可用方法收集此数据： Experience Platform Edge Network(Web SDK、服务器API)或Analytics Source Connector。

![内容分析 — 工作原理](assets/aca-overview.gif)


1. 当用户访问为Content Analytics](config/configuration.md)配置的[网站时，Experience Platform Web SDK会记录展示次数以及与内容的交互。
1. 身份和特征化服务处理这些交互。 此过程包含一个检索服务，该服务会修订定义交互的已配置URL的面向公众的版本。 对于所有这些检索到的URL，标识服务将唯一标识体验和资产。 而功能化服务则应用AI/ML服务来发现体验和资源的元数据和属性。
1. 这些服务（[组件、属性和标识](/help/content-analytics/report/components.md)）的结果用于更新Experience Platform中的相关特定内容分析数据集。
1. 内容分析数据以及行为数据和其他查找数据可以在Customer Journey Analytics设置中使用([连接](/help/connections/overview.md)、[数据视图](/help/data-views/data-views.md)和[Workspace](/help/analysis-workspace/home.md))。 该设置提供了对您的内容进行独特的宏级深入分析的基础。 <br/>您可以使用[Content Analytics模板](/help/content-analytics/report/report.md#template)快速启动Content Analytics报表和分析。

>[!NOTE]
>
>Content Analytics利用AI/ML服务可能会产生不准确或误导性的结果。 因此，请根据您的判断来审查和验证AI/ML生成的输出。
>
>您可以使用主界面上![InfoOutline](/help/assets/icons/InfoOutline.svg)中提供的&#x200B;**[!UICONTROL 反馈]**&#x200B;选项卡针对AI/ML生成的输出提供反馈。
>

>[!NOTE]
>
>如果您已许可Privacy and Security Shield插件，请注意，根据Content Analytics，DULE标签或客户管理的密钥不包含（任何从生成的）体验和资源。
>


>[!MORELIKETHIS]
>
>[Content Analytics报告](report/report.md)
>[配置内容分析](config/configuration.md)
>

