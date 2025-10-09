---
title: 使用派生字段报告LLM和AI生成的流量
description: 了解如何使用派生字段作为在Workspace中报告LLM和AI生成的流量的基础。
solution: Customer Journey Analytics
feature: Use Cases
role: User
hide: true
hidefromtoc: true
source-git-commit: 1cf0d957d62d60979982320f45b4fdadcc7458b8
workflow-type: tm+mt
source-wordcount: '1219'
ht-degree: 1%

---


# 关于LLM和AI生成的流量的报告

本用例文章探讨了如何使用Customer Journey Analytics派生字段功能作为报告LLM（大语言模型）和AI生成的流量的基础。

## 检测方法

要检测LLM和AI生成的流量，请区分：

* **LLM爬网程序**：收集用于训练和检索增强生成(RAG)的数据。
* **AI代理**：充当代表人类执行任务的接口。 AI代理更喜欢通过API进行交互，这绕过了网站分析跟踪方法。 尽管如此，您仍然可以分析人工智能生成的网站流量的很大一部分。

用于识别和监控LLM和AI生成的流量的三种常见核心检测方法是：

* **用户代理标识**：向服务器发出请求时，将提取HTTP User-Agent标头并根据已知的AI爬网程序和代理模式进行分析。 此服务器端方法需要访问HTTP标头，并且在数据收集层实施时最有效。
* **反向链接分类**： HTTP反向链接标头包含链接到当前请求的上一个网页的URL。 当用户从ChatGPT或Perplexity等Web界面点击进入您的网站时，此标题会显示。
* **查询参数检测**： AI服务可以将URL参数（特别是UTM参数）附加到链接。 这些参数会在URL中持续存在，并且可以通过标准分析实施进行检测，这使得这些URL参数即使在客户端跟踪场景中也可以发挥重要作用。

下表说明了如何针对不同的LLM和AI交互场景使用这些检测方法。

