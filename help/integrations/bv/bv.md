---
title: 品牌可见度集成
description: 将品牌可见度与Customer Journey Analytics集成
feature: Experience Platform Integration
role: User
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: e75a4a9c-d354-4ca4-9b02-1afeca73fa5e
    internal-label: Integrations
subfeature_v2:
  - id: d3fb138f-79e4-4a81-aedb-76dd93560085
    internal-label: Experience Platform integration
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
source-git-commit: fb3ebdba335ce2dde30d37b8aff4e8f201dc5d9f
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 3%
---

# Adobe Brand Visibility集成

[Adobe Brand Visibility](https://experienceleague.adobe.com/zh-hans/docs/brand-visibility/using/home){target="_blank"}是创新型人工智能优先的创新型引擎优化应用程序，旨在帮助品牌在人工智能驱动的搜索环境中增强可见性、准确性和影响力。 品牌可见度提供对AI生成答案中品牌存在感的洞察、提供规范性内容建议，并自动化优化修复。

人工智能已成为一个主要的发现渠道。 大型语言模型(LLM)代理（如ChatGPT、Claude、Copilot和Perplexity）抓取品牌内容。

>[!NOTE]
>
>您必须配置品牌可见度付费产品，并通过托管连接器连接到您的Experience Platform配置。


>[!IMPORTANT]
>
>作为这种集成的一部分，美国会对品牌可见度数据进行一些临时处理。 数据最终会存储在您在Customer Journey Analytics合同中配置的指定区域。


## 用例

您可以通过两种方式从Customer Journey Analytics与Brand Visibility之间的集成中受益：

* **入站集成**：使用Customer Journey Analytics中的品牌可见度数据测量现有Web、移动和其他类型的数据以及LLM驱动的流量（机器人爬虫、RAG请求、代理活动）。 例如，您可以：

  * 在传统渠道的同时，按代理源测量LLM驱动的流量。

  * 识别LLM大量使用但在人工转化中表现不佳的内容。

  * 检测LLM-agent请求在关键路径上的失败位置。

  * 在URL和主机级别匹配，将某个页面的LLM机器人需求与Web数据中的页面转化率和收入进行比较。

* **出站集成**：将Customer Journey Analytics性能数据发送到Brand Visibility中，以便您能够优化向您发送宝贵流量的LLM源（如ChatGPT或Perplexity）的AI可见性。 例如，您可以：

  * 查看哪些LLM来源会向继续转化或产生收入的人类访客发送信息。 Customer Journey Analytics从引用的Web流量（而不是机器人数据集）测量此值。
  * 按发送的人类访客的下游值对LLM源进行排名，然后将AI可见性工作集中在表现最佳的源上。


## 入站集成

LLM流量可通过两种方式访问您的网站。 Customer Journey Analytics从不同的数据源对每种方式进行测量。

第一种方式是用户阅读人工智能答案，然后点击进入您的网站。 该访问运行的JavaScript与收集您的其余网站数据的相同。 因此，您现有的Customer Journey Analytics Web数据包括访问以及向您发送用户的反向链接域，例如chatgpt.com。 Customer Journey Analytics不会单独将这些访问标记为AI流量。 要识别并分组它们，可在连接上创建与AI反向链接域匹配的派生字段，然后在该字段上构建区段和报表。 请参阅[派生字段](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/derived-fields){target="_blank"}。 您不需要品牌可见度数据集来获取此人员流量。

第二种方法是直接请求页面的机器人或代理。 这包括构建AI索引以及实时获取的爬虫，这些获取是在用户向AI助手提交提示时发生的。 这些请求不会运行任何JavaScript，因此您的现有Web数据不会记录它们。 品牌可见度数据集从CDN层捕获此流量。 本节的其余部分描述了该数据集。


### 载入数据集

品牌可见度托管连接器将数据作为摘要数据集交付给Experience Platform。 要在Customer Journey Analytics中测量客户历程，您需要自行完成两个设置步骤：

1. 创建包含品牌可见度数据集的连接。
2. 在该连接上创建数据视图。 数据视图允许在Analysis Workspace中使用以下维度和量度。

数据集：

* 使用基于XDM摘要度量类的[摘要数据集](/help/data-views/summary-data.md)。
* 按URL和主机、时间和请求特征（如机器人类型、CDN提供商和状态）存储数据。

>[!NOTE]
>
>品牌可见度数据集包含聚合数据。 它不包含任何PII，例如用户标识符、提示或响应。
>

由于它是一个摘要数据集，因此您可以将其用作查找数据集，并以完整URL键将其连接到事件数据集。

品牌可见度在&#x200B;**CDN URL**&#x200B;维度中为您提供此密钥。 它会将主机和请求的路径合并到一个规范化的完整URL中，类似于Customer Journey Analytics存储Web数据的方式。 连接是否成功取决于您自己的数据收集。 您的事件数据集需要一个等效的完整URL字段，或一个可解析并标准化以与品牌可见度提供的URL匹配的字段。 当双方解析为相同的完整URL时，品牌可见度记录与Web数据中的对应页面匹配。

有关详细信息，请参阅：

* [设置和配置入站集成](/help/integrations/bv/configure.md)
* [数据集引用](/help/integrations/bv/reference.md)

## 出站集成

有关出站集成的信息，请参阅Adobe Brand Visibility文档中的[Customer Journey Analytics集成](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/customer-journey-analytics-integration){target="_blank"}。
