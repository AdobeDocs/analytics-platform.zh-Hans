---
title: 当前 Customer Journey Analytics 发行说明
description: 查看最新的 Customer Journey Analytics 发行说明
exl-id: e8eab856-34e0-4875-b441-b1e680b9e111
feature: Release Notes
source-git-commit: 9f954709a3dde01b4e01581e34aece07fe0256b1
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 44%

---

# 当前的 Adobe Customer Journey Analytics 发行说明（2025 年 4 月）

**上次更新时间**：2025年4月16日

这些发行说明涵盖2025年3月27日至5月15日的发行期。 Adobe Customer Journey Analytics 版本在[持续投放模型](releases.md)上运行，通过该模型可采用更具可扩展性、分阶段的方法部署功能。因此，这些发行说明每月更新几次。请定期检查。

## 新增功能或更新后的功能

| 功能 | 描述 | [开始推出](releases.md) | [正式发布](releases.md) |
| ----------- | ---------- | ------- | ---- |
| **数值维度的“无值”行项目的更新** | 对于数值维度，此更新可让您<ul><li>在区段中使用“无值”维度项。</li><li>在报告中对“无值”行项目进行细分。</li></ul> [了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/no-value-options#numeric) | 2025 年 3 月 27 日 |
| **Adobe Content Analytics** | Adobe Content Analytics 可让您快速轻松地调查大量内容数据，以了解趋势、发现异常、识别内容疲劳并从内容曝光中获取见解。<p>开箱即用，您可以使用预建的报告模板和资产检查器等新功能节省时间。此功能不仅可以让您根据数据直观地查看资产，还可以打开每个资产以获取汇总的详细信息，包括绩效、投放环境、属性等。<p>您可以在完整的客户历程背景中调查这组新的内容数据，以回答重要的业务问题、评估内容绩效、增强分段、识别优化机会并定义新的待激活的受众。<p>内容分析是 Customer Journey Analytics 的附加功能。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/content-analytics/content-analytics) |  | 2025 年 3 月 27 日 |
| **媒体收集：Adobe Source Connector 更新了新的媒体报告 XDM** | Analytics 源连接器会自动将 Adobe Analytics 中的流媒体数据映射到 Web SDK 使用的相同字段。以前，数据被映射到旧位置和新位置，但未来只使用新位置。[了解详情](https://experienceleague.adobe.com/zh-hans/docs/analytics/implementation/aep-edge/xdm-var-mapping) |  | 2025 年 3 月 31 日 |
| **更新了用于将流媒体数据收集到Adobe Experience Platform的XDM字段** | 新的XDM字段组`mediaReporting`可用于将流媒体数据收集到Adobe Experience Platform中。 新的`mediaReporting`字段组替换了以前使用的`media.mediaTimed`字段组。<p>在三个月的过渡期间，`media.mediaTimed`字段上的数据摄取将继续。 但是，在2025年7月底，`the media.mediaTimed`字段将完全弃用，并且在Adobe Experience Platform架构UI中将不再可见，数据将仅使用`mediaReporting`字段发送。<p>在2025年4月22日之前实施了Analytics Source Connector以将流媒体数据收集到Platform的客户必须迁移其现有配置，才能使用新字段组发送数据。 此迁移必须在2025年7月底之前完成。 有关迁移支持，请联系您的Adobe Consulting服务或帐户团队。 对于在2025年4月22日后实施Analytics Source Connector的客户，无需执行任何操作。 |  | 2025年4月22日 |
| **术语更改：“筛选器”更改为“区段”** | 以前，Adobe Customer Journey Analytics将区段称为“过滤器”。 此术语现已与Adobe Analytics保持一致。 “过滤器”现在称为“区段”。 （显然，搜索筛选器仍称为“筛选器”。）用户界面已更新，文档正在更新中。 |  | 2025年4月16日 |
| **拼接：从XDM IdentityMap检索永久和临时ID** | 此功能支持在拼接过程中使用XDM identityMap中存储的身份。 identityMap可用于基于字段的拼合的永久ID或临时ID，也可用于基于图形的拼合的永久ID。  可以使用identityMap中的特定命名空间或主身份。 （文档链接见下文） |  | 2025年4月25日 |
| **跨数据视图共享量度和维度** | 允许您在多个数据视图中应用维度和量度设置。 对共享维度或量度所做的更改将应用于该维度或量度在所有适用数据视图中的所有实例。 使用此界面，Customer Journey Analytics管理员可以在使用许多数据视图时更轻松地管理组件。 （文档链接见下文） |  | 2025年4月30日 |


## Customer Journey Analytics 中的修复

**Admin Console**： AN-370228
**Analysis Workspace**： AN-371933； AN- 371933； AN-371979
**受众**： AN-373032
**组件设置**： AN-367400
**派生字段**： AN-370614； AN-370959
**导出位置**： AN-371670
**完整表导出**： AN-360492； AN-369204； AN-370755；AN-372294； AN-372363； AN-372754； AN-373040； AN-373081； AN-373168
**历程画布**： AN-373294
**移动设备应用程序**： AN-363169； AN-368496； AN-371766
**产品使用情况**： AN-369501
**报告**： AN-369085； AN-371094； AN-372580


## Customer Journey Analytics 管理员的重要注意事项

| 注意事项 | 添加或更新注意事项 | 描述 |
| --- | --- | --- |
| 不适用 | | |

## 相关资产

* [之前的 2025 Customer Journey Analytics 发行说明](/help/release-notes/2025.md)
* [Adobe Analytics 发行说明](https://experienceleague.adobe.com/docs/analytics/release-notes/latest.html?lang=zh-hans)
* [流媒体收藏集发行说明](https://experienceleague.adobe.com/docs/media-analytics/using/additional-resources/release-notes.html?lang=zh-hans)
* [Adobe Experience Cloud 发行说明](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=zh-hans)
* [Customer Journey Analytics 文档更新](/help/release-notes/doc-changes.md)
