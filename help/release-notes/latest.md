---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 8315bf705b576d597e346d17ff3998c336174361
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 95%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2024 年 6 月）

**上次更新时间**：2024 年 6 月 18 日

这些发行说明涵盖 2024 年 6 月 6 日至 2024 年 7 月的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Customer Journey Analytics 的 AI 助手** | 允许您在 Customer Journey Analytics UI 中提出自然语言问题，并根据 Customer Journey Analytics 文档获取答案。[了解详情](/help/ai-assistant.md) | | 2024 年 6 月 6 日 |
| **基于图形的拼合** | 通过基于图表的拼合，您可以使用Experience Platform身份服务中的身份图通过以下方式更好地查看客户历程：<ul><li>连接具有不同标识符的数据集，无需提取、转换和加载额外数据以反映单个标识符。</li><li>通过跨数据集共享标识，提高单个数据集中首选或黄金标识的覆盖率。</li><li>将 Real-Time Customer Data Platform 和 Journey Optimizer 中创建的轮廓与 Customer Journey Analytics 中的人员进行对齐。</li></ul>[了解详情](/help/stitching/overview.md) |  | 2024 年 6 月 28 日 |
| **个人到帐户的 B2B 架构转换** | 要在 B2B 数据（包括帐户、机会、营销列表和营销活动）上支持基于人的查找，您可以转换 B2B 查找数据集。此转换仅适用于包含以下类别的 B2B 查找模式数据的数据集：<ul><li>XDM 业务帐户人员关系</li><li>XDM 业务机会人员关系</li><li>XDM 商业营销列表成员</li><li>XDM 商业营销活动成员</li></ul>[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-connections/transform-datasets-b2b-lookups) |  | 2024 年 6 月 5 日 |
| **派生字段 - 数学函数** | 允许您在数据视图中执行简单的数学运算符来回答有关用户的问题。例如，您可以将产品、保修和运输收入结合起来。[了解详情](/help/data-views/derived-fields/derived-fields.md#math)</p> | | 2024 年 6 月 5 日 |
| **派生字段：下一个或上一个函数** | 允许您查看下一个或上一个值。例如，在所选营销渠道之前，用户与哪些营销渠道进行了互动？或者，在所选页面之前或之后，用户与哪个页面进行了互动？在店内访问之前，最受欢迎的渠道用户与什么进行交互？ [了解详情](/help/data-views/derived-fields/derived-fields.md#next-or-previous)</p> | | 2024 年 6 月 12 日 |
| **派生字段 — 摘要函数** | 允许在事件、会话和用户级别对量度或维度应用聚合类型函数。[了解详情](/help/data-views/derived-fields/derived-fields.md#summarize) | | 2024 年 6 月 26 日 |
| **派生字段：重复数据删除函数** | 有助于防止重复计算某个值。可以在用户或会话级别或基于维度的唯一值应用此函数。（文档链接见下文） |  | 2024年7月10日 |
| **数据摄取优先级和延迟** | 现在，无论数据是 24 小时、48 小时还是 7 天前的，您都可以在 90 分钟 (SLT) 内将事件数据摄取到 Customer Journey Analytics 中。请注意，此功能根据贵公司购买的 SKU 包而有所不同：<ul><li>CJA 优先输入基本版：在 90 分钟 SLT 处理时间内处理 24 小时前的数据（适用于 CJA Foundation 和 CJA Select）</li><li>CJA 优先摄取中级版：在 90 分钟 SLT 处理时间内处理 72 小时前的数据（适用于 CJA Prime）</li><li>CJA 优先摄取高级版：在 90 分钟 SLT 处理时间内处理 1 周前的数据（适用于 CJA Ultimate）</li></ul> |  | 2024 年 6 月 12 日 |
| **共享用于导出和导入的账户和位置** | 用户现在可以将他们创建的帐户和位置提供给其组织内的所有用户。只有帐户和位置所有者以及系统管理员可以编辑和删除帐户和位置。以前，帐户和位置只能由创建它们的用户使用。当用户[配置云导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)以及[配置云导出位置时，这些设置适用](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)。 | 2024 年 6 月 12 日 | 2024年7月中 |
| **在下拉筛选条件中选择多个字段** | 当下拉筛选条件中添加多个字段时，用户现在可以一次选择多个字段。面板经过过滤，可包含任何选定的字段。 <p>以前，用户在下拉筛选条件中一次只能选择一个字段。</p><p>右键单击下拉过滤器时，要求在下拉过滤器中进行选择的选项已移至菜单中。</p><p>以前，用户可以在下拉菜单中单击“无过滤器”选项旁边的 (x) 符号。</p><p>有关详细信息，请参阅[面板概述](/help/analysis-workspace/c-panels/panels.md)中的[静态下拉过滤器](/help/analysis-workspace/c-panels/panels.md#static-drop-down-filters)。</p> |  | 2024 年 6 月 19 日 |
| **Workspace 项目目录** | 现在可以为项目提供新的目录。目录提供了链接，使用户能够快速在项目内的面板和可视化内容之间移动。 <p>所有项目的左侧边栏中均可查看目录。</p><p>有关详细信息，请参阅[项目目录](/help/analysis-workspace/build-workspace-project/project-table-of-contents.md)。 |  | 2024 年 6 月 19 日 |
| **为自由格式表中的维度项目创建超链接** | 您可以为一个或多个维度项目创建超链接，使其在 Analysis Workspace 中的自由格式表中可点击。 <p>您可以为具有 URL 值的维度项目创建超链接，也可以为具有非 URL 值的维度项目创建自定义 URL。</p><p>您可以使用变量为多个维度项目创建动态自定义 URL。变量可以引用维度项目的值，也可以引用细分维度。</p><p>有关详细信息，请参阅[在自由格式表中为维度创建超链接](/help/analysis-workspace/visualizations/freeform-table/freeform-table-hyperlinks.md)。</p> |  | 2024 年 6 月 19 日 |
| **在 Adobe Journey Optimizer 中使用 Customer Journey Analytics 数据视图** | Customer Journey Analytics 中的新配置选项允许您指定一个 Customer Journey Analytics 数据视图，以便与 Adobe Journey Optimizer 一起使用，而无需手动配置。 <p>有关如何启用此配置选项的更多信息，请参阅[创建或编辑数据视图](/help/data-views/create-dataview.md)中的[兼容性](/help/data-views/create-dataview.md#compatibility)部分。</p><p>之前，在 Customer Journey Analytics 中查看 Journey Optimizer 数据时，您必须手动配置连接和数据视图。</p> |  | 2024 年 6 月 19 日 |
| **Audiences 已发布到 Experience Platform 中的新“Audiences”部分** | 从 Customer Journey Analytics 中发布的受众现在可以在 Adobe Experience Platform 的新“受众”部分中找到。<p>此前，从 Customer Journey Analytics 发布的受众可在 Experience Platform 的“细分”部分下找到。</p><p>此改进具有以下优点：</p><ul><li>受众出现在 Experience Platform 前不再有 1 小时的延迟；它们在发布后几秒钟即可使用。</li><li>可以使用 Experience Platform 中“来源”列对受众进行排序，该列显示了最初发布受众的应用程序。</li><li>Experience Platform 中的筛选和排序选项使您能够更快地找到相关受众。</li></ul> <p>（文档链接见下文）</p> |  | 2024 年 7 月 14 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-345454; AN-349816; AN-349905; AN-350617

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
