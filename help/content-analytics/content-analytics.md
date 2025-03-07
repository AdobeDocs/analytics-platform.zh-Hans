---
title: 内容分析概述
description: Content Analytics概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hide: true
hidefromtoc: true
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 8c257279353112df583b46d87ea17749a75867e2
workflow-type: tm+mt
source-wordcount: '668'
ht-degree: 0%

---

# 内容分析概述

>[!WARNING]
>
>本文是即将发布的最终版本的初步非官方草稿版本，是内容分析文档的一部分。 所有内容可能会发生更改，并且本条当前版本不承担任何法律义务。
>

{{release-limited-testing}}

内容分析可帮助营销人员了解内容如何影响企业定义的关键绩效指标。 除了行为数据之外， Content Analytics还收集如何使用内容以及内容如何推动影响的数据。 例如，客户对特定语调、特定调色板或特定主题的响应是否更好？ 此信息，以及特别设计的报表工作流和模板，可帮助您在Customer Journey Analytics中执行更好的分析并更深入地了解客户历程数据。

Content Analytics使用基于AI和机器学习的&#x200B;**特征化服务**&#x200B;将内容划分为组件和属性。 通过在您的所有内容上创建结构化元数据配置文件，您可以分析哪些内容以及该内容的哪些属性驱动了业务成果。

除了创建此结构化元数据配置文件之外，Content Analytics还提供使用单个标识符标识资产和体验的&#x200B;**标识服务**。 Identity Service可以识别同一资产何时出现在多个位置。 发生这种情况时，资产的两个实例将被视为相同，从而允许更全面地查看内容使用和使用。

## 值

内容分析的价值确实在不断增长：

1. 内容&#x200B;**使用情况**：通过Content Analytics，您可以深入了解哪些资产会收到展示次数，以及哪些资产会收到展示次数。 这些见解可帮助您查看资产在Web资产上是否未被充分利用或过度使用。
1. 内容&#x200B;**参与**： Content Analytics可以提供参与见解，例如具有某些属性的资产的平均点进率。 这些见解可帮助您确定特定类型的体验是否仍然有效。
1. 内容&#x200B;**历程**：此外，在与Experience Platform中的所有其他可用数据结合使用时，您可以获得有关内容历程的其他见解。 例如，在参与度之外，特定内容是否会导致转化。 利用这些知识，您可以确定内容类型的ROI。
1. 内容&#x200B;**个性化**：最终，内容分析允许您根据见解采取行动，并使用这些见解确定如何在内容上花费资金。 例如，我应该将特定类型的内容发送给特定受众吗？ 哪些内容为我提供了高度个性化的机会？

## 术语

Content Analytics使用以下关键术语：

![Assets和体验](/help/content-analytics/assets//content-analytics-experience-asset.png)

* **体验**：体验是网页上的所有文本，可以使用访问该网页的初始用户所使用的URL进行复制。 每个体验都获得一个唯一标识符。
* **资源**：资源是个别且唯一的内容，如图像。 每个资产还会获得一个唯一标识符。
* **属性**：属性是与体验或资源关联的描述性元数据元素。 属性的示例包括：摄影样式、可读性、说服策略、对象颜色、背景颜色。

## 工作原理

Content Analytics使用在Experience Platform的事件数据集中收集的Web图像视图数据。 可以通过各种可用方法收集此数据： Experience Platform Edge Network(Web SDK、服务器API)或Analytics Source Connector。

![内容分析 — 工作原理](assets/how-it-works.png)


1. 当用户访问网站时，为Content Analytics配置的Experience Plarform Web SDK记录与内容的交互。
1. 特征化汇编程序服务和标识服务处理重新访问的数据。
1. 这些服务（组件、属性和身份）的结果用于更新Experience Platform中的相关特定内容分析数据集。
1. 然后，可以在Customer Journey Analytics配置(连接、数据视图和Workspace)中使用内容分析数据以及行为数据和其他查找数据集。 该配置为您的内容提供了独特的宏级别见解的基础。

>[!NOTE]
>
>Content Analytics利用AI/ML。 结果（用于体验和资源的功能化）可能不准确。
>


>[!MORELIKETHIS]
>
>[Content Analytics报告](report/report.md)
>[配置内容分析](config/configuration.md)