| 场景 | 用户代理标识 | 反向链接分类 | 查询参数检测 |
|---|---|---|---|
| **训练模型** | 实施服务器端日志记录时，可以识别代理（`GPTBot`、`ClaudeBot`等）。 | 无法分类。 AI爬虫在训练期间不会生成反向链接。 | 检测是不可能的。 AI爬网程序在训练期间不添加参数。 |
| **代理浏览** | 服务器端日志记录捕获标头时可以识别代理(`ChatGPT-User`， `claude-web`)。 | 如果代理从具有反向链接保留的AI界面导航，则可以进行分类。 | 如果AI服务添加跟踪参数，则有时可能进行检测。 |
| 用于回答查询的&#x200B;**Retrieval-Enhanced Generation (RAG)** | 可以使用服务器端日志记录标识代理(`OAI-SearchBot`， `PerplexityBot`)。 | 由于RAG操作通常会绕过反向链接机制，因此通常不可能进行分类。 | 除非由AI提供程序专门实施，否则很少可能进行检测。 |
| **用户点进次数** | 无法识别代理。 AI代理显示为普通用户代理。 | 当用户从AI界面单击链接（[chatgpt.com](https://chatgpt.com)、[claude.ai](https://claude.ai)等）时，可以进行分类。 | 当AI服务将UTM参数添加到出站链接时，可能会进行检测。 |
| **流量可见性条件** | 需要与Customer Journey Analytics或服务器端标记集成的服务器端日志记录才能识别代理。 | 分类取决于AI平台反向链接策略和适当的HTTP标头传输。 | 检测要求通过重定向和正确的URL参数收集来保留参数。 |

### 挑战

LLM和AI代理在与数字属性交互时表现出复杂且不断演变的行为。 这些技术在不同平台和版本之间运行不一致。 这种不一致给数据专业人员带来了独特的挑战。 行为模式存在显着差异，具体取决于所使用的特定AI平台、版本和交互模式。 这种操作多样性使得在标准分析框架中跟踪和分类LLM和AI生成的流量的工作变得复杂。 这些交互的复杂性质，加上其快速演化，需要细致的检测和分类方法来维护数据完整性：

* **部分数据收集**：一些较新的AI代理执行有限的JavaScript，导致客户端实施的Analytics数据不完整。 因此，某些交互会被跟踪，而其他交互会被错过。
* **会话数据不一致**： AI代理可能在不同会话或页面类型中执行JavaScript的方式有所不同。 这种执行差异在Customer Journey Analytics中为客户端实施创建了零碎的用户旅程。
* **检测挑战**：对于部分跟踪，检测变得不可靠，因为某些接触点可能对Analytics不可见。


## 检测签名

从2025年8月起，可以识别每种检测方法的以下特定信号。

### 用户代理标识

<table>
<thead>
<tr>
<th>爬网程序</th>
<th>用户代理字符串</th>
<th>用途/行为</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>GPTBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; GPTBot/1.1; +<a href="https://openai.com/gptbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/gptbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">OpenAI的主要网络爬虫程序，用于训练ChatGPT和语言模型</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/1.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">在ChatGPT代表用户浏览网站时使用（旧版）</a></td>
</tr>
<tr>
<td><strong>ChatGPT-User v2</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ChatGPT-User/2.0; +<a href="https://openai.com/bot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/bot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">ChatGPT的更新版本用于按需获取和响应查找</a></td>
</tr>
<tr>
<td><strong>OAI-SearchBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; OAI-SearchBot/1.0; +<a href="https://openai.com/searchbot" target="_blank" rel="noopener nofollow noreferrer">https://openai.com/searchbot</a></code></td>
<td><a href="https://platform.openai.com/docs/bots/" target="_blank" rel="noopener nofollow noreferrer">ChatGPT的搜索主题爬虫程序，用于发现内容</a></td>
</tr>
<tr>
<td><strong>克劳德机器人</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko); compatible; ClaudeBot/1.0; +claudebot@anthropic.com</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">用于训练和更新克劳德AI助理的人工爬行器</a></td>
</tr>
<tr>
<td><strong>克劳德用户</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-User/1.0; +Claude-User@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">支持Claude AI用户，当个人向Claude提问时，它可以使用Cl访问网站……</a></td>
</tr>
<tr>
<td><strong>克劳德 — 搜索机器人</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Claude-SearchBot/1.0; +Claude-SearchBot@anthropic.com)</code></td>
<td><a href="https://support.claude.com/en/articles/8896518-does-anthropic-crawl-data-from-the-web-and-how-can-site-owners-block-the-crawler" target="_blank" rel="noopener nofollow noreferrer">通过在线内容分析，对Claude AI用户进行网络导航，以提高其搜索结果质量。</a></td>
</tr>
<tr>
<td><strong>PerplexityBot</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; PerplexityBot/1.0; +<a href="https://www.perplexity.ai/perplexitybot" target="_blank" rel="noopener nofollow noreferrer">https://perplexity.ai/perplexitybot</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">Perplexity.ai用于实时编制网页数据索引的爬虫程序</a></td>
</tr>
<tr>
<td><strong>Perplexity — 用户</strong></td>
<td><code>Mozilla/5.0 AppleWebKit/537.36 (KHTML, like Gecko; compatible; Perplexity-User/1.0; +<a href="https://www.perplexity.ai/useragent" target="_blank" rel="noopener nofollow noreferrer">https://www.perplexity.ai/useragent</a>)</code></td>
<td><a href="https://docs.perplexity.ai/guides/bots" target="_blank" rel="noopener nofollow noreferrer">在用户单击Perplexity引文时加载页面（绕过robots.txt）</a></td>
</tr>
<tr>
<td><strong>Google-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Google-Extended/1.0; +<a href="https://support.google.com/webmasters/answer/182072" target="_blank" rel="noopener nofollow noreferrer">http://www.google.com/bot.html</a>)</code></td>
<td><a href="https://blog.google/technology/ai/an-update-on-web-publisher-controls/" target="_blank" rel="noopener nofollow noreferrer">Google面向Gemini的以人工智能为中心的爬虫程序，独立于标准的GoogleBot</a></td>
</tr>
<tr>
<td><strong>BingBot</strong></td>
<td><code>Mozilla/5.0 (compatible; BingBot/1.0; +<a href="http://www.bing.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bing.com/bot.html</a>)</code></td>
<td>Microsoft的爬虫程序为Bing Search和Bing Chat提供支持(Copilot)</td>
</tr>
<tr>
<td><strong>DuckAssistBot</strong></td>
<td><code>Mozilla/5.0 (compatible; DuckAssistBot/1.0; +<a href="https://duckduckgo.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.duckduckgo.com/bot.html</a>)</code></td>
<td><a href="https://duckduckgo.com/duckduckgo-help-pages/results/duckassistbot" target="_blank" rel="noopener nofollow noreferrer">为DuckDuckGo的私人AI应答功能DuckAssist删除内容</a></td>
</tr>
<tr>
<td><strong>YouBot</strong></td>
<td><code>Mozilla/5.0 (compatible; YouBot (+<a href="http://www.you.com" target="_blank" rel="noopener nofollow noreferrer">http://www.you.com</a>))</code></td>
<td>You.com的AI搜索和浏览器助手背后的爬网程序</td>
</tr>
<tr>
<td><strong>meta-externalagent</strong></td>
<td><code>Mozilla/5.0 (compatible; meta-externalagent/1.1 (+<a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers" target="_blank" rel="noopener nofollow noreferrer">https://developers.facebook.com/docs/sharing/webmasters/crawler</a>))</code></td>
<td><a href="https://developers.facebook.com/docs/sharing/webmasters/web-crawlers#identify-2" target="_blank" rel="noopener nofollow noreferrer">Meta用于收集数据以训练或微调LLM的机器人</a></td>
</tr>
<tr>
<td><strong>Amazonbot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_1) AppleWebKit/600.2.5 (KHTML, like Gecko) Version/8.0.2 Safari/600.2.5 (Amazonbot/0.1; +<a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">https://developer.amazon.com/support/amazonbot</a>)</code></td>
<td><a href="https://developer.amazon.com/amazonbot" target="_blank" rel="noopener nofollow noreferrer">Amazon的搜索和AI应用程序爬网程序</a></td>
</tr>
<tr>
<td><strong>Applebot</strong></td>
<td><code>Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_5) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/13.1.1 Safari/605.1.15 (Applebot/0.1; +<a href="https://support.apple.com/kb/HT6619" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/go/applebot</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Apple的聚焦、Siri和Safari爬虫程序</a></td>
</tr>
<tr>
<td><strong>Applebot-Extended</strong></td>
<td><code>Mozilla/5.0 (compatible; Applebot-Extended/1.0; +<a href="https://www.apple.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.apple.com/bot.html</a>)</code></td>
<td><a href="https://support.apple.com/en-us/119829" target="_blank" rel="noopener nofollow noreferrer">Apple面向未来AI模型的以AI为中心的爬虫程序（选择加入）</a></td>
</tr>
<tr>
<td><strong>Bytespid</strong></td>
<td><code>Mozilla/5.0 (compatible; Bytespider/1.0; +<a href="https://www.bytedance.com/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.bytedance.com/bot.html</a>)</code></td>
<td>字节跳动用于TikTok和其他服务的AI数据收集器</td>
</tr>
<tr>
<td><strong>MistralAI — 用户</strong></td>
<td><code>Mozilla/5.0 (compatible; MistralAI-User/1.0; +<a href="https://mistral.ai/bot" target="_blank" rel="noopener nofollow noreferrer">https://mistral.ai/bot</a>)</code></td>
<td><a href="https://docs.mistral.ai/robots/" target="_blank" rel="noopener nofollow noreferrer">Mistral的“Le Chat”助理实时引文提取器</a></td>
</tr>
<tr>
<td><strong>cohere-ai</strong></td>
<td><code>Mozilla/5.0 (compatible; cohere-ai/1.0; +<a href="http://www.cohere.ai/bot.html" target="_blank" rel="noopener nofollow noreferrer">http://www.cohere.ai/bot.html</a>)</code></td>
<td>为Cohere的语言模型收集文本数据</td>
</tr>
</tbody>
</table>


### 反向链接分类

<table>
<thead>
<tr>
<th><strong>来源</strong></th>
<th><strong>反向链接</strong></th>
<th><strong>流量类型</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td>chatgpt.com</td>
<td>直接来自ChatGPT界面的流量</td>
</tr>
<tr>
<td>克劳德</td>
<td>claude.ai</td>
<td>来自Anthropic的Claude界面的流量</td>
</tr>
<tr>
<td>Google Gemini</td>
<td>gemini.google.com</td>
<td>来自Google AI助理的流量</td>
</tr>
<tr>
<td>Microsoft Copilot</td>
<td>copilot.microsoft.com</td>
<td>来自Microsoft AI助理的流量</td>
</tr>
<tr>
<td>Microsoft Copilot</td>
<td>m365.cloud.microsoft</td>
<td>来自Microsoft AI助手(Microsoft 365 cloud services)的流量</td>
</tr>
<tr >
<td>复杂人工智能</td>
<td>perplexity.ai</td>
<td>来自具有引文的AI搜索的流量</td>
</tr>
<tr>
<td>Meta人工智能</td>
<td>meta.ai</td>
<td>来自Meta AI助理的流量</td>
</tr>
</tbody>
</table>

### 查询参数检测

<table>
<thead>
<tr>
<th><strong>LLM服务</strong></th>
<th>示例URL</th>
<th><strong>查询参数</strong></th>
<th><strong>示例值</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>ChatGPT</td>
<td ><a href="https://www.yoursite.com/product?utm_source=chatgpt.com" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/product?utm_source=chatgpt.com</a></td>
<td>utm_source</td>
<td>chatgpt.com</td>
</tr>
<tr>
<td>复杂性</td>
<td><a href="https://www.yoursite.com/article?utm_source=perplexity" target="_blank" rel="noopener nofollow noreferrer">https://www.yoursite.com/article?utm_source=perplexity</a></td>
<td>utm_source</td>
<td>复杂性</td>
</tr>
</tbody>
</table>


## 实施

您可以通过[派生字段](#derived-fields)、[区段](#segments)和[工作区项目](#workspace-project)的特定设置和配置，在典型的Customer Journey Analytics设置（连接、数据视图、工作区项目）中报告LLM和AI生成的流量。


### 派生字段

要配置检测方法和检测信号，需以派生字段为基础。 例如，定义用于用户代理识别、查询参数检测和反向链接分类的派生字段。

#### LLM/AI用户代理识别

使用[Case When](/help/data-views/derived-fields/derived-fields.md#case-when)派生字段函数定义标识LLM/AI用户代理的派生字段。

![LLM/AI用户代理标识](assets/aitraffic-useragents.png){zoomable="yes"}


#### LLM/AI查询参数检测

使用[URL Parse](/help/data-views/derived-fields/derived-fields.md#url-parse)和[Classify](/help/data-views/derived-fields/derived-fields.md#classify)派生字段函数定义可检测UTM参数检测的派生字段。

![LLM/AI UTM参数检测](assets/aitraffic-utmparams.png){zoomable="yes"}


#### LLM/AI反向链接分类

使用“URL解析”和“对派生字段进行分类”函数可定义用于对反向链接进行分类的派生字段。

![LLM/AI反向链接分类](assets/aitraffic-utmparams.png){zoomable="yes"}


### 区段

设置专用区段，帮助您识别与LLM和AI生成的流量相关的事件、会话或人员。 例如，使用您之前创建的派生字段定义一个区段，以标识LLM和AI生成的流量。

![LLM和AI生成的流量区段](assets/aitraffic-segment.png){zoomable="yes"}


### Workspace项目

使用派生的字段和区段来报告和分析LLM和AI生成的流量。 例如，请参阅下面带注释的项目。

![LLM和AI生成的流量Workspace项目](assets/aitraffic-workspace.png){zoomable="yes"}



>[!MORELIKETHIS]
>
>此用例文章基于Brian Au的博客文章： [在Adobe Customer Journey Analytics中跟踪和分析LLM和AI生成的流量](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/tracking-and-analyzing-llm-and-ai-generated-traffic-in-adobe/ba-p/771967)
>
>
