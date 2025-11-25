---
title: 在Customer Journey Analytics中分析Experience Platform受众
description: 了解如何在Customer Journey Analytics中分析Experience Platform受众。
solution: Customer Journey Analytics
feature: Audiences
role: Admin
hide: true
hidefromtoc: true
source-git-commit: 2b91c0592ac4ec0e0b5ffa3db91758466563abaf
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# 在Customer Journey Analytics中分析Experience Platform受众 {#analyze-audiences-RTCDP}

当受众数据在Customer Journey Analytics中可用作新维度时，在[创建受众分析配置](/help/connections/audience-analysis/audience-analysis-configure.md)之后，即可开始在Analysis Workspace中分析Experience Platform受众。

Customer Journey Analytics中提供了受众概述模板。

<!-- Can you also use the new audience dimensions in any project, regardless of whether it's a template? I assume so -->

<!-- What are the names of the new dimensions? Are they customized to whatever your audience names are in AEP, or are they always the same? -->

有关如何访问受众概述模板的信息，请参阅[使用模板](/help/analysis-workspace/templates/use-templates.md#access-and-run-a-template)中的[访问和运行模板](/help/analysis-workspace/templates/use-templates.md)。

受众概述模板包含以下面板：

## 使用概述面板

显示所有受众的数据，其中包含与选定数据视图关联的使用事件。 受众会员资格数据每天从Experience Platform更新。 数据始终显示于昨天，因此更改面板日期范围导致数据不准确。

使用此面板中的表可以更好地了解受众行为。 从所选数据视图拖动受众描述维度，并将其添加为划分。 或使用任何其他交互维度（例如“页面”、“操作”等）作为细分。

## “顶级受众来源”面板

显示创建受众的位置，无论是在RTCDP、Customer Journey Analytics还是其他位置。

使用本面板中的表可以更好地了解受众来源可能如何影响其他因素。 从所选数据视图拖动受众名称维度，并将其添加为划分。 或使用任何其他交互维度（例如“页面”、“操作”等）作为细分。

## 受众重叠面板

显示所有受众的数据，其中包含与选定数据视图关联的使用事件。 数据始终显示于昨天，因此更改面板日期范围导致数据不准确。

在此面板中的表中选择最多三个受众，以查看它们在相应的维恩图中的重叠方式。

## “退出受众使用情况”面板

显示所有已退出受众的数据，其中包含与所选数据视图关联的使用事件。 数据始终显示于昨天，因此更改面板日期范围导致数据不准确。 “退出受众”是指具有使用事件的用户昨天离开或退出的受众。

使用本面板中的表可以更好地了解受众行为。 从所选数据视图拖动现有的受众描述维度，并将其添加为划分。 或使用任何其他交互维度或量度（例如页面、操作等）作为细分。

## “退出次数最多的受众来源”面板

显示退出每个受众最初创建的位置，无论是在RTCDP、Customer Journey Analytics还是其他位置。

使用本面板中的表可以更好地了解受众来源可能如何影响其他因素。 从所选数据视图拖动退出受众名称维度，并将其添加为划分。 或使用任何其他交互维度或量度（例如页面、操作等）作为细分。








