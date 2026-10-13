---
title: 品牌可见度入站集成数据集参考
description: 了解用于将Brand Visibility与Customer Journey Analytics集成的数据集的所有详细信息
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
source-git-commit: e3958dfbad19f5fdd78b2755817d21afad8f8e84
workflow-type: tm+mt
source-wordcount: '1894'
ht-degree: 2%
---

# 数据集引用

[Adobe Brand Visibility](https://experienceleague.adobe.com/zh-hans/docs/brand-visibility/using/home){target="_blank"}是创新型人工智能优先的创新型引擎优化应用程序，旨在帮助品牌在人工智能驱动的搜索环境中增强可见性、准确性和影响力。 品牌可见度提供对AI生成答案中品牌存在感的洞察、提供规范性内容建议，并自动化优化修复。

人工智能已成为一个主要的发现渠道。 大型语言模型(LLM)代理（如ChatGPT、Claude、Copilot和Perplexity）抓取品牌内容。

>[!PREREQUISITES]
>
>您必须拥有品牌可见度付费产品。 然后，在Experience Platform沙盒中[配置并启用](./configure.md)Adobe Brand Visibility源。
>


>[!IMPORTANT]
>
>作为这种集成的一部分，美国会对品牌可见度数据进行一些临时处理。 数据最终会存储在您在Customer Journey Analytics合同中配置的指定区域。


## 关于数据集

有关Brand Visibility与Customer Journey Analytics的入站和出站集成用例的更多详细信息，请参阅[概述](./bv.md)。

Brand Visibility读取服务器端的CDN访问日志，并提取请求方是机器人或自动代理的记录。 由于数据来自CDN层，因此Brand Visibility会捕获来自不会触发任何JavaScript标记的机器人的请求。 标准网站分析工具完全没有显示此流量。

数据集使用&#x200B;**CDN请求摘要**&#x200B;字段组。 每个字段都位于`cdn`对象下，因此下表中的字段名称采用<code>cdn._name_&#x200B;的形式</code>，例如`cdn.url`和`cdn.botType`。

每条记录描述主机、URL路径、机器人类型、CDN提供商、状态代码、反向链接、转发主机以及1小时到第一个字节的时间的组合。 当相同的组合每小时出现一次以上时，Customer Journey Analytics会将这些记录组合为一行，并增加请求计数。 使用&#x200B;**CDN请求计数**&#x200B;度量来度量卷。 不要使用行计数。

## 维度

在设置包含品牌可见度数据集的连接后，以下维度可用作数据视图中的组件。 **字段**&#x200B;列显示CDN请求摘要字段组中的源字段。

| 维度 | 字段 | 描述 |
|-----------|-------|-------------|
| CDN URL | `cdn.url` | 请求的规范化完整URL，用作连接键。 品牌可见度将主机和请求的路径合并为一个URL，并将其标准化以匹配Customer Journey Analytics为Web数据存储的完整URL表单。 使用此维度可将品牌可见度查找数据集连接到具有等效的完整URL字段的事件数据集。 它包括主机和路径，但不包括方案。 |
| CDN URL路径 | `cdn.path` | 代理请求的原始URL路径和查询字符串，由CDN提供。 不包括方案或主机。 当您需要确切的请求路径（而不是规范化的连接密钥）时，可使用此选项。 |
| CDN主机 | `cdn.host` | 接收请求的主机名，例如www.example.com。 此主机也是CDN URL连接键的一部分。 当一个组织在同一个CDN帐户上拥有多个子域时，一个数据集可以包含多个主机。 |
| CDN机器人类型 | `cdn.botType` | 品牌可见度对请求代理的分类。 值涵盖经典搜索爬虫、AI索引爬虫和AI实时获取代理。 有关完整分类，请参阅下面的[机器人代理类别](#bot-agent-categories)。 |
| CDN用户代理 | `cdn.userAgent` | CDN日志中的原始用户代理字符串。 用于区分机器人分类中的子类型，或验证由品牌可见度分配的分类。 |
| CDN HTTP状态 | `cdn.status` | HTTP响应状态代码。 指示机器人是否收到其请求的内容。 有关特定于AI流量的解释指南，请参阅下面的[状态代码](#status-codes)。 |
| CDN提供商 | `cdn.cdnProvider` | 哪个CDN处理了请求。 值为`akamai`、`byocdn-akamai`、`byocdn-fastly`和`byocdn-cloudfront`。 `byocdn-`前缀表示日志收集路径，而不是不同的CDN供应商。 当组织在其不同CDN配置之后有主机时，数据集可以包含多个值。 |
| CDN反向链接 | `cdn.referer` | CDN日志中的HTTP引用头值。 对于机器人流量，通常为空。 如果存在，它可以指示触发获取的AI产品或域。 例如，chat.openai.com。 |
| CDN转发的主机 | `cdn.xForwardedHost` | X-Forwarded-Host标头值（如果存在）。 当请求在到达源之前通过反向代理或CDN屏蔽层时相关。 |
| CDN事件日期 | 从记录时间戳派生 | 此记录的每小时批次时间戳的日期部分。 |
| CDN事件小时 | 从记录时间戳派生 | 此记录每小时批次时间戳的小时部分。 |

### 机器人代理类别

**CDN机器人类型**&#x200B;维度将代理组织为三个类别。 每个类别回答一个不同的分析问题。

**传统搜索爬虫**&#x200B;索引传统搜索引擎的内容。 使用此类别可衡量您的内容对传统搜索引擎的可见程度。

| 机器人类型值 | 供应商 | 描述 |
|---|---|---|
| `GoogleBot` | Google | Google的主要搜索索引爬虫。 还提供Google Discover和Google News。 |
| `BingBot` | Microsoft | 必应搜索索引爬虫。 此外还有Microsoft Copilot的Web接地指数。 |

**AI索引爬虫**&#x200B;抓取内容以生成或更新AI产品的训练语料库或搜索索引。 这些爬虫正在准备模型的知识库，没有响应实时用户请求。 当URL具有大量爬虫时，AI供应商会认为内容值得索引。 当URL的爬虫量较低但实时提取量较高时，模型会从缓存的知识中提取，而不是提取新内容。

| 机器人类型值 | 供应商 | 描述 |
|---|---|---|
| `GPTBot` | OpenAI | OpenAI用于模型训练数据和知识库构建的主要爬虫。 |
| `OAI-SearchBot` | OpenAI | OpenAI用于ChatGPT网络搜索产品的爬虫。 不同于GPTBot。 该代理构建的是实时搜索索引，而不是训练语料库。 |
| `ClaudeBot` | 人类学 | 人类对模型训练数据的主要爬虫。 |
| `Claude-SearchBot` | 人类学 | Anthropic对Claude搜索检索索引的爬虫。 与ClaudeBot不同。 |
| `PerplexityBot` | 复杂性 | 复杂度的索引爬虫。 Perplexity使用此代理来构建其答案生成的语料库。 |

**AI实时提取**&#x200B;发生于：实际用户向AI助理提交提示，而该助理在响应之前实时提取页面。 使用此类别可衡量通过AI助理到达的直接用户需求。

| 机器人类型值 | 供应商 | 描述 |
|---|---|---|
| `ChatGPT-User` | OpenAI | 用户向ChatGPT提了一个问题。 ChatGPT已获取此URL以读取它并形成其答案。 |
| `ChatGPT Clients` | OpenAI | ChatGPT移动应用程序（iOS和Android）执行实时获取。 用户代理字符串包含应用程序版本和设备。 |
| `Claude-User` | 人类学 | 使用Claude Live的用户或应用程序获取了此URL。 用户代理字符串可以标识特定的Claude产品，例如claude-code。 |
| `Perplexity-User` | 复杂性 | 用户向Perplexity提了一个问题。 Perplexity获取此URL以构建其答案。 |
| `Google-NotebookLM` | Google | 用户打开了Google NotebookLM并作为此域的来源。 NotebookLM会获取来源域中的每个可访问URL。 |
| `Google-ai-mode` | Google | Google搜索的AI概述功能获取此URL以将其包含在搜索结果中的AI生成答案面板中。 |
| `Gemini-Deep-Research` | Google | 用户运行了Gemini深度研究会话。 Deep Research在多个源中进行多次连续回迁，以编纂研究报告。 |
| `GoogleAgent-URLContext` | Google | 用户与Gemini共享URL并询问有关该页面的问题。 Gemini已获取URL Live以回答有关该特定内容的问题。 |
| `Amzn-User` | Amazon | Amazon Alexa或Amazon AI代理实时获取此URL。 通常显示在引用和文档内容中。 |
| `MistralAI-User` | Mistral | 从Mistral支持的产品或API使用者中实时获取。 |

当品牌可见度无法将user-agent与可识别的模式匹配时，它分配值`Unknown`。 您可以使用&#x200B;**CDN用户代理**&#x200B;维度来识别发出这些请求的代理。

### 状态代码

此数据集中的HTTP状态代码指示AI代理是否收到其请求的内容。

| 状态 | 名称 | 解释 |
|--------|------|----------------|
| 200 | 确定 | 机器人收到了完整响应。 该内容可供AI使用。 |
| 304 | 未修改 | 机器人确认内容未更改并使用其缓存版本。 内容可用。 |
| 301 | 已永久移动 | 机器人被重定向到新的URL。 每个重定向会添加一个额外的来回访问。 经常抓取的URL上的301流量过高意味着应在CDN级别解析重定向。 |
| 302 | 已找到（临时重定向） | 延迟惩罚与301相同。 与301不同，它不表示永久移动，因此机器人将继续点击原始URL。 |
| 403 | 禁止 | CDN或源阻止该机器人。 这可能是有意为之，例如，通过robots.txt规则或WAF策略，或者可能是无意的，例如，通过过于宽泛的速率限制。 当AI获取被阻止时，该内容无法出现在AI答案中。 |
| 404 | 未找到 | URL不存在。 AI代理类型上的404数量过高表示AI索引包含陈旧的URL。 使用410状态告知爬虫从其索引中永久删除URL。 |
| 429 | 请求过多 | CDN速率限制了机器人。 实时获取代理类型持续出现429错误，这意味着向AI助手询问有关您内容的问题时，用户将收到不完整或缺失的响应。 |
| 504 | 网关超时 | CDN已停止等待源响应。 内容未到达人工智能。 当页面超时时，AI无法访问其内容，也无法将其包含在答案中。 实时获取代理类型上的高504卷存在直接的AI可见性风险。 |

## 量度

在设置包含品牌可见度数据集的连接后，以下量度可用作数据视图中的组件。 **字段**&#x200B;列显示CDN请求摘要字段组中的源字段。

| 量度 | 字段 | 描述 |
|--------|-------|-------------|
| CDN请求计数 | `cdn.requests` | CDN请求的总数（从请求字段中所有行的总和）。 始终使用此量度测量数量。 不要使用行计数。 |
| CDN错误计数 | `cdn.status`, `cdn.requests` | 返回4xx或5xx HTTP状态代码的请求计数。 |
| CDN错误率 | 派生自CDN错误计数 | 错误数占总请求数的百分比。 |
| CDN到第一个字节的平均时间 | `cdn.timeToFirstByte` | CDN收到响应第一个字节的请求后的平均时间（以毫秒为单位）。 CDN缓存的响应通常不超过50毫秒。 从源提供的响应通常为300毫秒到700毫秒。 AI实时获取代理通常显示更高的值，对应于超时或极慢的原始响应。 实时获取代理类型的高平均值值得调查为AI可见性风险。 |

## 边界

此数据集仅从CDN访问日志中捕获机器人流量。 它不包含下列内容：

* **用户会话、转化或参与数据。** 通过点击人工智能答案的用户会在您的页面上运行JavaScript，因此访问位于您现有的Web数据中，而不是此数据集中。 您可以将两个数据集引入Customer Journey Analytics，并比较它们对于同一URL和主机的效果。
* **任何人员标识符，如ECID。** 您无法从此数据集执行人员级别联接。 连接在URL和主机级别运行。
* **次秒时间粒度。** 时间戳为每小时。 您无法将一小时内的流量划分为几分钟或几秒钟。
* **页面内容或渲染的HTML。** 此数据集记录获取及其结果的实际，而不是AI从页面中读取的内容。
* **转换数据。** 此数据集不会告诉您人工智能答案是否会导致人员访问您的网站或进行转化。 它包含汇总的CDN摘要数据，而不是基于人员的事件数据，因此不会将任何请求关联到个人或会话。
