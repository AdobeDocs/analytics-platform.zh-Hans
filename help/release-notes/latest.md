---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9e6231e4dc9770fbb7c859b397ea8c57e7dff478
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 100%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2023 年 7 月）

**上次更新日期**：2023 年 7 月 13 日

Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **Adobe Product Analytics** | Adobe Product Analytics 是一种与 Customer Journey Analytics 中的跨渠道数据和见解进行交互的新方式。这些新功能使产品团队能够通过引导式分析工作流程自助提供有关其产品体验的数据和见解。团队可以：<ul><li>了解用户参与在一段时间内的模式</li><li>跟踪产品用户群的增长和保留</li><li>确定产品中出现分歧的方面</li><li>衡量功能发布和首次使用的影响</li><li>在产品的整个生命历程中，发现有意义的用户细分群体，与之互动并进行培养</li><li>连接到 Analysis Workspace 以进行更深入的分析并与分析师进行协作</li></ul>Adobe Product Analytics 是 Customer Journey Analytics 的付费加载项。如果您的组织想配置为使用此功能，请联系您的 Adobe 帐户团队。[了解详情](/help/guided-analysis/overview.md) | 不适用 | 2023 年 7 月 17 日 |
| **派生字段** | 这代表派生字段的初始版本。通过派生字段和可自定义的规则生成器，即可迅速定义（一般较为复杂的）数据操作。可进一步将该派生字段定义为数据视图中的组件（指标或维度），然后将该派生字段用作 Workspace 中的组件。<p>此版本支持营销渠道模板和以下功能：</p><ul><li>拼接</li><li>Case When</li><li>查找和替换</li><li>查询</li><li>URL 解析</li></ul> <p>[了解详情](/help/data-views/derived-fields/derived-fields.md)</p> | 2023 年 5 月 10 日 | 2023 年 8 月 2 日 |
| **配置文件和查找数据的扩展查找支持** | 提供将数据集添加为配置文件或查找数据集中的字段查找的功能。之前，仅支持事件数据集。[了解详情](/help/connections/create-connection.md) | 2023 年 6 月 21 日 | 2023 年 7 月 12 日 |
| **Report Builder 增强功能** | <ul><li>从单元格中过滤多个数据块。您可以更改单元格中多个数据块的过滤器。使用预定义的单元格，将它分配给多个数据块，并基于单元格中定义的过滤器更新数据。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/select-data-view.html?lang=zh-Hans)</li><li>显示和隐藏行标题和列标题。您可以显示或隐藏数据块表标题或行标题和列标题，以重新格式化表并对齐报表中的数据块。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-reportbuilder/create-a-data-block.html?lang=zh-Hans#build-the-data-block)</li></ul> | 不适用 | 2023 年 7 月 19 日 |
| **Experience Edge 地理位置查询** | Adobe Experience Edge 添加了一项地理位置查询服务，可为所有 Experience Edge 用户（Adobe Analytics、Customer Journey Analytics、Adobe Target、Adobe Media Analytics、Adobe Experience Platform 等）提供统一的地理数据。 | 不适用 | 2023 年 7 月 26 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-317971；AN-319234；AN-320439；AN-320519；AN-321740；AN-322444；AN-323116

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| **Customer Journey Analytics 处理数据方式的变更** | 2023 年 6 月 22 日 | 我们最近变更了 Customer Journey Analytics 中的数据处理方式。<ul><li>任何时间戳少于 24 小时的事件数据都将流入。</li><li>任何时间戳多于 24 小时的事件数据（即使它与更新的数据属于同一批次）都将视为回填，并将以较低的优先级摄取。</li></ul> |

{style="table-layout:auto"}

## 生命周期终止 (EOL) 通知

| 产品或功能 EOL | 添加或更新日期 | 描述 |
| --- | --- | --- |
| **迁移到 Adobe I/O OAuth 服务器到服务器凭据** | 2023 年 5 月 11 日 | 使用 Adobe I/O JWT 凭据的 Adobe Analytics API、Customer Journey Analytics API 和 Livestream 客户必须在 **2025 年 1 月 1 日**&#x200B;之前迁移到 Adobe I/O OAuth 服务器到服务器凭据。从 2024 年 5 月 1 日开始，Adobe I/O 将不允许创建新的 JWT 凭据。使用 JWT 的客户必须创建新的 OAuth 服务器到服务器凭据或将他们现有的 JWT 凭据迁移到 OAuth 服务器到服务器凭据。客户还必须更新其客户端应用程序以使用新的 OAuth 服务器到服务器凭据。 <ul><li>[从服务帐户 (JWT) 凭据迁移](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/)</li><li>[使用新的 OAuth 服务器到服务器凭据](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/)</li><li>[常见问题解答](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/faqs/)</li></ul> |

{style="table-layout:auto"}


## 相关资源

* [之前的 2023 Customer Journey Analytics 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
