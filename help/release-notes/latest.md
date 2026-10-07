---
title: 当前的Customer Journey Analytics发行说明
description: 查看最新的Customer Journey Analytics发行说明，包括当前时期的新增功能、修复的问题和延迟的版本。
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
TQID: 'https://experienceleague.adobe.com/EQKhna8E33DddZQGWe3ASBKMY9r-UsfuUcJg7DMwH0w'
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
    internal-label: Customer Journey Analytics
feature_v2:
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
    internal-label: Analysis Workspace
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
    internal-label: Components
  - id: d76b9e53-27fb-4597-933f-419cc0dd46db
    internal-label: Administration
subfeature_v2:
  - id: ad333ea6-e90d-4c8f-8d61-9f8690784d6f
    internal-label: Templates
  - id: ad5685a0-8296-4a0c-814c-658c10b4af12
    internal-label: Content Analytics
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
    internal-label: Metrics
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
    internal-label: Segments
  - id: bcaa1b08-8269-4ff3-a0c2-f599783b6107
    internal-label: Filters
  - id: cc092ab1-90ba-4bbc-b4c6-6249d87daf5c
    internal-label: Audiences
  - id: d1d3b429-e0a8-4e2f-af0a-a48d23e366b7
    internal-label: Connections
  - id: d3c978ee-1ff0-4475-968a-721e2dd99ef1
    internal-label: Freeform tables
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
    internal-label: Dimensions
  - id: ef46ac31-f951-48d6-bae5-51c52ab47fb8
    internal-label: Exports
  - id: a8e39571-4463-4aa3-8b3f-4e2341ecf3b3
    internal-label: Release notes
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
    internal-label: Insights
source-git-commit: 0a83f4d08806b4d9b97265989f9d687011b232c3
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 28%
---
# 当前Customer Journey Analytics发行说明（2026年10月）

**上次更新时间**：2026年10月7日

这些发行说明涵盖2026年10月发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。 因此，这些发行说明每月更新几次。 请定期检查。

## 新增功能或更新后的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **Customer Journey Analytics MCP服务器的只读权限**<br/>&#x200B;管理员现在可以授予用户对Customer Journey Analytics MCP服务器的只读访问权限。 新的[!UICONTROL MCP只读]权限项允许用户访问所有只读工具，而不允许用户创建项目、区段或计算量度。<p>现有的[!UICONTROL MCP访问]权限项已重命名为[!UICONTROL MCP完全访问]。 具有此权限的用户可保留对所有工具的访问权限，包括创建、更改或删除组件的工具。</p><p>有关详细信息，请参阅[Customer Journey Analytics MCP服务器](https://developer.adobe.com/analytics-mcp/docs/cja/)。</p> | | 2026年10月6日 |
| **在Analysis Workspace中使用对话见解分析LLM客户体验**<br/> Customer Journey Analytics现在将非结构化聊天数据引入Analysis Workspace，允许您报告资产中利用LLM进行的浏览和购买体验。<p>利用此功能，您可以：</p><ul><li>通过Web SDK从对话代理（贵组织的自定义代理或Adobe Brand Concierge）收集提示、响应和代理元数据。</li><li>分析意图、语气和情绪，以便您了解客户提出的问题、您的座席如何回应以及客户对其交互的感受。</li><li>使用现有架构、数据集和数据视图进行大规模分析，然后在Analysis Workspace中显示见解。</li><li>通过将代理互动与更广泛的客户历程联系起来，将对话与成果联系起来，以便您衡量对转化、参与度等工作的实际影响。</li></ul><p>以前，由LLM提供支持的体验难以测量，并且几乎无法连接到您现有的客户历程。</p><p>有关详细信息，请参阅[对话分析](/help/conversation-insights/overview.md)。</p> | | 2026年10月8<p>（原计划于2026年9月22日）</p> |
| **自动生成组件描述** <br/>您现在可以自动生成维度、量度、计算量度、区段和日期范围的描述。 这使得Workspace用户能够了解要使用的组件，尤其是在具有大型组件库的组织中。 <p>您可以为单个组件生成描述，或同时为多个组件生成描述。</p> <p>（文档链接见下文。）<!--For more information, see [Automatically generate descriptions](/help/components/add-component-descriptions.md#automatically-generate-descriptions).--></p> | | 2026年10月28日 |
| **Adobe Brand Visibility集成**<br/>&#x200B;将Adobe Brand Visibility与贵组织的Customer Journey Analytics数据连接起来，以便您可以衡量AI驱动的发现如何转化为真正的网站参与度和业务成果。<p>（文档链接将随后提供。）</p> | | 2026年10 |


### Customer Journey Analytics 中的修复

**Analysis Workspace**： AN-495340、AN-494789、AN-493307、AN-468900
**组件**： AN-492523
**连接**： AN-492236
**Content Analytics**：
**引导式分析**： AN-495592
**导出**： AN-495077、AN-494337、AN-486563、AN-469919、AN-462560、AN-462372
**数据视图**： AN-492093、AN-467770、AN-455367、AN-444467
**数据摄取**： AN-496439、AN-495339、AN-493456、AN-491984、AN-490515、AN-490479、AN-470065
**实施**：
**Report Builder**： AN-496602、AN-494224、AN-493737、AN-493508、AN-493505、AN-492806、AN-468981、AN-454376
**报告**： AN-495661、AN-493562、AN-487058、AN-478768
**分段**：
**计划报告**： AN-491103、AN-468049
**共享量度和维度**： AN-493722
**受众分析**： AN-469101
**其他**： AN-493865

## 延迟的功能

| 功能和描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| -----------|-----------|-----------|
| **总人口报告**<br/>&#x200B;您现在可以分析和报告在Customer Journey Analytics连接中存在的配置文件和查找数据集中定义的实体。 这种分析和报告不仅仅是来自事件数据集的基于时间的事件系列。 <p>此功能支持新类别的查询、量度和受众定义，它们反映了企业客户群的整个范围。</p><p>（文档链接将随后提供。）</p> | | 待定<p>（原计划于2026年9月22日）</p> |
| **流媒体服务：支持计划数据** <br/>您现在可以上传过去直播流媒体服务内容的计划数据，以便更轻松、更准确地跟踪观看人数。<p>以下是计划数据上传支持的实时内容示例：</p><ul><li>FAST（免费广告支持电视）平台</li><li>本地流</li><li>直播体育赛事</li></ul><p>上传计划数据允许您跟踪在上传文件中指定的时间内运行的各个节目的观看人数数据。 您甚至可以收集特定主题或节目片段的观看人数数据。</p><p>无论您如何实现流媒体收集，这些功能都是可用的。</p><p>以前，在分析直播内容时很难准确地将特定场次与特定节目联系起来，也不可能将特定场次与单个主题或节目片段联系起来。</p><p>有关详细信息，请参阅[上传计划数据以跟踪实时内容](https://experienceleague.adobe.com/zh-hans/docs/media-analytics/using/media-use-cases/track-schedule-data)。</p> | 2025 年 10 月 29 日 | 待定<p>（原计划于2025年10月29日）</p> |

>[!MORELIKETHIS]
>
>* [以前的2026年Customer Journey Analytics发行说明](/help/release-notes/2026.md)
>* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
>* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
>* [CX Enterprise发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
>* [Customer Journey Analytics文档更新](/help/release-notes/doc-changes.md)

