---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7fdef4a33154f443722ad4625c83f91bea7e047d
workflow-type: tm+mt
source-wordcount: '1283'
ht-degree: 91%

---

# 当前的 Customer Journey Analytics (CJA) 发行说明（2023 年 6 月）

**上次更新日期**：2023 年 6 月 19 日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 版本亮点 {#highlights}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **智能题注** | 通过[!UICONTROL 折线图]可视化效果的自然语言概括，为用户提供更丰富多彩的叙事。[了解详情](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023 年 5 月 17 日 | 2023 年 6 月 1 日 |
| **用链接共享项目（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置 Adobe Analytics 的人员共享。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans#share-public-link) <p>默认启用此功能，而系统管理员可禁用此功能。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=zh-Hans#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 6 日 |
| **派生字段** | 这代表派生字段的初始版本。通过派生字段和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。您可以进一步将派生字段定义为数据视图中的组件（量度或维度），然后在工作区中将派生字段用作组件。<p>此版本支持营销渠道模板和以下功能：</p><ul><li>拼接</li><li>Case When</li><li>查找和替换</li><li>查询</li><li>URL 解析</li></ul> <p>[了解详情](/help/data-views/derived-fields/derived-fields.md)</p> | 2023 年 5 月 10 日 | 2023 年 6 月 14 日 |
| **PowerBI 和 Tableau 访问 CJA 数据视图** | 通过 Customer Journey Analytics (CJA) SQL Connector，SQL 可访问您在 CJA 中定义的数据视图。更熟悉 Power BI、Tableau 或其他商业智能和可视化工具的数据工程师和分析师现在可根据 CJA 用户用于其 Analysis Workspace 项目的相同数据视图创建报表和仪表板。[了解详情](/help/data-views/sql-connector.md) |  | 2023 年 6 月 30 日 |
| **Experience Edge 地理位置查询** | 为数据流启用 Experience Edge 地理位置查询后，即可使用 CJA 中的地理位置数据生成报表。 |  | 2023 年 6 月 30 日 |
| **将对查找的支持扩充至配置文件和查找数据** | 您将不仅可将查找数据集添加到事件数据集，还可将其添加到配置文件和查找数据集。 | 2023 年 6 月 28 日 | 2023 年 7 月 12 日 |
| **货币兑换支持** | 在数据视图中格式化量度组件时，支持货币转换。 [了解详情](../data-views/component-settings/format.md#currency) | 2023 年 6 月 7 日 | 2023 年 6 月 21 日 |

{style="table-layout:auto"}

## 其他新增功能或更新 {#other-new}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer 数据视图** | CJA 管理员有权访问 CJA 中某些额外的名为“AJO 数据视图（沙盒名称）”的数据视图。这些数据视图用于为 Adobe Journey Optimizer (AJO) 中的报表提供数据。它们还可用于对 CJA 中的 AJO 活动执行更深入的分析。[了解详情](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html)。 | | 2023 年 5 月 25 日 |
| **非生产沙盒的回填** | 在非生产沙盒中创建 Analytics 源连接器数据流时，非生产沙盒中的回填将限制为 3 个月。生产沙盒的时间将保持在 13 个月。 | 不适用 | 2023 年 4 月 26 日 |
| **用链接共享项目（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置 Adobe Analytics 的人员共享。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>默认启用此功能，而系统管理员可禁用此功能。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 6 日 |
| **更新了 Analytics 功能板应用程序（移动应用程序）的主屏幕** | 通过新近更新的主屏幕，可在一个合并的记分卡列表中查看您的所有记分卡。如果您可用一个登录名访问多个组织，则在一个列表中即可找到所有来自您这些组织的记分卡。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | 不适用 | 2023 年 5 月 10 日 |
| **CJA Report Builder - 从单元格选择数据视图** | 通过此功能，用户可从单元格选择数据块的数据视图。如果创建一个工作簿，并有多个数据视图的数据构造相似，而您希望能够以不同的数据视图多次重用工作簿，则这样做很有帮助。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 不适用 | 2023 年 5 月 24 日 |
| **CJA的更新学习页面** | Customer Journey Analytics登录页上的“学习”选项卡现在包含特定于CJA的内容，包括侧重于从Adobe Analytics过渡到CJA的内容。<p>“学习”选项卡上还提供了以下其他增强功能：</p><ul><li>改进了设计，其中在单个页面上展示更多学习内容并改进了导航</li><li>可根据经验级别（初学者、中级和高级）使学习内容个性化</li></ul><p>以前，CJA中的“学习”选项卡包含的信息与Adobe Analytics中的“学习”选项卡相同。</p> [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/landing.html?lang=en#navigate-learning) | 不适用 | 2023 年 6 月 30 日 |
| **为 Analysis Workspace 中的组件排序** | <p>在 Analysis Workspace 中的左边栏或数据词典中查看组件时，现在有一个新的排序选项可用。可按“推荐”（最常用的那些组件）、“字母顺序”或“分类”（类型）为组件排序。</p><p>而以前只能搜索或过滤组件。[了解详情](/help/components/overview.md)</p> | 不适用 | 2023 年 6 月 7 日 |
| **从自由格式表中删除包含动态维度的行** | 现在可在 Analysis Workspace 的自由格式表中使用 x 图标快速地删除包含动态维度的特定行。这样做时，将自动应用“始终排除项目”过滤规则。<p>而以前只有在“过滤器”对话框中手动创建规则才能删除包含动态维度的行。[了解详情](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **在面板中新增一个用于添加可视化效果的按钮** | Analysis Workspace 中每个面板的底部现在都有一个新按钮，通过它，可快速地添加可视化效果。 <p>而以前只有从左边栏拖动可视化效果、重复或复制现有的可视化效果或创建空白面板才能将可视化效果添加到面板。[了解详情](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **深层链接（移动应用程序）** | 使用户可发送记分卡的链接，而这些链接将引导用户直接进入应用程序中的记分卡项目。这样使得可更轻松地从不太熟悉技术的受众共享项目和提高参与度。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/create-scorecard.html#share-scorecards-using-a-shareable-link) | 不适用 | 2023 年 5 月 17 日 |
| **智能题注** | 通过[!UICONTROL 折线图]可视化效果的自然语言概括，为用户提供更丰富多彩的叙事。[了解详情](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023 年 5 月 17 日 | 2023 年 6 月 1 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-318343、AN-319453

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | 不适用 | 不适用 |

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 AdobeIO JWT 凭据的 Adobe Analytics API、CJA API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 AdobeIO OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，AdobeIO 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## 相关资源

* [以前的 2023 年 CJA 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
