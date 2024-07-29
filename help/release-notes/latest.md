---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 4f228dbe58a9efbe988f274c071c61ec5e36d321
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 99%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2024 年 7 月）

**上次更新日期**：2024年7月29日

这些发行说明涵盖 2024 年 7 月 17 日至 2024 年 8 月的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **智能警报** | Customer Journey Analytics 中现已提供智能警报功能，当您的数据出现异常事件时，您可以立即收到通知。<p>您可以设置根据异常阈值、变化的百分比或特定数据点触发的警报。警报提供与异常检测集成的细粒度控制，在您最需要时触发。</p><p>在 Customer Journey Analytics 中使用智能警报的过程与在 Adobe Analytics 中使用智能警报的过程几乎相同。一个主要的区别是 Customer Journey Analytics 不提供每小时警报。这种差异是因为，各种事件数据摄取只能在延迟之后才能完成，通常是数据事件时间之后的 3 到 9 个小时。</p><p>（已更新的文档链接见下文）</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 待定 |
| **用于控制将报告导出到云时使用的帐户和位置的管理员设置** | 一个新的[位置管理器中的“管理设置”选项卡](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only)使管理员可以控制用户是否可以创建和编辑帐户和位置。<p>当用户[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)和[配置云导出位置](/help/components/exports/cloud-export-locations.md)时会应用这些设置。</p><p>管理员还可以限制用户可以创建和使用的帐户类型。帐户类型包括 Google Cloud Platform、Azure RBAC、Amazon S3、AEP Data Landing Zone、Snowflake 等。</p><p>以前，任何用户都可以创建、编辑和使用任何类型帐户的帐户和位置。</p> | 2024 年 7 月 11 日 | 2024 年 7 月 19 日 |
| **摘要级别数据源** | 允许您引入没有人员 ID 的时间序列数据。该时间序列数据可用于支持各种用例，例如：<ul><li>将高级性能指标作为事件级数据的一部分或在其旁边呈现。这可以包括诸如日期和单个指标值之类的简单内容，也可以包括多个维度和指标，例如广告展示、电子邮件打开、广告支出、销售成本等。</li><li>按日、周、月或季度上传目标，并根据事件级指标定位这些目标，以帮助直观地了解指标相对于组织目标的趋势。</li></ul><p>（已更新的文档链接见下文）</p> |  | 2024年8月11日 |
| **派生字段：重复数据删除函数** | 派生字段中的 [重复数据删除函数](/help/data-views/derived-fields/derived-fields.md#deduplicate) 可帮助您避免多次计算某个值。 |  | 2024 年 7 月 17日 |
| **为 CJA 客户提供指导分析配置** | 引导式分析使用户能够通过基于 Customer Journey Analytics 的跨渠道数据的引导式工作流程，自助提供有关客户历程的高质量数据和洞察。 <p>从营销到产品的跨职能团队可以实时连接，以使用和理解这些报告。</p><p>CJA 包中现在最多可提供 11 个引导分析视图。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 2024 年 7 月 17日 |
| **共享用于导出和导入的账户和位置** | 用户现在可以将他们创建的帐户和位置提供给其组织内的所有用户。只有帐户和位置所有者以及系统管理员可以编辑和删除帐户和位置。以前，帐户和位置只能由创建它们的用户使用。当用户[配置云导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)以及[配置云导出位置时，这些设置适用](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)。 | 2024 年 6 月 12 日 | 2024 年 7 月 19 日 |
| **Audiences 已发布到 Experience Platform 中的新“Audiences”部分** | 从 Customer Journey Analytics 中发布的受众现在可以在 Adobe Experience Platform 的新“受众”部分中找到。<p>此前，从 Customer Journey Analytics 发布的受众可在 Experience Platform 的“细分”部分下找到。</p><p>此改进具有以下优点：</p><ul><li>受众出现在 Experience Platform 前不再有 1 小时的延迟；它们在发布后几秒钟即可使用。</li><li>可以使用 Experience Platform 中“来源”列对受众进行排序，该列显示了最初发布受众的应用程序。</li><li>Experience Platform 中的筛选条件和排序选项使您能够更快地找到相关受众。</li></ul> <p>（文档链接见下文）</p> |  | 待定 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-306000; AN-288748; AN-351547; AN-351110

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

{style="table-layout:auto"}

## 相关资源

* [之前的 2024 Customer Journey Analytics 发行说明](/help/release-notes/2024.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [流媒体收藏集附加组件发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
