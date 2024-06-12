---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: e71fe4bc1b854dcb904dfbfd770233cdadd5c8eb
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 38%

---

# 当前Adobe Customer Journey Analytics发行说明（2024年6月）

**上次更新**：2024年6月12日

这些发行说明涵盖2024年6月6日至2024年7月的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics 的 AI 助手** | 允许您在 Customer Journey Analytics UI 中提出自然语言问题，并根据 Customer Journey Analytics 文档获取答案。[了解详情](/help/ai-assistant.md) | | 2024 年 6 月 6 日 |
| **基于图形的拼接：使用UIS图形导出进行拼接** | 通过基于图的拼合，我们使用身份图通过以下方式更好地查看客户历程：<ul><li>使用不同的标识符连接数据集，而不必ETL数据以反映单个标识符。</li><li>通过跨数据集共享身份，提高单个数据集的首选或黄金身份覆盖率。</li><li>将AdobeReal-time CDP和Adobe历程优化器中创建的配置文件与Adobe Customer Journey Analytics中的人员保持一致。</li></ul>（文档链接见下文） |  | 2024年6月28日 |
| **个人到帐户的 B2B 架构转换** | 为了支持对B2B数据（包括客户、机会、营销列表和营销活动）进行基于人员的查找，我们现在提供了对B2B查找数据集的转换。 此转换仅适用于包含B2B查找架构数据的数据集，它基于以下类：<ul><li>XDM 业务帐户人员关系</li><li>XDM 业务机会人员关系</li><li>XDM 商业营销列表成员</li><li>XDM 商业营销活动成员</li></ul>[了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 2024 年 6 月 5 日 |
| **派生字段 - 数学函数** | 允许您在数据视图中执行简单的数学运算符来回答有关用户的问题。例如，您可以将产品、保修和运输收入结合起来。 <p>[了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#math)</p> | | 2024 年 6 月 5 日 |
| **派生字段 — 派生字段 — 下一个或上一个函数** | 让您查看下一个或上一个值是什么。 例如，在选定营销渠道之前，用户与之交互的上一个营销渠道是什么？ 或者，在选定页面之前或之后，用户与哪个页面进行了交互？ 在店内访问之前，最受欢迎的渠道用户与什么进行交互？ [了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/derived-fields#next-or-previous) | | 2024 年 6 月 12 日 |
| **派生字段 — 摘要函数** | 提供在事件、会话和用户级别将聚合类型函数应用于量度或维度的功能。 （文档链接见下文） | | 2024年6月26日 |
| **派生字段 — 高级重复数据删除功能** | 有助于防止重复计算某个值。 可以在用户或会话级别应用，也可以根据维度的唯一值应用。 （文档链接见下文） |  | 2024年6月26日 |
| **摄取优先级和延迟** | 现在，无论事件数据是在24小时、48小时还是7天之前，您都可以在90分钟(SLT)内以Customer Journey Analytics摄取该数据。 请注意，此功能因您公司购买的SKU软件包而异：<ul><li>CJA优先级摄取基本：90分钟SLT处理内24小时旧数据（可用于CJA Foundation和CJA Select）</li><li>CJA优先摄取中间：90分钟SLT处理内72小时旧数据（适用于CJA Prime）</li><li>CJA优先级摄取高级：90分钟SLT处理内1周前的数据（适用于CJA Ultimate）</li></ul> |  | 2024 年 6 月 12 日 |
| **共享用于导出和导入的账户和位置** | 用户现在可以将他们创建的帐户和位置提供给其组织内的所有用户。只有帐户和位置所有者和系统管理员可以编辑和删除帐户和位置。 以前，帐户和位置只能由创建它们的用户使用。 当用户[配置云导出帐户](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)以及[配置云导出位置时，这些设置适用](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)。 | 2024 年 6 月 12 日 | 2024年6月18日 |
| **在自由格式表的下拉菜单中选择多个可用过滤器** | 当多个过滤器作为下拉菜单添加到自由格式表时，自由格式表的用户现在可以同时选择多个过滤器。 自由格式表将进行筛选，以包含任何选定的过滤器。 <p>以前，用户在过滤器下拉菜单中一次只能选择一个过滤器。</p><p>（文档链接随后提供。）<!--For more information, see "Add filters to a project" in "Use components in Analysis Workspace."--> |  | 2024年6月19日 |
| **工作区项目的目录** | 现在有新的目录可用于项目。 目录提供了使用户能够快速跳转到项目中的面板和可视化图表的链接。 <p>可以为单个项目或给定用户的所有项目启用目录。</p><p>（文档链接随后提供。）<!--For more information, see "Display the project table of contents" in "Create projects".--> |  | 2024年6月19日 |
| **在自由格式表中为维度项目创建超链接** | 您可以为一个或多个维度项目创建超链接，以使它们可在Analysis Workspace的自由格式表中点击。 <p>您可以为具有URL值的维度项创建超链接，也可以为具有非URL值的维度项创建自定义URL。</p><p>您可以使用变量为多个维度项目创建动态自定义URL。 变量可以引用维度项的值，也可以引用划分维度。</p><p>（文档链接随后提供。）<!--For more information, see "Add hyperlinks to dimensions in a freeform table."--></p> |  | 2024年6月19日 |
| **Audiences 已发布到 Experience Platform 中的新“Audiences”部分** | 从 Customer Journey Analytics 中发布的受众现在可以在 Adobe Experience Platform 的新“受众”部分中找到。<p>此前，从 Customer Journey Analytics 发布的受众可在 Experience Platform 的“细分”部分下找到。</p><p>此改进具有以下优点：</p><ul><li>受众出现在 Experience Platform 前不再有 1 小时的延迟；它们在发布后几秒钟即可使用。</li><li>可以使用 Experience Platform 中“来源”列对受众进行排序，该列显示了最初发布受众的应用程序。</li><li>Experience Platform 中的筛选和排序选项使您能够更快地找到相关受众。</li></ul> <p>（文档链接见下文）</p> |  | 2024年7月14日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-345454； AN-349816； AN-349905； AN-350617

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

{style="table-layout:auto"}

## 相关资源

* [之前的 2024 Customer Journey Analytics 发行说明](/help/release-notes/2024.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
