---
title: 当前的Customer Journey Analytics发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: f3aad257d518373812176cb123d799b83cf45520
workflow-type: tm+mt
source-wordcount: 1261
ht-degree: 20%

---

# 当前Customer Journey Analytics发行说明（2026年9月）

**上次更新日期**：2026年9月9日

这些发行说明涵盖2026年9月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或更新后的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **Customer Journey Analytics MCP服务器插件**<br/>&#x200B;使用适用于ChatGPT和Claude的新Customer Journey Analytics MCP服务器插件快速访问您的数据。 <p>有关详细信息，请参阅[连接到ChatGPT](https://developer.adobe.com/analytics-mcp/docs/guides/chatgpt)和[连接到Claude](https://developer.adobe.com/analytics-mcp/docs/guides/claude)。</p> | 2026年9月1日 | 2026年9月1日 |
| **支持其他数据使用标签**<br> Customer Journey Analytics现在支持数据集内元素的以下其他数据使用标签：<ul><li>C2 — 限制第三方数据导出（现在可用）</li><li>C3 — 限制可直接识别的数据组合（现在可用）</li><li>C9 — 限制数据科学（计划于8月或9月发布）</li></ul><p>有关详细信息，请参阅[标签、策略和营销操作](/help/data-views/data-governance.md)。</p> | | 2026年9月3日 |
| **同意策略筛选和报告**<br>&#x200B;您现在可以报告哪些访客与您的Adobe Experience Platform同意策略匹配。 （同意策略维度和量度会添加到连接中的数据视图。）<p>此外，您可以先排除非同意访客，然后再将其数据摄取到Customer Journey Analytics。</p><p>（文档链接见下文。）<!--For more information, see Consent reporting and filtering overview.--></p> | | 2026年9月 |
| **将区段限制为报表日期范围**<br/>&#x200B;当区段包含日期范围组件时，Workspace报表中的数据可能会超出报表日期范围。<p>现在提供了一个新选项，通过该选项可将结果限制为报表日期范围，而不管该区段中包含的任何日期组件如何。</p><p>创建或修改顶级容器为“人员”的区段时，此选项可用。</p><p>有关详细信息，请参阅[生成区段](/help/components/segments/seg-builder.md#components)。</p> | 2026年8月26日 | 2026年9月9日 |
| **在Analysis Workspace中使用对话见解分析LLM客户体验**<br/> Customer Journey Analytics现在将非结构化聊天数据引入Analysis Workspace，允许您报告资产中利用LLM进行的浏览和购买体验。<p>利用此功能，您可以：</p><ul><li>通过Web SDK从对话代理（贵组织的自定义代理或Adobe Brand Concierge）收集提示、响应和代理元数据。</li><li>分析意图、语气和情绪，以便您了解客户提出的问题、您的座席如何回应以及客户对其交互的感受。</li><li>使用现有架构、数据集和数据视图进行大规模分析，然后在Analysis Workspace中显示见解。</li><li>通过将代理互动与更广泛的客户历程联系起来，将对话与成果联系起来，以便您衡量对转化、参与度等工作的实际影响。</li></ul><p>以前，由LLM提供支持的体验难以测量，并且几乎无法连接到您现有的客户历程。</p><p>（文档链接将随后提供。）</p> | | 2026年9月22日 |
| **总人口报告**<br/>&#x200B;您现在可以分析和报告在Customer Journey Analytics连接中存在的配置文件和查找数据集中定义的实体。 这种分析和报告不仅仅是来自事件数据集的基于时间的事件系列。 <p>此功能支持新类别的查询、量度和受众定义，它们反映了企业客户群的整个范围。</p><p>（文档链接将随后提供。）</p> | | 2026年9月22日 |
| **每小时警报**<br/>&#x200B;您现在可以将警报的时间粒度设置为“每小时”。<p>每小时警报适用于在给定小时内到达的数据。 如果数据的滞后时间超过一小时，则较长的粒度可确保警报评估完整的数据。 如果您不确定数据需要多长时间才能到达，请咨询数据工程师。</p>p>（要遵循的文档链接。）</p> | | 2026年9月 |
| **警报投放严格遵循配置的延迟**<br/>&#x200B;现在，无论指定事件范围的数据已完成还是仍在接收数据，警报均会在您设置的延迟窗口的末尾投放。 延迟时段之后到达的任何数据都不会包含在警报中。<p>以前，警报包括后台处理检查，用于等待迟到的数据，即使这意味着警报在配置的延迟时段后发送。</p>p>（要遵循的文档链接。）</p> | | 2026年9月 |
| **Adobe Brand Visibility集成**<br/>&#x200B;将Adobe Brand Visibility与贵组织的Customer Journey Analytics数据连接起来，以便您可以衡量AI驱动的发现如何转化为真正的网站参与度和业务成果。<p>（文档链接将随后提供。）</p> | | 2026年9月 |
| **CX Enterprise Coworker中的升级和实施技能**<br>&#x200B;同事将获得新技能。 这些技能有助于使Customer Journey Analytics的升级和实施更加顺畅、轻松：<ul><li>**实施指南技能**：生成量身定制的升级或实施步骤和建议列表。 然后，可以使用预定义的行动手册将升级和实施指导转化为同事项目。</li><li>**智能升级和实施核对清单技能**：使用同事项目根据定制的升级或实施核对清单管理和跟踪实施进度，维护项目状态，跨团队协作，分配任务，并在需要时引入批准审核。</li><li>**数据验证技能**：验证您的实施配置正确且符合最佳实践。</li></ul><p>（文档链接随后提供。）</p> | | 2026年9月30日 |

### Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-487374、AN-487119、AN-468907、AN-468810、AN-468363、AN-468096、AN-467414、AN-466986、AN-466982、AN-465073、AN-463571、AN-462373、AN-492801、AN-488821、AN-488452、AN-486517、AN-478930、AN-468325
**组件**：
**连接**： AN-451458、AN-365942
**Content Analytics**：
**引导式分析**： AN-485600
**导出**： AN-489161、AN-467131、AN-464746、AN-469034、AN-447252、AN-437803、AN-394444
**数据视图**： AN-478732、AN-468836、AN-467851、AN-487651、AN-423592
**数据摄取**： AN-489829、AN-489722、AN-469451、AN-467436、AN-467049、AN-466087、AN-465049、AN-463524、AN-457433、AN-490288、AN-487500、AN-390916、AN-342311
**实施**：
**Report Builder**： AN-487486、AN-478944、AN-470036、AN-468589、AN-468436、AN-456747、AN-456700、AN-442695、AN-492330、AN-490564、AN-468293、AN-460921
**报告**： AN-479145、AN-469095、AN-468070、AN-467786、AN-456684、AN-465257、AN-422685、AN-406114、AN-356706、AN-322733
**分段**： AN-486561， AN-278260
**计划报告**： AN-479157
**共享的量度和维度**：
**受众分析**： AN-468237、AN-462553
**Other**： AN-469601、AN-462817、AN-362308、AN-349757、AN-326432、AN-326345、AN-324341、AN-309317

## 延迟的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体服务内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是计划数据上传支持的实时内容示例：</p><ul><li>FAST（免费广告支持的电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>有关详细信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)。</p> | 2025 年 10 月 29 日 | 待定<p>（原计划于2025年10月29日）</p> |

>[!MORELIKETHIS]
>
>* [以前的2026年Customer Journey Analytics发行说明](/help/release-notes/2026.md)
>* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
>* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
>* [CX Enterprise发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
>* [Customer Journey Analytics文档更新](/help/release-notes/doc-changes.md)

