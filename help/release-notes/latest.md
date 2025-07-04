---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: cbe5f3894a01f662a6ebe9c380583d0a039863fd
workflow-type: tm+mt
source-wordcount: '647'
ht-degree: 86%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2025 年 6 月）

**上次更新时间**：2025 年 6 月 18 日


这些发行说明涵盖 2025 年 6 月 2 日至 7 月 15 日的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Analysis Workspace 左侧面板不再在鼠标悬停时打开和关闭** | Analysis Workspace 中的左侧面板用于将组件、面板和可视化图表等元素添加到您的项目中。将鼠标悬停在最左侧的一个图标上以临时打开左侧面板，这个选项不再可用。现在，只需单击其中一个图标即可保持面板打开，然后单击相同的图标可将其关闭。 |  | 2025 年 6 月 2 日 <p>（原计划于 2025 年 5 月 29 日发布）</p> |
| **Customer Journey Analytics B2B Edition** | Customer Journey Analytics B2B Edition 提供有助于推动收入增长的可操作的帐户洞察，帮助 B2B 公司协调其营销活动、销售和产品团队。帐户是数据模型的中心，因此所有分析都集中在帐户历程上。在基于人员及时间的事件之上添加一层新实体（帐户、机会和购买群组），可以创建 B2B 营销活动和收入生命周期的完整图景。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition) |  | 2025 年 6 月 18 日 |
| **在Report Builder中支持安全云目标** | 您现在可以将报表从Report Builder导出到以下云存储目标：<ul><li>Amazon S3 Role ARN</li><li>Google Cloud Platform</li><li>Azure SAS</li><li>Azure RBAC</li></ul><p>以前，您可以通过电子邮件将工作簿与其他用户共享，但无法将报表从Report Builder导出到云目标。</p><p>有关详细信息，请参阅[通过导出到云目标来计划工作簿](/help/report-builder/report-builder-export.md)。</p> |  | 2025 年 6 月 19 日（原定 2025 年 6 月 18 日） |
| **新预览体验** | 现在，创建区段或配置数据视图设置时使用的预览面板使用的是水平条形图可视化图表，而不是圆环图可视化图表。 |  | 2025 年 6 月 18 日 |
| **修改了归因模型对话框** | 您现在可以在归因模型对话框中分别定义容器和时段。 |  | 18,2025 年 6 月 |
| **连接图** | 全新的[连接映射界面](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-connections/create-connection#connection-map)现已推出，可用于以可视化方式展示您的连接配置。 |  | 2025 年 6 月 18 日 |
| **在 Analysis Workspace 项目中添加和查看评论** | Analysis Workspace 中新增的[评论功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/build-workspace-project/comment-projects)可让您在 Analysis Workspace 项目的上下文中分享见解和提出问题。这可以简化有关数据的讨论，使对话保持在正在讨论的数据范围内。您可以 <ul><li>对任何您有权访问的 Analysis Workspace 项目进行评论</li><li>对可视化图表中的特定点进行评论，也可以对项目进行一般性评论</li><li>标记其他用户，将您的评论告知他们</li><li>管理现有评论（编辑、固定、解决等）</li></ul>Customer Journey Analytics 管理员可以[在组织级别禁用评论功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/user-preferences#ims-organization-preferences)。项目所有者可以[在项目级别禁用评论功能](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-workspace/build-workspace-project/create-projects)。 | 2025 年 6 月 25 日 | 2025年7月11日 <p>（原计划于 2025 年 5 月 29 日发布）</p> |
| **支持 Chrome 预渲染** | 控制 Chrome 预渲染页面时数据收集库的行为方式。（文档链接见下文） |  | 2025 年 6 月 30 日 |

## Customer Journey Analytics 中的修复

**警报**：AN-379554
**Analysis Workspace**：AN-339607；AN-379222；AN-381138；AN-383291
**B2B**：AN-376028
**Tableau 的 BI 扩展**：AN-377488
**组件**：AN-376174
**数据视图**：AN-379011
**导出位置**：AN-382191
**完整表导出**：AN-375646；AN-376986；AN-380355；AN-381310
**历程画布**：AN-375865；AN-378011
**Report Builder**：AN-369786；AN-371395；AN-372809
**报告**：AN-372615；AN-378578；


## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

## 相关资产

* [之前的 2025 Customer Journey Analytics 发行说明](/help/release-notes/2025.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
