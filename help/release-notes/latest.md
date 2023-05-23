---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新 CJA 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 440a23258b0a4bd024894168e3201ee0c2d5c756
workflow-type: tm+mt
source-wordcount: '852'
ht-degree: 84%

---

# 当前 Customer Journey Analytics (CJA) 发行说明（2023 年 5 月）

**上次更新日期**：2023 年 5 月 17 日

Customer Journey Analytics 版本在[持续交付模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 主要功能及更新

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **非生产沙盒的回填** | 在非生产沙盒中创建 Analytics 源连接器数据流时，非生产沙盒中的回填将限制为 3 个月。生产沙盒的时间将保持在 13 个月。 | 不适用 | 2023 年 4 月 26 日 |
| **用链接共享项目（无需登录）** | 您现在可以与无权访问 Adobe Analytics 的人员共享 Analysis Workspace 项目的只读链接。这包括与组织外的人员或组织内未配置 Adobe Analytics 的人员共享。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/share-projects.html?lang=zh-Hans#share-public-link) <p>默认启用此功能，而系统管理员可禁用此功能。[了解详情](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/user-preferences.html?lang=en#company-preferences)</p> | 2023 年 5 月 3 日 | 2023 年 6 月 |
| **更新了 Analytics 功能板应用程序（移动应用程序）的主屏幕** | 通过新近更新的主屏幕，可在一个合并的记分卡列表中查看您的所有记分卡。如果您可用一个登录名访问多个组织，则在一个列表中即可找到所有来自您这些组织的记分卡。 | 不适用 | 2023 年 5 月 10 日 |
| **派生字段** | 这代表派生字段的初始版本。通过派生字段和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。可进一步将该派生字段定义为数据视图中的组件（量度或维度），然后将该派生字段用作 Workspace 中的组件。<p>此版本支持营销渠道模板和以下功能：</p><ul><li>拼接</li><li>Case When</li><li>查找和替换</li><li>查询</li><li>URL 解析</li></ul> <p>[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/derived-fields.html)</p> | 2023 年 5 月 10 日 | 待定 |
| **CJA Report Builder - 从单元格选择数据视图** | 通过此功能，用户可从单元格选择数据块的数据视图。如果创建一个工作簿，并有多个数据视图的数据构造相似，而您希望能够以不同的数据视图多次重用工作簿，则这样做很有帮助。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html) | 不适用 | 2023 年 5 月 24 日 |
| **为 Analysis Workspace 中的组件排序** | <p>在 Analysis Workspace 中的左边栏或数据词典中查看组件时，现在有一个新的排序选项可用。可按“推荐”（最常用的那些组件）、“字母顺序”或“分类”（类型）为组件排序。</p><p>而以前只能搜索或过滤组件。[了解详情](/help/components/overview.md)</p> | 不适用 | 待定 |
| **从自由格式表中删除包含动态维度的行** | 现在可在 Analysis Workspace 的自由格式表中使用 x 图标快速地删除包含动态维度的特定行。這麼做時，會自動套用「一律排除專案」篩選規則。<p>而以前只有在“过滤器”对话框中手动创建规则才能删除包含动态维度的行。[了解详情](/help/analysis-workspace/visualizations/freeform-table/filter-and-sort.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **在面板中新增一个用于添加可视化效果的按钮** | Analysis Workspace 中每个面板的底部现在都有一个新按钮，通过它，可快速地添加可视化效果。 <p>而以前只有从左边栏拖动可视化效果、重复或复制现有的可视化效果或创建空白面板才能将可视化效果添加到面板。[了解详情](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)</p> | 不适用 | 2023 年 5 月 17 日 |
| **深层链接（移动应用程序）** | 使用户可发送记分卡的链接，而这些链接将引导用户直接进入应用程序中的记分卡项目。这样使得可更轻松地从不太熟悉技术的受众共享项目和提高参与度。 | 不适用 | 2023 年 5 月 17 日 |
| **智能字幕** | 透過的自然語言摘要，豐富使用者的敘事能力 [!UICONTROL 折線圖] 視覺效果。 [了解详情](/help/analysis-workspace/visualizations/intelligent-captions.md) | 2023 年 5 月 17 日 | 2023 年 6 月 1 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-316412、AN-317105、AN-318122、AN-317353

## CJA 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | 不适用 | 不适用 |

## 生命周期终止 (EOL) 通知 {#eol}

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **移轉至AdobeIO OAuth伺服器對伺服器認證** | 2023 年 5 月 11 日 | 使用AdobeIO JWT憑證的Adobe Analytics API、CJA API和Livestream客戶必須移轉至AdobeIO OAuth伺服器對伺服器憑證 **2025年1月1日**. 自2024年5月1日起，AdobeIO不允許建立新的JWT憑證。 使用JWT的客戶必須建立新的OAuth伺服器對伺服器認證，或將其現有的JWT認證移轉至OAuth伺服器對伺服器認證。 客戶也必須更新其使用者端應用程式，以使用新的OAuth伺服器對伺服器認證。 <ul><li>[從服務帳戶(JWT)憑證移轉](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的OAuth伺服器對伺服器認證](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul>![](assets/jwt.png) |

{style="table-layout:auto"}

## 相关资源

* [以前的 2023 年 CJA 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
