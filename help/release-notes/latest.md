---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新Customer Journey Analytics发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 2b0d091484c3c80d97de2952f4200d166ab5cd8a
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 37%

---

# 当前的Adobe Customer Journey Analytics发行说明（2023年7月）

**上次更新日期**：2023 年 7 月 10 日

Adobe Customer Journey Analytics版本在 [连续传递模型](releases.md) 这允许采用更具可扩展性、分阶段的方法部署功能。 因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics是在Customer Journey Analytics中与跨渠道数据和见解进行交互的新方法。 这些新功能使产品团队能够通过引导式分析工作流程自助提供有关其产品体验的数据和见解。团队可以：<ul><li>了解用户参与在一段时间内的模式</li><li>跟踪产品用户群的增长和保留&#x200B;。</li><li>识别产品中的摩擦区域</li><li>衡量功能发布&#x200B;和首次使用的影响</li><li>发现用户中有意义的区段，以便在其整个产品历程中吸引和培育&#x200B;。</li><li>连接到Analysis Workspace以进行更深入的分析和与分析师的合作</li></ul>Adobe Product Analytics是Customer Journey Analytics的付费附加组件。 如果您的组织希望进行配置以使用此功能，请联系您的Adobe客户团队。 [了解详情](/help/guided-analysis/overview.md) | 不适用 | 2023 年 7 月 17 日 |
| **派生字段** | 这代表派生字段的初始版本。通过派生字段和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。您可以进一步将派生字段定义为数据视图中的组件（量度或维度），然后在工作区中将派生字段用作组件。<p>此版本支持营销渠道模板和以下功能：</p><ul><li>拼接</li><li>Case When</li><li>查找和替换</li><li>查询</li><li>URL 解析</li></ul> <p>[了解详情](/help/data-views/derived-fields/derived-fields.md)</p> | 2023 年 5 月 10 日 | 2023 年 8 月 2 日 |
| **扩展了对配置文件和查找数据的查找支持** | 提供将数据集添加为配置文件或查找数据集内字段的查找的功能。 以前，仅支持事件数据集。 [了解详情] | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **Report Builder增强功能** | <ul><li>从单元格中筛选多个数据块。 您可以更改单元格中多个数据块的筛选器。 使用预定义单元格，将其分配给多个数据块，并根据单元格中定义的过滤器更新数据。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=en)</li><li>显示和隐藏行和列标题。 可显示或隐藏数据块表标题或行和列标题，以重新格式化表并在报表中对齐数据块。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=en#build-the-data-block)</li></ul> | 不适用 | 2023 年 7 月 19 日 |
| **Experience Edge 地理位置查询** | Adobe Experience Edge将添加地理查找服务，为所有Experience Edge用户(Adobe Analytics、Customer Journey Analytics、Adobe Target、Adobe Medium Analytics、Adobe Experience Platform等)提供统一的地理数据。 | 不适用 | 2023 年 7 月 26 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-317971； AN-319234； AN-320439； AN-320519； AN-321740； AN-322444； AN-323116

## Customer Journey Analytics管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **对Customer Journey Analytics处理数据的方式的更改** | 2023 年 6 月 22 日 | 我们最近改变了在Customer Journey Analytics中处理数据的方式。<ul><li>任何时间戳少于24小时的事件数据都将流式传入。</li><li>时间戳超过24小时的任何事件数据（即使它与较新数据位于同一批次中）都将被视为回填，并将以较低的优先级摄取。</li></ul> |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到Adobe I/OOAuth服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用Adobe I/OJWT凭据的Adobe Analytics API、Customer Journey AnalyticsAPI和Livestream客户必须迁移至Adobe I/OOAuth服务器到服务器凭据，迁移方式为 **2025年1月1日**. 从2024年5月1日开始，Adobe I/O不允许创建新的JWT凭据。 使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 相关资源

* [以前的Customer Journey Analytics2023年发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
