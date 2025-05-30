---
title: 过渡指南
description: 了解如何从Customer Journey Analytics过渡到Customer Journey Analytics B2B edition
solution: Customer Journey Analytics
feature: Basics
role: User, Admin
badgePremium: label="B2B Edition"
exl-id: d0e6398b-8080-4e36-b178-0cb91945d0c5
source-git-commit: 2fad11178853e08783b8f48671b504f50b6e0770
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 0%

---

# 过渡指南

{{draft-b2b}}

本指南讨论如何从Customer Journey Analytics过渡到Customer Journey Analytics的B2B edition。

本文假定您已在某种程度上使用Customer Journey Analytics：

* 您有[个连接](/help/connections/overview.md)将数据摄取到Customer Journey Analytics。
* 您有[个数据视图](/help/data-views/data-views.md)，它们使用这些连接中的数据。
* 您有[个项目](/help/analysis-workspace/home.md)，其中包含利用这些数据视图的报表和可视化图表。

如果您以前未使用Customer Journey Analytics，请参阅[B2B edition快速入门指南](cja-b2b-quick-start-guide.md)。

如果您是Adobe Analytics用户并计划使用Customer Journey Analytics B2B edition，请首先参阅[从Adobe Analytics升级到Customer Journey Analytics](cja-upgrade/cja-upgrade-recommendations.md)文档。


## 现有实施

在您获得Customer Journey Analytics许可并进行配置以使用Customer Journey Analytics B2B edition后，的现有实施根本不会更改。

所有现有连接都视为[基于人员的连接](cja-b2b-concepts-features.md#connections-and-identifiers)，并且无需任何更新即可继续工作。 依赖这些基于人员的连接中的数据的所有内容（例如数据视图、工作区项目、区段、计划导出、警报等）将继续按原计划和预期工作。

>[!IMPORTANT]
>
>您无法将现有的基于人员的连接更改为基于帐户的连接。 需要新的基于帐户的连接才能使用B2B edition功能。
>


## 实施B2B功能

要在现有实施中实施B2B功能，您需要执行以下步骤：

1. 为您的B2B数据建模。 Customer Journey Analytics B2B edition至少会假定基于帐户的时间系列事件数据，并从其他配置文件或查找记录数据中受益。 例如帐户数据、购买群组数据、商机数据、营销列表成员数据等。

   * 定义要用作主帐户标识符的标识符（帐户ID）。 通常，现有的CRM或其他工具（例如：Demandbase）可帮助您确定该标识符。
   * 为计划使用的其他B2B数据标识其他标识符：全局帐户标识符、商机标识符、购买组标识符和人员标识符。

1. 准备B2B数据。 确保在所有时间序列事件数据和相关记录数据中添加和收集帐户标识符。 同样，请确保您的时间序列事件数据和查找记录包含相关事件的其他标识符。 例如：表示移动到另一个销售阶段的事件应具有机会标识符。 该标识符应当是机会查找数据的一部分。

1. [创建新的基于帐户的连接](/help/connections/create-connection.md#account-based-connection)。 选择要包含的可选容器，[添加数据集](/help/connections/create-connection.md#add-datasets)并为每个数据集[&#128279;](/help/connections/create-connection.md#dataset-settings)定义设置。 尽可能将[按容器](cja-b2b-concepts-features.md#match-by-container)匹配用于查找记录数据集。

1. [根据新连接创建数据视图](/help/data-views/create-dataview.md)。

   * 确保从已摄取的数据中添加所有相关字段作为量度或维度。
   * 根据需要应用组件设置（如持久性、归因等）。
   * 根据需要，添加其他派生字段。

1. [创建工作区项目](/help/analysis-workspace/build-workspace-project/create-projects.md)以报告和了解您的B2B数据。 使用特定的B2B功能（如[容器](cja-b2b-concepts-features.md#containers)）获取深入的见解。

   通过使用多个[面板](/help/analysis-workspace/c-panels/panels.md)，您可以将B2B（基于人员）和B2B（基于帐户）报表和见解合并到一个工作区项目中。
