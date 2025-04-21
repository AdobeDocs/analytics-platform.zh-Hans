---
title: 内容分析概述
description: 内容分析概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: feb253b20820112d5aa4b4eee31cff74d99fa186
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 44%

---

# 内容分析概述

{{release-limited-testing}}

内容分析帮助营销人员了解内容如何影响企业定义的关键绩效指标。除了行为数据之外，Content Analytics还收集有关如何使用内容以及内容如何推动影响的数据。 例如，客户对特定语调、特定调色板或特定主题的响应是否更好？ 这些信息，配合专门设计的报告工作流程和模板，可以帮助您在 Customer Journey Analytics 中执行更出色的分析，并更深入地洞察客户历程数据。

内容分析采用基于人工智能和机器学习的&#x200B;**特征化服务**，将内容分解为各个组件和属性。通过在所有内容上创建结构化的元数据轮廓，您可以分析哪些内容以及这些内容的哪些属性可以推动业务成果。

除了创建这种结构化的元数据轮廓之外，内容分析还提供了一种&#x200B;**身份标识服务**，该服务使用单一身份标识符来识别资产和体验。身份标识服务能够识别出完全相同的资产在多个位置出现的情况。发生这种情况时，会将此资源的实例视为相同的资源，从而更全面地查看内容的使用和使用。

## 值

内容分析确实提供了越来越大的价值：

1. 内容&#x200B;**使用情况**：借助内容分析，您可以深入了解哪些资产正在获得印象，以及这些资产在哪里获得印象。这些洞察有助于您了解您的网络资产中是否存在资产使用不足或过度使用的情况。
1. 内容&#x200B;**参与度**：内容分析可以提供参与度洞察，例如具有特定属性的资产的平均点击率。这些洞察可以帮助您确定特定类型的体验是否仍然有效。
1. 内容&#x200B;**历程**：此外，当与 Experience Platform 中提供的所有其他数据相结合时，您可以获得有关内容历程的更多洞察。例如，除了参与度之外，特定内容是否能够促成转化。有了这些知识，您就能确定各类内容的投资回报率。
1. 内容&#x200B;**个性化**：最终，内容分析使您能够根据洞察采取行动，并利用这些洞察来决定如何在内容上投入资金。例如，我应该向特定受众发送特定类型的内容吗？哪些内容能为我提供高度个性化的机会？

## 术语

内容分析使用以下关键术语：

![资产和体验](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **体验**：体验是网页上的所有文本，可以使用访问网页的初始用户使用的URL重现这些文本。 每个体验都获得一个唯一标识符。 对页面所做的更改将导致对页面的HTML所做的更改从而产生新的体验。
* **资产**：资产是单独且独特的内容，如图像。每个资产还会获取一个唯一标识符和一个可感知ID。 可感知ID是与视觉上相同的资产共享的标识符。 可感知ID可帮助删除重复资产，这些资产可能具有不同的资产URL，因此具有不同的资产ID，但在感知上相同。
* **属性**：属性是与体验或资产相关的描述性元数据元素。属性的示例有：摄影风格、可读性、说服策略、物体颜色、背景颜色。

## 工作原理

Content Analytics在Experience Platform的事件数据集中使用Web图像视图数据来[收集内容事件数据](config/datacollection.md)。 并将该内容数据收集与（现有）行为数据收集实施整合在一起。

![内容分析——工作原理](assets/aca-overview.gif)

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

>[!NOTE]
>
>Content Analytics [发送了额外事件](config/datacollection.md#content-analytics-event)，这些事件极有可能影响任何基于会话或页面中事件数的跳出率定义。
>

>[!MORELIKETHIS]
>
>[内容分析报告](report/report.md)
>[配置内容分析](config/configuration.md)
>[在Customer Journey Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446#M454)中计算跳出次数和跳出率
>

