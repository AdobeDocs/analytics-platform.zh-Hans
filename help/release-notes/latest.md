---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 7e6383bf94e10f6ab6f9db990f4ef3df0fb826d3
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 85%

---

# 当前 Customer Journey Analytics (CJA) 发行说明（2023 年 5 月）

**上次更新日期**：2023 年 5 月 8 日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 主要功能及更新

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **非生产沙盒的回填** | 在非生产沙盒中创建 Analytics 源连接器数据流时，非生产沙盒中的回填将限制为 3 个月。生产沙盒的时间将保持在 13 个月。 | 不适用 | 2023 年 4 月 26 日 |
| **共享项目链接（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置 Adobe Analytics 的人员共享。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>此功能默认启用，可由系统管理员禁用。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 |
| **更新了 Analytics 功能板应用程序（移动应用程序）的主屏幕** | 新更新的主屏幕允许您在一个综合记分卡列表中查看所有记分卡。如果您登录一次可以访问多个组织，则您组织的所有记分卡都将在一个列表中提供。 | 不适用 | 2023 年 5 月 10 日 |
| **派生的字段** | 这代表派生字段的初始版本。派生字段允许您通过可自定义的规则生成器动态定义（通常是复杂的）数据操作。您可以进一步将派生字段定义为数据视图中的组件（度量或维度），然后将派生字段用作工作区中的组件。<p>此版本支持营销渠道模板和以下功能：</p><ul><li>串联</li><li>情况</li><li>查找和替换</li><li>查询</li><li>URL 解析</li></ul> <p>[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 2023 年 5 月 10 日 | 待定 |
| **CJA Report Builder - 从单元格中选择数据视图** | 此功能允许用户从单元格中选择数据块的数据视图。如果您创建一个工作簿并且您有多个具有相似数据结构的数据视图，并且希望能够多次重用具有不同数据视图的工作簿，这将很有帮助。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 不适用 | 2023 年 5 月 24 日 |
| **在 Analysis Workspace 中对组件进行排序** | <p>在 Analysis Workspace 的左侧栏或数据词典中查看组件时，现在可以使用新的排序选项。您可以按推荐（最常用的）、字母顺序或分类（类型）对组件进行排序。</p><p>以前，您只能搜索或过滤组件。[了解详情](/help/components/overview.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **从自由格式表中删除包含动态维度的行** | 在 Analysis Workspace 的自由格式表中，您现在可以使用 x 图标快速删除包含动态维度的特定行。这样做时，会自动应用“不等于”过滤规则。<p>以前，删除包含动态维度的行的唯一方法是在“过滤器”对话框中手动创建规则。[了解详情](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **用于在面板中添加可视化的新按钮** | Analysis Workspace 中每个面板的底部现在都有一个新按钮，可供您快速添加可视化效果。 <p>以前，在面板中添加可视化效果的唯一方法是从左侧栏拖动可视化、复制现有可视化效果，或者创建空白面板。[了解详情](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **深层链接（移动应用程序）** | 允许用户发送指向记分卡的链接，这些链接会直接引导他们进入应用程序中的记分卡项目。这使得共享项目和提高技术水平较低的受众的参与度变得更加容易。 | 不适用 | 2023 年 5 月 17 日 |
| **智能题注** | 通过 [!UICONTROL 折线图] 可视化图表。 [了解详情](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023 年 5 月 17 日 | 2023 年 6 月 1 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-316412; AN-317105; AN-318122; AN-317353

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | 不适用 | 不适用 |

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到AdobeIO OAuth服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用AdobeIO JWT凭据的Adobe Analytics API、CJA API和Livestream客户必须通过 **2025年1月1日**. 从2024年5月1日开始，AdobeIO将不允许创建新的JWT凭据。 使用JWT的客户必须创建新的OAuth服务器到服务器凭据，或将其现有的JWT凭据迁移到OAuth服务器到服务器凭据。 客户还必须更新其客户端应用程序才能使用新的OAuth服务器到服务器凭据。 <ul><li>[从服务帐户(JWT)凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的OAuth服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |

{style="table-layout:auto"}

## 相关资源

* [以前的 2023 年 CJA 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
