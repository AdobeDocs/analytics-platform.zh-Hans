---
description: 管理现有导出的日志
keywords: Analysis Workspace
title: 导出失败疑难解答
feature: Components
hide: true
hidefromtoc: true
source-git-commit: 24e9e4151360597b099a7985a4566b3ca7bfff00
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 3%

---

# 导出失败疑难解答

当您 [将完整表从Analysis Workspace导出到云目标](/help/analysis-workspace/export/export-cloud.md)，您可以从以下位置查看这些导出的状态 [“导出”选项卡](/help/components/exports/manage-exports.md) 和从 [“日志”选项卡](/help/components/exports/manage-export-logs.md). 失败的导出显示状态 [!UICONTROL **失败**].

导出可能由于各种原因而失败。 下表介绍了一些最常见的原因，以及您可以采取的解决故障的措施：

| 失败原因 | 建议的操作 | 更多信息 |
|---------|----------|---------|
| 位置或帐户信息无效 | 确保您要导出的云帐户和位置的凭据和其他信息正确。 | [配置云导出帐户](/help/components/exports/cloud-export-accounts.md) 和 [配置云导出位置](/help/components/exports/cloud-export-locations.md). |
| 报表中的维度或量度已从数据视图中删除 | 请与系统管理员联系，查看已从数据视图中删除哪些组件。 您可能需要在导出中使用不同的数据视图，或从表中删除不再可用的组件。 | [将Customer Journey Analytics数据导出到云端](/help/analysis-workspace/export/export-cloud.md) |
| 您的组织强制实施的数据治理策略限制导出表中的组件 | 请与系统管理员联系，查看哪些组件被限制导出。 导出之前删除受限制的组件。 | *筛选数据视图中的数据治理策略* 中的部分 [标签和策略](/help/data-views/data-governance.md) |