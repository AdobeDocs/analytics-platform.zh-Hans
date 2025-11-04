---
description: 管理现有导出的日志
keywords: Analysis Workspace
title: 导出失败疑难解答
feature: Components
exl-id: fbc25150-4390-40a2-9f17-aadf254258ad
role: User
source-git-commit: 39147f5bd8409578199607fee84cf436cfd624fb
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 6%

---

# 导出失败疑难解答

当您将整个表从Analysis Workspace[导出到Cloud目标](/help/analysis-workspace/export/export-cloud.md)时，您可以从[Exports选项卡](/help/components/exports/manage-exports.md)和[Logs选项卡](/help/components/exports/manage-export-logs.md)查看这些导出的状态。 失败的导出显示&#x200B;[!UICONTROL **失败**]&#x200B;的状态。

## 常见失败和操作

导出可能由于各种原因而失败。 下表介绍了一些最常见的原因，以及您可以采取的解决故障的措施：

| 失败原因 | 建议的操作 | 更多信息 |
|---------|----------|---------|
| 位置或帐户信息无效 | 确保您要导出的云帐户和位置的凭据和其他信息正确。 | [配置云导出帐户](/help/components/exports/cloud-export-accounts.md)和[配置云导出位置](/help/components/exports/cloud-export-locations.md)。 |
| 报表中的维度或量度已从数据视图中删除 | 请与系统管理员联系，查看已从数据视图中删除哪些组件。 您可能需要在导出中使用不同的数据视图，或从表中删除不再可用的组件。 | [将Customer Journey Analytics报表导出到云](/help/analysis-workspace/export/export-cloud.md) |
| 超出行数限制 | 根据您的许可证类型，最多可以导出300万、3000万、1.5亿或3亿行。 更新要导出的表以减少总行数。 | [将Customer Journey Analytics报表导出到云](/help/analysis-workspace/export/export-cloud.md) |
| 计划的导出过期 | 您配置的计划导出已过期。 更新导出的过期。 | [管理导出](/help/components/exports/manage-exports.md) |
| 不支持Dimension | <p>完全表导出不支持任何满足以下所有条件的维度：</p> <ul><li>从属于对象数组的字段创建</li><li>已启用持久性<li>未使用绑定维度</li> | <ul><li>[使用对象数组](/help/use-cases/object-arrays.md)</li><li>[持久性组件设置](/help/data-views/component-settings/persistence.md)<li>[在Customer Journey Analytics中使用绑定维度和量度](/help/use-cases/data-views/binding-dimensions-metrics.md)</li> |
| 您的组织强制实施的数据治理策略限制导出表中的组件 | 请与系统管理员联系，查看哪些组件被限制导出。 导出之前删除受限制的组件。 | *筛选*&#x200B;标签和策略[中数据视图](/help/data-views/data-governance.md)部分的数据治理策略 |

## 联系Adobe客户关怀部门

如果您仍然遇到问题，请联系Adobe客户关怀部门。 在联系客户关怀部门了解导出失败的情况时，请确保您具有以下可用信息：

* 导出名称

* 导出 ID

* 实例 ID

* 数据视图名称

* 位置

* 帐户

* 连接

* 公司名称
