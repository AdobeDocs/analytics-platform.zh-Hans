---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: aa7f4361b1353a86b87c36c3d08e99ddb8ffd049
workflow-type: ht
source-wordcount: '602'
ht-degree: 100%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2023 年 9 月）

**上次更新日期**：2023 年 9 月 13 日

这些发行说明涵盖 2023 年 9 月 13 日至 2023 年 10 月 3 日的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **在 Analytics Source Connector 中支持 A4T 分类** | 现在可在 Adobe Analytics 源连接器架构中找到 `_experience.decisioning.propositions.scopeDetails.correlationID` 字段。该字段用于支持 A4T 分类，并将会于 2023 年 9 月开始填充。 | | 不适用 | 2023 年 9 月 12 日 |
| **更新了派生字段** | 对派生字段功能进行了以下更新：<ul><li>已将[!UICONTROL 查找]功能重命名为[!UICONTROL 分类]，并附带加载 CSV 数据的选项。**（2023 年 9 月 27 日发布）**</li><li>在定义派生字段时有附加功能可用：[!UICONTROL 修剪]、[!UICONTROL 小写]和[!UICONTROL 查找]。</li><li>派生字段定义现在还支持来自[!UICONTROL 查找]和[!UICONTROL 配置文件]数据集的字段。</li></ul>[了解详情](/help/data-views/derived-fields/derived-fields.md) | 不适用 | 2023 年 9 月 13 日 |
| **Adobe Product Analytics 中的新功能** | <ul><li>**异常检测**：比较事件与从历史趋势派生的预期值。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/usage.html)</li><li>**使用频率趋势视图**：通过使用频率衡量您的功能的采用情况。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/guided-analysis/trends/frequency.html)</li><li>**用户偏好设置**：配置许多用户偏好设置，例如调色板和数字格式。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-workspace/user-preferences.html)</li></ul> | 不适用 | 2023 年 9 月 18 日 |
| **Experience Edge 设备查找** | 通过 Experience Platform Edge Network 实现自动收集设备类型数据。此 Experience Edge 服务有利于 Customer Journey Analytics 以及其他 Experience Platform 应用程序。（文档链接见下文） | 不适用 | 2023 年 9 月 27 日 |
| **管理组件时可用的新列** | 在管理组件时，现在可在[计算量度管理器](/help/components/calc-metrics/cm-workflow/cm-manager.md)和[过滤器管理器](/help/components/filters/manage-filters.md)中找到以下新列：<ul><li>用在</li><li>上次使用时间</li></ul><p>此信息可帮助您确定某个组件是否对组织中的用户有用、在何处使用该组件以及是否需要删除或修改该组件。可使用数据词典配合此信息帮助您跟踪并更好地了解如何在您的组织中使用组件。</p> | 2023 年 9 月 20 日 | 2023 年 10 月 4 日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-310972；AN-319509；AN-322245；AN-323411；AN-323719；AN-326101；AN-326125；AN-326888


## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | 不适用 | 不适用 |

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
