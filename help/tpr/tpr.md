---
title: 总人口报表
description: 使用Customer Journey Analytics中的总人口报表分析数据集中的用户档案和帐户，与事件活动或面板日期范围无关。
solution: Customer Journey Analytics
feature: Connections
role: Admin
hide: true
source-git-commit: 1ce48a6e077ee1069c55f3ef8969ed2eced4742e
workflow-type: tm+mt
source-wordcount: '1388'
ht-degree: 4%

---

# 总人口报表

总人口报表引入了对在Customer Journey Analytics连接中存在的配置文件和查找数据集中定义的实体进行分析和报表的功能。 该分析和报告功能超越了事件数据集中的基于时间的事件系列。 该功能支持全新类别的查询、量度和受众定义，它们可反映企业客户群的整个范围。

Customer Journey Analytics是围绕事件构建的。 每个量度、每个可视化图表、每个面板、每个报表都锚定到一个日期时间范围以及该日期时间范围内发生的事件。 您可以提出解决方案这样的问题：

| 问题 | 事件 | 日期时间范围 |
|---|---|---|
| 上周有多少人购买了商品？ | 购买 | 上周 |
| 第1季度有多少客户访问了定价页面？ | 访问 | Q1 |

工作区面板的日期时间范围会过滤数据，您的维度和量度描述在该日期时间范围内发生的情况。

但并不是你的企业需要回答的所有问题都与所发生的事件有关。 有时你需要了解人口本身。

| 问题 | 事件 | 日期时间范围 |
|---|---|---|
| 我们现在有多少活跃客户？ | 不适用 | 不适用 |
| 我们的数据库中有多少帐户？ | 不适用 | 不适用 |
| 有多少会员在过去30天内未购买产品？ | 不适用 | 最近30天 |

这些问题不是关于事件，而是关于存在的人和帐户，无论这些人或帐户最近是否做过任何事。

总人口报表引入了一类新的量度，用于报告个人资料数据。 配置文件数据可能包含人员和帐户，在您的配置文件数据集中与面板的日期范围无关。 借助总人口报表，您可以在同一分析中混合使用基于群体的量度和基于事件的量度，从而更加全面地了解客户的身份和所做的工作。

通过总人口报表，Customer Journey Analytics可以报告配置文件和查找数据集定义的所有实体，而不管事件活动如何。 此报表包括：

* **基于用户档案的查询**：分析用户档案（所有人员、帐户、商机和购买群组）的属性（不考虑事件）。
* **个人资料减去事件查询**：识别在报告窗口内未执行特定操作或体验的个人资料（所有人员、客户、商机和购买组）。
* **共享查找**：支持在多个实体中重复使用查找数据集，以降低引入成本并提高性能。

<!--
* **Classification-based queries**: (future enhancement) Analyze lookup datasets such as product catalogs, including items not tied to events.
-->



## 总人口报告指标

总人口报表量度的行为与Customer Journey Analytics中通常使用的量度有所不同：

