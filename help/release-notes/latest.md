---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: c7aad8e75f47b978da109972928d1f314c15a9f9
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 41%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2024 年 7 月）

**上次更新日期**：2024年7月17日

这些发行说明涵盖2024年7月17日至2024年8月的发行期。 Adobe Customer Journey Analytics版本在[连续交付模型](releases.md)上运行，该模型允许采用更具可扩展性、分阶段的方法部署功能。 因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **智能警报** | 智能警报现在可以在Customer Journey Analytics中使用，当数据中出现异常事件时，您会立即收到通知。<p>您可以设置要根据异常阈值、更改的百分比或特定数据点触发的警报。 警报提供了与异常检测集成的粒度控制，可在您最需要它们时触发。</p><p>在Customer Journey Analytics中使用智能警报的过程与在Adobe Analytics中使用智能警报的过程几乎相同。 一个关键区别在于Customer Journey Analytics中不存在每小时警报。 此差异在于可摄取的各种事件数据的数据摄取仅在延迟后才能完成，延迟时间通常比数据事件时间晚3到9个小时。</p><p>（更新了要遵循的文档链接）</p><!--<p>[Learn more](/help/analysis-workspace/c-intelligent-alerts/intellligent-alerts.md)</p> --> |  | 2024年7月26日 |
| **管理员设置，用于控制将报告导出到云时使用的帐户和位置** | 位置管理器](/help/components/exports/manage-export-locations.md#configure-company-wide-settings-administrators-only)中新增的[“管理员设置”选项卡可让管理员控制用户是否可以创建和编辑帐户和位置。<p>当用户[配置云导出帐户](/help/components/exports/cloud-export-accounts.md)和[配置云导出位置](/help/components/exports/cloud-export-locations.md)时，这些设置适用。</p><p>管理员还可以限制用户可以创建和使用的帐户类型。 帐户类型包括Google Cloud Platform、Azure RBAC、Amazon S3、AEP Data Landing Zone、Snowflake等。</p><p>以前，任何用户都可以创建、编辑和使用任何类型帐户的帐户和位置。</p> | 2024年7月11日 | 2024年7月19日 |
| **摘要级数据源** | 允许您引入没有人员ID的时间系列数据。 此时间序列数据可用于支持各种用例，例如：<ul><li>将高级别绩效指标作为事件级别数据的一部分或旁边显示。 这可能包括简单的日期和单个量度值等，也可能包括多个维度和量度，如广告展示次数、电子邮件打开次数、广告支出、商品销售成本等。</li><li>每天、每周、每月或每季度上传目标或目标，并根据事件级别的量度定位这些目标或目标，以帮助可视化量度相对于组织目标或目标的趋势。</li></ul><p>（更新了要遵循的文档链接）</p> |  | 2024年7月31日 |
| **派生字段 — 删除重复函数** | Derived Fields中的Deduplicate函数有助于避免对一个值多次计数。<p>[了解详情](/help/data-views/derived-fields/derived-fields.md#deduplicate)</p> |  | 2024年7月17日 |
| **针对CJA客户的引导式分析配置** | 引导式分析使用户能够通过基于Customer Journey Analytics的跨渠道数据构建的引导式工作流为客户历程提供高质量数据和见解。 <p>从营销到产品的跨职能团队可以实时连接，以使用和理解这些报告。</p><p>CJA包中现在提供最多11个引导式分析视图。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/guided-analysis/overview)</p> |  | 2024年7月17日 |
| **共享用于导出和导入的账户和位置** | 用户现在可以将他们创建的帐户和位置提供给其组织内的所有用户。只有帐户和位置所有者以及系统管理员可以编辑和删除帐户和位置。以前，帐户和位置只能由创建它们的用户使用。当用户[配置云导出帐户](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/exports/cloud-export-accounts)以及[配置云导出位置时，这些设置适用](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/exports/cloud-export-locations)。 | 2024 年 6 月 12 日 | 2024 年 7 月中旬 |
| **Audiences 已发布到 Experience Platform 中的新“Audiences”部分** | 从 Customer Journey Analytics 中发布的受众现在可以在 Adobe Experience Platform 的新“受众”部分中找到。<p>此前，从 Customer Journey Analytics 发布的受众可在 Experience Platform 的“细分”部分下找到。</p><p>此改进具有以下优点：</p><ul><li>受众出现在 Experience Platform 前不再有 1 小时的延迟；它们在发布后几秒钟即可使用。</li><li>可以使用 Experience Platform 中“来源”列对受众进行排序，该列显示了最初发布受众的应用程序。</li><li>Experience Platform中的过滤和排序选项使您能够更快地找到相关受众。</li></ul> <p>（文档链接见下文）</p> |  | 待定 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-306000； AN-288748； AN-351547； AN-351110

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
