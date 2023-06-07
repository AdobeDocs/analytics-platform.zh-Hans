---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 86b411ac28aaa78914c6f105af2716e1b3a4150c
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 67%

---

# 当前的 Customer Journey Analytics (CJA) 发行说明（2023 年 6 月）

**上次更新时间**：2023 年 6 月 6 日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 版本亮点 {#highlights}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **智能字幕** | 利用的自然语言摘要丰富用户的叙事能力 [!UICONTROL 折线图] 可视化图表。 [了解详情](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023 年 5 月 17 日 | 2023 年 6 月 1 日 |
| **用链接共享项目（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置 Adobe Analytics 的人员共享。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans#share-public-link) <p>默认启用此功能，而系统管理员可禁用此功能。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=zh-Hans#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 6 日 |
| **派生字段** | 这代表派生字段的初始版本。通过派生字段和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。可进一步将该派生字段定义为数据视图中的组件（量度或维度），然后将该派生字段用作 Workspace 中的组件。<p>此版本支持营销渠道模板和以下功能：</p><ul><li>拼接</li><li>Case When</li><li>查找和替换</li><li>查询</li><li>URL 解析</li></ul> <p>[了解详情](/help/data-views/derived-fields/derived-fields.md)</p> | 2023 年 5 月 10 日 | 2023 年 6 月 21 日 |
| **PowerBI和Tableau对CJA数据视图的访问** | Customer Journey Analytics(CJA) SQL Connector允许SQL访问您在CJA中定义的数据视图。 更熟悉Power BI、Tableau或其他商业智能和可视化工具的数据工程师和分析人员现在可以根据CJA用户用于其Analysis Workspace项目的相同数据视图创建报告和仪表板。 [了解详情](/help/data-views/sql-connector.md) |  | 2023 年 6 月 30 日 |
| **Experience Edge地理查找** | 为您的数据流启用Experience Edge地理查找后，您将能够使用CJA中的地理位置数据构建报告。 |  | 2023 年 6 月 30 日 |
| **扩展了对配置文件和查找数据的查找支持** | 您不仅可以将查找数据集添加到事件数据集，还可以将查找数据集添加到配置文件和查找数据集。 | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **支持货币兑换** | CJA将支持货币兑换，作为格式化数据视图中的量度组件的一部分。 | 2023 年 6 月 21 日 | 2023 年 7 月 19 日 |

{style="table-layout:auto"}

## 其他新增功能或更新 {#other-new}

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Journey Optimizer数据视图** | CJA管理员有权访问CJA中一些名为“AJO数据视图(Sandbox-name)”的额外数据视图。 这些数据视图用于为Adobe Journey Optimizer (AJO)中的报表提供支持。 它们还可用于在CJA中对AJO活动进行更深入的分析。 [了解详情](https://experienceleague.adobe.com/docs/journey-optimizer/using/campaigns/content-experiment/reporting-configuration.html)。 |  | 2023 年 5 月 25 日 |
| **非生产沙盒的回填** | 在非生产沙盒中创建 Analytics 源连接器数据流时，非生产沙盒中的回填将限制为 3 个月。生产沙盒的时间将保持在 13 个月。 | 不适用 | 2023 年 4 月 26 日 |
| **用链接共享项目（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置 Adobe Analytics 的人员共享。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>默认启用此功能，而系统管理员可禁用此功能。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html?lang=en#ims-organization-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 6 日 |
| **更新了 Analytics 功能板应用程序（移动应用程序）的主屏幕** | 通过新近更新的主屏幕，可在一个合并的记分卡列表中查看您的所有记分卡。如果您可用一个登录名访问多个组织，则在一个列表中即可找到所有来自您这些组织的记分卡。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dashboards/executive.html#use-dashboards) | 不适用 | 2023 年 5 月 10 日 |
| **派生字段** | 这代表派生字段的初始版本。通过派生字段和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。可进一步将该派生字段定义为数据视图中的组件（量度或维度），然后将该派生字段用作 Workspace 中的组件。<p>此版本支持营销渠道模板和以下功能：</p><ul><li>拼接</li><li>Case When</li><li>查找和替换</li><li>查询</li><li>URL 解析</li></ul> <p>[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 2023 年 5 月 10 日 | 2023年8月2日 |
| **CJA Report Builder - 从单元格选择数据视图** | 通过此功能，用户可从单元格选择数据块的数据视图。如果创建一个工作簿，并有多个数据视图的数据构造相似，而您希望能够以不同的数据视图多次重用工作簿，则这样做很有帮助。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 不适用 | 2023 年 5 月 24 日 |
| **为 Analysis Workspace 中的组件排序** | <p>在 Analysis Workspace 中的左边栏或数据词典中查看组件时，现在有一个新的排序选项可用。可按“推荐”（最常用的那些组件）、“字母顺序”或“分类”（类型）为组件排序。</p><p>而以前只能搜索或过滤组件。[了解详情](/help/components/overview.md)</p> | 不适用 | 待定 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-318343； AN-319453

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | 不适用 | 不适用 |

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到AdobeIO OAuth服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用AdobeIO JWT凭据的Adobe Analytics API、CJA API和Livestream客户必须通过以下方式迁移到AdobeIO OAuth服务器到服务器凭据 **2025年1月1日**. 从2024年5月1日开始，AdobeIO不允许创建新的JWT凭据。 使用JWT的客户必须创建新的OAuth服务器到服务器凭据，或将其现有JWT凭据迁移到OAuth服务器到服务器凭据。 客户还必须更新其客户端应用程序才能使用新的OAuth服务器到服务器凭据。 <ul><li>[从服务帐户(JWT)凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的OAuth服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}

## 相关资源

* [以前的 2023 年 CJA 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
