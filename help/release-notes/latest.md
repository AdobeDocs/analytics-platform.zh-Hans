---
title: 查看当前 Customer Journey Analytics 发行说明
description: 最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 22b87a6f64c296e3eb05ec3b7076bf6dfa2935f9
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 43%

---

# 当前的Adobe Customer Journey Analytics发行说明（2024年2月）

**上次更新**：2024年2月14日

这些发行说明涵盖2024年2月14日至2024年3月11日的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **时间序列预测** | [预测](../analysis-workspace/c-forecast/forecasting.md) 是一项新的Analysis Workspace功能，用于通过任何受支持的时间粒度（每小时、每天、每周、每月和每年）为自由格式表和折线图预测标准或计算量度。 | 2024 年 1 月 31 日 | 2024 年 2 月 21 日 |
| **Media Analytics报表 — 平均受众访问分钟数(AMA)** | “平均受众访问分钟数”面板现在在CJA中可用。 Media Analytics客户可以使用“平均受众访问分钟数”面板来更好地了解其内容的平均使用情况。 平均受众访问分钟数可以比较任何长度或类型的编程。此外，客户可以将此数字平均受众访问分钟数与线性电视平均访问分钟数指标进行比较或附加到其上。此面板提供了更大的灵活性来测量自定义时间段的平均受众访问，以及持续时间分类在事后更新的时间。 |  | 2024 年 2 月 |
| **查找和配置文件数据的行计数量度** | 作为连接的一部分配置的数据集的行计数量度现在包括添加、跳过或从配置文件和查找数据集中删除的记录。 |  | 2024年2月14日 |
| **体验边缘机器人检测** | [机器人检测](https://experienceleague.adobe.com/docs/experience-platform/datastreams/bot-detection.html) 用于识别由已知爬虫程序和机器人生成的Web SDK、Mobile SDK和服务器API生成的事件。 | | 2024 年 2 月 21 日 |
| **使用情况量度** | 使用量度界面显示所有连接中摄取和可报告行的使用情况。 利用此界面，可确定您的Customer Journey Analytics使用是否符合合同约定的内容。 | 2024年2月20日 | 2024年3月初 |
| **Adobe Product Analytics：与任何人共享** | 允许您与无权访问Adobe Product Analytics的用户共享指向Product Analytics项目的只读链接。 |  | 2024 年 2 月 21 日 |
| **Adobe Product Analytics：应用计算指标** | 您现在可以在“趋势：使用情况”视图中访问在Analysis Workspace或计算量度生成器中创建的计算量度，从而能够显示一段时间内的量度趋势并比较这些量度。 |  | 2024年2月16日 |

{style="table-layout:auto"}

## Customer Journey Analytics 中的修复

AN-333172； AN-336887； AN-337402； AN-337593； AN-338482； AN-338684； AN-339883； AN-340200

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
