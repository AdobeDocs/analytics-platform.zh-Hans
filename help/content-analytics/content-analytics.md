---
title: Content Analytics 概述
description: Content Analytics 概述
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
exl-id: 0d3be50d-c635-459b-8b01-61d6d4ef0cdf
source-git-commit: 58254cab90d907ad9675c30dfc1b835910214b3a
workflow-type: ht
source-wordcount: '854'
ht-degree: 100%

---

# Content Analytics 概述

Content Analytics 帮助营销人员了解内容如何影响企业定义的关键绩效指标。除了行为数据之外，Content Analytics 还收集关于内容如何被消费以及内容如何产生影响的数据。例如，客户是否对某种特定的语调、特定的颜色组合或特定的主题做出更好的反应？这些信息，配合专门设计的报告工作流程和模板，可以帮助您在 Customer Journey Analytics 中执行更出色的分析，并更深入地洞察客户历程数据。

Content Analytics 采用基于 AI 和机器学习的&#x200B;**特征化服务**，将内容分解为多个组件和属性。通过在所有内容上创建结构化的元数据轮廓，您可以分析哪些内容以及这些内容的哪些属性可以推动业务成果。

除了创建这种结构化的元数据配置文件之外，Content Analytics 还提供了一种&#x200B;**身份标识服务**，该服务使用单一身份标识符来识别资产和体验。身份标识服务能够识别出完全相同的资产在多个位置出现的情况。当这种情况发生时，这个资产的多个实例将被视为同一资产，从而可以更全面地了解内容的使用和消费情况。

## 值

Content Analytics 提供递增价值：

1. 内容&#x200B;**使用情况**：借助 Content Analytics，您可以洞察哪些资产获得了印象，以及在何处获得。这些洞察有助于您了解您的网络资产中是否存在资产使用不足或过度使用的情况。
1. 内容&#x200B;**参与度**：Content Analytics 可以提供参与度洞察，例如具有特定属性资产的平均点击率。这些洞察可以帮助您确定特定类型的体验是否仍然有效。
1. 内容&#x200B;**历程**：此外，当与 Experience Platform 中提供的所有其他数据相结合时，您可以获得有关内容历程的更多洞察。例如，除了参与度之外，特定内容是否能够促成转化。有了这些知识，您就能确定各类内容的投资回报率。
1. 内容&#x200B;**个性化**：最终，Content Analytics 使您能够根据洞察采取行动，并利用这些洞察来决定如何为内容投入资金。例如，我应该向特定受众发送特定类型的内容吗？哪些内容能为我提供高度个性化的机会？

## 术语

Content Analytics 使用以下关键术语：

![资产和体验](/help/content-analytics/assets/content-analytics-experience-asset.png)

* **体验**：体验是网页上的所有文本，可以使用访问该网页的初始用户所使用的 URL 被重现。每次体验都会获得一个唯一的标识符。对页面的更改会导致页面 HTML 变化，从而带来新的体验。
* **资产**：资产是单独且独特的内容，如图像。每个资产还会获得一个唯一标识符和一个感知 ID。感知 ID 是与那些在视觉上相同的资产所共享的标识符。对于那些可能具有不同资产 URL 并因此具有不同资产 ID，但感知上相同的资产，感知 ID 有助于删除这类资产的重复数据。
* **属性**：属性是与体验或资产相关的描述性元数据元素。属性的示例有：摄影风格、可读性、说服策略、物体颜色、背景颜色。

## 工作原理

Content Analytics 使用在 Experience Platform 的事件数据集中的网页图像视图数据[收集内容事件数据](config/datacollection.md)。这些内容体验事件需要通过 Experience Platform Edge Network（Web SDK 或服务器 API）进行数据收集。行为数据可通过 Web SDK 或 Analytics 源连接器进行收集。

![Content Analytics 工作原理](assets/aca-overview.gif)

1. 当用户访问[配置了 Content Analytics](config/configuration.md) 的网站时，Experience Plarform Web SDK 会记录对内容的印象以及与内容的交互情况。
1. 身份标识服务和特征化服务会对这些交互进行处理。该过程包括一个检索服务，该服务会重新访问定义这些交互的公众版本的已配置 URL。身份标识服务会为所有这些检索到的 URL 唯一性标识体验和资产。特征化服务应用 AI/ML 服务来发现体验和资产元数据和属性。
1. 这些服务（[组件、属性和身份标识](/help/content-analytics/report/components.md)）的结果用于更新 Experience Platform 中相关的特定 Content Analytics 数据集。
1. Content Analytics 数据以及行为数据和其他查找数据可一起用在 Customer Journey Analytics 配置中（[连接](/help/connections/overview.md)、[数据视图](/help/data-views/data-views.md)和[工作区](/help/analysis-workspace/home.md)）。该设置为对内容的独特宏观级洞察提供了基础。<br/>您可以使用[Content Analytics 模板](/help/content-analytics/report/report.md#template)快速启动 Content Analytics 报告和分析。


>[!NOTE]
>
>Content Analytics 使用 AI/ML 服务，可能会产生不准确或误导性的结果。因此，请运用您的判断力来检查和验证 AI/ML 生成的输出。
>
>您可以使用主界面上 ![InfoOutline](/help/assets/icons/InfoOutline.svg) 中的&#x200B;**[!UICONTROL 反馈]**&#x200B;选项卡，对 AI/ML 生成的输出提供反馈。
>

>[!NOTE]
>
>如果您已获得隐私与安全盾附加组件的许可证，请注意根据 Content Analytics，体验和资产（生成的任何数据）不受 DULE 标签或客户管理密钥的保护。而且，Content Analytics 不是 HIPAA 就绪的服务。
>


>[!MORELIKETHIS]
>
>[Content Analytics 报告](report/report.md)
>[配置 Content Analytics](config/configuration.md)
>[在 Customer Journey Analytics 中计算跳出次数和跳出率](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/calculating-bounces-amp-bounce-rate-in-adobe-customer-journey/ba-p/706446?profile.language=zh-Hans#M454)
>

