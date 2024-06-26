---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8315bf705b576d597e346d17ff3998c336174361
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 50%

---

# 当前Adobe Customer Journey Analytics发行说明（2024年6月）

**上次更新**：2024年6月18日

这些发行说明涵盖2024年6月6日至2024年7月的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics 的 AI 助手** | 允许您在 Customer Journey Analytics UI 中提出自然语言问题，并根据 Customer Journey Analytics 文档获取答案。[了解详情](/help/ai-assistant.md) | | 2024 年 6 月 6 日 |
| **基于图形的拼合** | 通过基于图表的拼合，您可以使用Experience Platform身份服务中的身份图通过以下方式更好地查看客户历程：<ul><li>使用不同的标识符连接数据集，而不必提取、转换和加载额外的数据以反映单个标识符。</li><li>通过跨数据集共享身份，提高单个数据集的首选或黄金身份覆盖率。</li><li>将Real-time Customer Data Platform和Journey Optimizer中创建的用户档案与Customer Journey Analytics中的人员保持一致。</li></ul>[了解详情](/help/stitching/overview.md) |  | 2024年6月28日 |
| **个人到帐户的 B2B 架构转换** | 为了支持对B2B数据（包括客户、机会、营销列表和营销活动）进行基于人员的查找，您可以转换B2B查找数据集。 此转换仅适用于包含B2B查找架构数据的数据集，它基于以下类：<ul><li>XDM 业务帐户人员关系</li><li>XDM 业务机会人员关系</li><li>XDM 商业营销列表成员</li><li>XDM 商业营销活动成员</li></ul>[了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 2024 年 6 月 5 日 |
| **派生字段 - 数学函数** | 允许您在数据视图中执行简单的数学运算符来回答有关用户的问题。例如，您可以将产品、保修和运输收入结合起来。[了解详情](/help/data-views/derived-fields/derived-fields.md#math)</p> | | 2024 年 6 月 5 日 |
| **派生字段 — 下一个或上一个函数** | 让您查看下一个或上一个值是什么。 例如，在选定营销渠道之前，用户与之交互的上一个营销渠道是什么？ 或者，在选定页面之前或之后，用户与哪个页面进行了交互？ 在店内访问之前，最受欢迎的渠道用户与什么进行交互？ [了解详情](/help/data-views/derived-fields/derived-fields.md#next-or-previous)</p> | | 2024 年 6 月 12 日 |
| **派生字段 — 摘要函数** | 提供在事件、会话和用户级别将聚合类型函数应用于量度或维度的功能。 [了解详情](/help/data-views/derived-fields/derived-fields.md#summarize) | | 2024年6月26日 |
| **派生字段 — 重复数据删除函数** | 有助于防止重复计算某个值。 可以在用户或会话级别应用，也可以根据维度的唯一值应用。 （文档链接见下文） |  | 2024年7月10日 |
| **摄取优先级和延迟** | 现在，无论事件数据是在24小时、48小时还是7天之前，您都可以在90分钟(SLT)内以Customer Journey Analytics摄取该数据。 请注意，此功能因您公司购买的SKU软件包而异：<ul><li>CJA优先级摄取基本：90分钟SLT处理内24小时旧数据（可用于CJA Foundation和CJA Select）</li><li>CJA优先摄取中间：90分钟SLT处理内72小时旧数据（适用于CJA Prime）</li><li>CJA优先级摄取高级：90分钟SLT处理内1周前的数据（适用于CJA Ultimate）</li></ul> |  | 2024 年 6 月 12 日 |
| **共享用于导出和导入的账户和位置** | 用户现在可以将他们创建的帐户和位置提供给其组织内的所有用户。只有帐户和位置所有者和系统管理员可以编辑和删除帐户和位置。 以前，帐户和位置只能由创建它们的用户使用。 当用户[配置云导出帐户](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)以及[配置云导出位置时，这些设置适用](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)。 | 2024 年 6 月 12 日 | 2024年7月中 |
| **在下拉筛选条件中选择多个字段** | 当下拉筛选条件中添加多个字段时，用户现在可以一次选择多个字段。面板经过过滤，可包含任何选定的字段。 <p>以前，用户在下拉筛选条件中一次只能选择一个字段。</p><p>右键单击下拉筛选器时，需要在下拉筛选器中进行选择的选项（已移至菜单）。</p><p>以前，用户可以单击下拉菜单中“无过滤器”选项旁边的(x)。</p><p>有关更多信息，请参阅 [静态下拉过滤器](/help/analysis-workspace/c-panels/panels.md#static-drop-down-filters) 在 [面板概述](/help/analysis-workspace/c-panels/panels.md).</p> |  | 2024 年 6 月 19 日 |
| **Workspace 项目目录** | 现在可以为项目提供新的目录。目录提供的链接使用户能够在项目中的面板和可视化图表之间快速移动。 <p>该目录在所有项目的左边栏中均可用。</p><p>有关详细信息，请参阅[项目目录](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)。 |  | 2024 年 6 月 19 日 |
| **为自由格式表中的维度项目创建超链接** | 您可以为一个或多个维度项目创建超链接，使其在 Analysis Workspace 中的自由格式表中可点击。 <p>您可以为具有 URL 值的维度项目创建超链接，也可以为具有非 URL 值的维度项目创建自定义 URL。</p><p>您可以使用变量为多个维度项目创建动态自定义 URL。变量可以引用维度项目的值，也可以引用细分维度。</p><p>有关详细信息，请参阅[为自由格式表中的维度创建超链接](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。</p> |  | 2024 年 6 月 19 日 |
| **在Adobe Journey Optimizer中使用Customer Journey Analytics数据视图** | Customer Journey Analytics中新增的配置选项允许您指定要与Adobe Journey Optimizer一起使用的Customer Journey Analytics数据视图，而无需手动配置。 <p>有关如何启用此配置选项的信息，请参见 [兼容性](/help/data-views/create-dataview.md#compatibility) 中的部分 [创建或编辑数据视图](/help/data-views/create-dataview.md).</p><p>以前，在Customer Journey Analytics中查看Journey Optimizer数据时，您必须手动配置连接和数据视图。</p> |  | 2024 年 6 月 19 日 |
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
