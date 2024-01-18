---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: efae6138159820414004a21de7c05b4373257876
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 28%

---

# 当前Adobe Customer Journey Analytics发行说明（2024年1月）

**上次更新**：2024年1月12日

这些发行说明涵盖2023年10月底至2024年1月的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **指导分析 — 保留率** | 一种新视图类型，显示初始参与后在所需日期范围内返回的用户百分比。 [了解详情](../guided-analysis/types/retention-rates.md) | 不适用 | 2024年1月8日 |
| **时间序列预测** | 预测是Analysis Workspace的一项新功能，可用于预测具有任何受支持时间粒度（每小时、每天、每周、每月和每年）的标准或计算量度。 | 不适用 | 2024年1月31日 |
| **引导式分析 — 趋势线** | 趋势线叠加图现在在以下位置提供： [使用情况](/help/guided-analysis/types/usage.md) 视图，这有助于更清晰地描述数据中的模式。 | 不适用 | 2024年1月17日 |
| **“连接详细信息”页面 — 跳过的记录** | 现在，您可以在定义连接时检查跳过记录的原因。 [了解详情](../connections/manage-connections.md) | 不适用 | 2024年1月31日 |
| **关键量度摘要可视化图表的更新** | 在使用关键指标摘要可视化图表时，比较日期范围现在可以自动更新，具体取决于您选择的比较日期范围选项是相对于主日期范围还是相对于固定日期范围。 [了解详情](/help/analysis-workspace/visualizations/key-metric.md)。 | 不适用 | 2024年1月17日 |
| **引导式分析 — 流** | 一种允许您浏览单个用户事件流的新视图类型。 此分析允许您查找体验模式并讲述更好的用户故事。 | 不适用 | 2024年1月31日 |
| **引导式分析 — 改进了查询边栏** | 一些组件设置现已包含在查询边栏中，从而改进了可用性。 | 不适用 | 2024年1月31日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-310972、AN-332774、AN-332793、AN-332796、AN-333157、AN-334067、AN-334134、AN-334968、AN-335315、AN-335518、AN-335533、AN-335736；

## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 添加API对象成员Adobe | 2024年1月17日 | Adobe可以将可选请求和响应成员（名称/值对）添加到现有API对象，而无需在版本控制中通知或更改。 此类添加内容应该对您的实施进行不间断的更改。 Adobe建议您查阅与我们的API集成的任何第三方工具的API文档，以便在处理过程中忽略不了解的此类添加。 如果未首先通过发行说明提供标准通知，Adobe将不会移除参数或添加所需参数。 |

{style="table-layout:auto"}

## 相关资源

* [之前的 2023 Customer Journey Analytics 发行说明](/help/release-notes/2023.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-Hans)
* [Media Analytics 发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-Hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-Hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
