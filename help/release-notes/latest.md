---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 306c1432163841034c8e7a34f8e112a5cc734da4
workflow-type: tm+mt
source-wordcount: '850'
ht-degree: 29%

---

# 当前 Customer Journey Analytics (CJA) 发行说明（2023 年 5 月）

**上次更新日期**：2023 年 5 月 8 日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 主要功能及更新

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **非生产沙盒的回填** | 在非生产沙盒中创建 Analytics 源连接器数据流时，非生产沙盒中的回填将限制为 3 个月。生产沙盒的时间将保持在 13 个月。 | 不适用 | 2023 年 4 月 26 日 |
| **共享项目链接（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置Adobe Analytics的人员共享。 [了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=en#share-public-link) <p>默认情况下，此功能处于启用状态，系统管理员可以禁用此功能。 [了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023年5月3日 | 2023 年 6 月 |
| **更新了Analytics功能板应用程序（移动设备应用程序）的主屏幕** | 新的更新主页屏幕允许您在一个整合的记分卡列表中查看所有记分卡。  如果您通过一次登录访问多个组织，则来自您组织的所有记分卡都将在单个列表中可用。 | 不适用 | 2023 年 5 月 10 日 |
| **派生字段** | 这表示派生字段的初始版本。 利用派生字段，可通过可自定义的规则生成器，即时定义（通常复杂）数据操作。 您可以在“数据”视图中进一步将派生字段定义为组件（量度或维度），然后在工作区中将派生字段用作组件。<p>此版本支持营销渠道模板和以下功能：</p><ul><li>串联</li><li>情况</li><li>查找和替换</li><li>查询</li><li>URL 解析</li></ul> <p>[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 2023 年 5 月 10 日 | 待定 |
| **Report BuilderCJA — 从单元格中选择数据视图** | 此功能允许用户从单元格中选择数据块的数据视图。 如果您创建工作簿，并且有多个数据视图，这些视图具有相似的数据结构，并且您希望能够使用不同的数据视图多次重复使用工作簿，则此操作会很有帮助。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 不适用 | 2023年5月24日 |
| **对Analysis Workspace中的组件排序** | <p>现在，在左边栏或Analysis Workspace的“数据字典”中查看组件时，可以使用新的排序选项。 您可以按推荐（最常用的组件）、按字母顺序或类别（类型）对组件进行排序。</p><p>以前，您只能搜索或过滤组件。 [了解详情](/help/components/overview.md)</p> | 不适用 | 2023年5月17日 |
| **从自由格式表中删除包含动态维度的行** | 在Analysis Workspace的自由格式表中，您现在可以使用x图标快速删除包含动态维度的特定行。 这样做时，会自动应用“不等于”过滤规则。<p>以前，删除包含动态维度的行的唯一方法是在过滤器对话框中手动创建规则。 [了解详情](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 不适用 | 2023年5月17日 |
| **用于在面板中添加可视化的新按钮** | 现在，Analysis Workspace中每个面板底部都有一个新按钮，通过该按钮，您可以快速添加可视化图表。 <p>以前，向面板添加可视化的唯一方法是从左边栏拖动可视化、复制或复制现有可视化，或创建空白面板。 [了解详情](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 不适用 | 2023年5月17日 |
| **深层链接（移动设备应用程序）** | 允许用户发送指向记分卡的链接，这些记分卡会将用户直接引导到应用程序中的记分卡项目。 这样，就更容易共享项目并提高技术含量较低的受众的参与度。 | 不适用 | 2023年5月17日 |
| **智能字幕** | 通过 [!UICONTROL 折线图] 可视化图表。 | 2023年5月17日 | 2023 年 6 月 1 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-316412;AN-317105;AN-318122;AN-317353

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
