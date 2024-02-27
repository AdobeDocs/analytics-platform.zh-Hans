---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 70705430e578ad49a919bc8ad172adf7d28c4887
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 82%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2024 年 2 月）

**上次更新**：2024年2月27日

这些发行说明涵盖 2024 年 2 月 14 日至 2024 年 3 月 11 日的发行期。Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **时间序列预测** | [预测](../analysis-workspace/c-forecast/forecasting.md)是 Analysis Workspace 的一项新功能，用于按任何支持的时间粒度（每小时、每天、每周、每月和每年）为自由格式表和折线图预测标准量度或计算量度。 | 2024 年 1 月 31 日 | 2024 年 2 月 21 日 |
| **Media Analytics 报告 - 平均受众访问分钟数 (AMA)** | CJA 中现已提供“平均受众访问分钟数”面板。Media Analytics 客户使用“平均受众访问分钟数”面板可更好地了解其内容的平均使用情况。平均受众访问分钟数可以比较任何长度或类型的编程。此外，客户可以将此数字平均受众访问分钟数与线性电视平均访问分钟数指标进行比较或附加到其上。此面板可更灵活地衡量自定义时段的平均受众以及在事后更新持续时间分类的时间。 |  | 2024 年 2 月 |
| **查找和配置文件数据的行数量度** | 作为连接的一部分配置的数据集行数量度现在包括从配置文件和查找数据集添加、跳过或删除的记录。 |  | 2024 年 2 月 14 日 |
| **体验边缘机器人检测** | 通过[机器人检测](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html)，可将 Web SDK、Mobile SDK 和 Server API 生成的事件视为由已知的蜘蛛程序和机器人生成。 | | 2024年4月29日 |
| **使用情况量度** | 使用情况量度界面显示所有连接中摄取和可报告的行的使用情况。在此界面中可确定您的 Customer Journey Analytics 使用情况是否遵守合同条款。 | 2024 年 2 月 20 日 | 2024 年 3 月初 |
| **Adobe Product Analytics：与任何人共享** | 使您可与无权访问 Product Analytics 的人士共享 Adobe Product Analytics 项目的只读链接。 |  | 2024年3月5日 |
| **Adobe Product Analytics：应用计算指标** | 现在可在“趋势：使用情况”视图中访问在 Analysis Workspace 或计算量度生成器中创建的计算量度，使您可分析和比较一段时间内的量度。 |  | 2024 年 2 月 16 日 |
| **更新了数据视图和连接UI中的链接** | 3月初，Adobe计划在Customer Journey Analytics产品用户界面中更新以下链接。 请相应地更新您的书签。<ul><li>**数据视图页面，数据视图管理器**： [现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/manager) > [新建链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views)</li><li>**创建新数据视图**： [现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/new) > [新建链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/data-views/new)</li><li>**编辑数据视图**： [现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/dataViewsCJA/edit/dv_65b9f6eba2c6554743236e88) > [新建链接](https://experience.adobe.com/#/@aresemeavalidationco/platform/analytics/#/apps/data-management/data-views/dv_62fde2e158324f2803c9e5d6/edit)</li><li>**连接管理器**： [现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/manager) > [新建链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections)</li><li>**连接信息**： [现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/view/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新建链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8)</li><li>**编辑连接**： [现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/edit/dg_66749c92-784b-45bb-b114-e9e8377a2fc1) > [新建链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/dg_a2b297a6-9220-440d-a403-ee8fbf627cd8/edit)</li><li>**创建新连接**： [现有链接](https://experience.adobe.com/#/@aresstagevalidationco/platform/analytics/#/connections2/new) > [新建链接](https://experience.adobe.com/#/@org/platform/analytics/#/apps/data-management/connections/new/edit)</li></ul> |  | 2024 年 3 月 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-333172、AN-336887、AN-337402、AN-337593、AN-338482、AN-338684、AN-339883、AN-340200

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 添加了 Adobe API 对象成员 | 2024 年 1 月 17 日 | Adobe 可能会无通知或在版本控制中无变更地将可选的请求和响应成员（名称/值对）添加到现有的 API 对象。此类添加应为不令您的实施发生中断的更改。Adobe 建议您参考与我们的 API 集成的任何第三方工具的 API 文档，以便在处理过程中忽略不了解的此类添加。如果没有首先通过发行说明提供标准通知，Adobe 不会删除参数或添加所需参数。 |

{style="table-layout:auto"}

## 相关资源

* [之前的 2023 Customer Journey Analytics 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