* 总人口报表量度未绑定到面板日期范围。 总人口报表量度(如&#x200B;**[!UICONTROL 总人数（个人资料）]**)会从您的个人资料数据集返回当前人口，而不管应用于面板的日期范围如何。 日期过滤器和日期范围比较不会影响总体报表量度，就像这些过滤器和比较影响事件量度一样。
* 总体人口报表要求连接上有一个用户档案数据集。 仅当您的连接包括至少一个用户档案数据集和至少一个事件数据集时，才会显示总人口报表量度。 仅包含事件数据集的连接仍与之前完全相同，并且不显示总人口报表量度。

在Workspace中，总人口量度使用非重复图标(TBD)进行标记，因此，您可以快速识别哪些量度符合面板的日期范围，哪些量度不符合要求。 大多数情况下，总人口量度可与事件量度一起使用，但不支持依赖于事件序列的可视化图表类型（如流失和流量）。

### 标准总人口报告指标

默认情况下，系统包括三个标准总人口报告量度，可用于其连接包括用户档案数据集的任何数据视图：

* **总人数（个人资料）**：个人资料数据集中的总人数。
* **总帐户（配置文件）**：配置文件数据集中的帐户总数。 [!BADGE B2B Edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}
* **总人数（个人资料+事件）**：将个人资料范围内的人员与事件范围内的人员相结合的合并数。

您还可以使用个人资料数据集的字段，创建包含三个范围中任一范围的自定义量度。

## 要求、先决条件和注意事项

为使总人口报表正常工作，应考虑先决条件、要求和注意事项。

### 连接要求

对于支持总人口报告的连接：

* 连接至少需要一个事件数据集。 不支持仅配置文件连接。
* 必须至少将一个配置文件数据集添加到连接。 总体人口报表量度不会显示在基于仅包含事件数据的连接构建的数据视图中。
* 必须为每个配置文件数据集配置共享查找。 共享查找通过指定匹配键、命名空间（用于身份映射字段）和连接路径，定义如何将每个配置文件数据集连接到连接中的事件。

#### 配置文件数据集配置

将用户档案数据集添加到连接后，Customer Journey Analytics会填充基于数据集类型的默认共享查找配置：

* 对于人员配置文件数据集：默认为按容器匹配设置为[!UICONTROL 人员]，标识映射作为键字段。 您可以编辑此默认值。 例如，从身份映射中选择特定的命名空间，而不是主键。 或者，为未填充第一个命名空间的情况指定辅助命名空间（这与拼接数据集通用）。
* 对于帐户配置文件数据集[!BADGE B2B edition]{type=Informative url="https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-overview/cja-b2b/cja-b2b-edition" newtab=true tooltip="Customer Journey Analytics B2B Edition"}：默认设置为[!UICONTROL 帐户]（或者[!UICONTROL 全局帐户]，如果连接上启用了全局帐户）。 帐户字段可以是单个标识符或标识映射。 当帐户字段为身份映射时，选择要使用的命名空间。

您可以在单个用户档案数据集上配置多个共享查找，以支持事件的多个连接路径。 当在多个共享查找中使用相同的标识映射作为键字段时，命名空间选择必须一致。

### 数据视图要求

要使总人口报表量度在数据视图上正确工作，请执行以下操作：

* 连接必须包括配置文件数据集（请参阅[连接要求](#connection-requirements)）。 如果从连接中删除最后一个剩余的配置文件数据集，则从连接构建的数据视图上无法使用总人口报表量度。
* [数据视图级别区段](/help/data-views/create-dataview.md#settings-segments)不能为事件显式区段。 如果直接应用于数据视图的区段完全按照事件范围的条件（例如，`hit where page = X`）定义，则无法对该数据视图进行总体报告。 在依赖总人口报表量度之前，请验证任何数据视图级别区段是否与配置文件范围的报表兼容。
* 必须正确设置量度范围。 在数据视图生成器中创建自定义量度组件时，请根据字段的数据集以及您希望量度的行为方式，选择相应的范围（事件、用户档案或用户档案+事件）。 在受众或定期报表中使用量度后，如果不破坏这些依赖关系，则无法更改范围。

### Workspace兼容性

在大多数Workspace上下文中，总人口报表量度可与基于事件的量度一起使用：[自由格式表](/help/analysis-workspace/visualizations/freeform-analysis-visualizations.md)、[行](/help/analysis-workspace/visualizations/line.md)、[条形图](/help/analysis-workspace/visualizations/bar.md)和[水平条形图](/help/analysis-workspace/visualizations/horizontal-bar.md)可视化图表、[同类群组表](/help/analysis-workspace/visualizations/cohort-table/cohort-analysis.md)（配置适当时）等等。 一些可视化图表类型不受支持，因为它们本身依赖于事件序列：

* [流失](/help/analysis-workspace/visualizations/fallout/fallout-flow.md)
* [流量](/help/analysis-workspace/visualizations/c-flow/flow.md)
* 其他不支持的可视化图表类型需要在发布之前确认。

当您向不支持的可视化图表添加总人口报表量度时，Workspace指示该量度不能在该上下文中使用。

### 受众注意事项

基于总人口报表量度构建的受众取决于数据视图中剩余的那些量度：

* 如果从数据视图中删除了总人口报表量度，则使用总人口报表量度的循环受众会失败并变为“错误”状态。
* Customer Journey Analytics界面阻止删除量度，而任何活动的定期受众都依赖于该量度，并且在您确认删除之前会显示关于依赖性的指导。

### 权限

待确认：在总群体报表量度可见之前，客户的IMS组织或产品配置文件存在任何角色或功能访问要求。 值得在发布前标记为PM。
