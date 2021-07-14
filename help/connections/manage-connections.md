---
title: 管理连接
description: 介绍如何管理与Customer Journey Analytics(CJA)中Experience Platform数据集的连接。
mini-toc-levels: 3
source-git-commit: ec76734f270666d13db28fd60ffdf62c04e378bf
workflow-type: tm+mt
source-wordcount: '1445'
ht-degree: 8%

---

# 管理连接

管理员用户创建一个或多个连接后，即可在[!UICONTROL 连接]管理器中管理它们。 [](/help/connections/create-connection.md)连接体验的最新更新在连接详细信息页面中添加了两个重要功能，在此页面中有进一步的描述：

* 它允许您检查连接数据集和摄取流程的&#x200B;**状态**。 此状态检查可让您知道数据何时可用，以便您能够进入Analysis Workspace并开始分析。

* 它允许您&#x200B;**识别由于配置错误而导致的任何数据差异**。 你缺少任何行吗？ 如果是，会缺少哪些行以及原因？ 您是否在CJA中配置了连接并导致缺少数据？

>[!NOTE]
> 此功能将于2021年8月19日正式提供。

## 连接管理器 {#connections-manager}

连接管理器允许您：

* 快速查看所有连接，包括所有者、沙盒以及创建和修改连接的时间。
* 查看连接中的所有数据集。
* 检查连接的状态。
* 删除连接。
* 重命名连接。
* 从连接中创建一个数据视图。

![管理连接](assets/conn-manager.png)

| 设置 | 描述 |
| --- | --- |
| [!UICONTROL 名称] | 连接的友好名称。 单击超链接名称后，您将转到下面描述的连接详细信息页面。 |
| 连接信息 | 单击连接名称旁边的信息图标可查看以下信息：![查看连接信息](assets/conn-info.png) |
| 编辑连接 | 单击连接名称旁边的省略号(...)，然后单击[!UICONTROL 编辑]。![编辑](assets/conn-edit-delete.png) 连接有关详细信息，请参阅下面的“编辑连接”。 |
| 删除连接 | 单击连接名称旁边的省略号(...)，然后单击[!UICONTROL Delete]。 下方“删除连接”标题下的更多信息。 |
| 创建数据视图 | 单击连接名称旁边的省略号(...)，然后单击[!UICONTROL 创建数据视图]。 此操作将基于此连接创建新的数据视图。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL 数据集] | 连接中的数据集。 您可以单击超链接以查看连接中的所有数据集。 单击某个数据集会在Adobe Experience Platform的新选项卡中打开该数据集。 |
| [!UICONTROL 沙盒] | 此连接从中绘制其数据集的[Adobe Experience Platform沙盒](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en)。 首次创建连接时，已选择此沙盒。 无法更改。 |
| [!UICONTROL 所有者] | 创建连接的人员。 |
| [!UICONTROL 导入数据集] | 允许您启用或禁用以前称为“数据流”的内容。 |
| [!UICONTROL 创建日期] | 首次创建连接的日期。 |
| [!UICONTROL 上次修改时间] | 上次更新连接的日期。 |

### 删除连接 {#connections-delete}

只有管理员才有权删除连接。 非管理员用户不会显示此操作。

1. 单击连接名称旁边的省略号(...)。
1. 单击[!UICONTROL 删除]。

在[!UICONTROL Customer Journey Analytics]中删除连接时，将显示一条错误消息，指示：

* 基于已删除的连接创建的任何数据视图都不再起作用。
* 同样地，任何依赖于已删除连接中的数据视图的工作区项目都将停止运行。

[了解](/help/getting-started/cja-deletion.md) 有关删除含义的更多信息。

### 搜索连接或数据集

您可以使用[!UICONTROL 连接]标题下顶部的搜索栏搜索连接。

### 对连接排序

您可以通过单击每个列标题并向上或向下排序来对连接进行排序。

## “连接详细信息”页 {#connection-detail}

新的“连接详细信息”页面为您提供连接状态的非常详细的视图。

它允许您：

* 检查连接数据集和摄取过程的状态。
* 识别导致跳过或删除记录的配置问题。
* 请参阅数据何时可用于报表。

以下是介绍的小组件和设置：

![查看连接详细信息](assets/conn-details.png)

| 构件/设置 | 描述 |
| --- | --- |
| 数据集选择器 | 允许您选择连接中的一个或多个数据集。 不能多选数据集。 默认为[!UICONTROL 所有数据集]。 |
| 日历/日期范围 | 日期范围指示您何时向连接添加数据。 包含所有标准日历预设。 您可以自定义日期范围，但下拉菜单中不显示任何自定义日期范围。 |
| [!UICONTROL 可用记录] 小组件 | 表示可用于报告的总行数，**适用于整个连接**。 此计数与任何日历设置无关。 如果您从数据集选择器中选择数据集，或通过在表中选择数据集来更改数据集，则该数据集会发生更改。 （请注意，添加数据后，需要等待1到2小时才能在报表中显示数据。） |
|  量度小组件 | 汇总添加/跳过/删除的记录以及您选择的&#x200B;**数据集和日期范围的批次添加数量(**)。 |
| [!UICONTROL 添加了记] 录小组件 | 指示在选定的时间段(**)内为您选择的数据集和日期范围添加了多少行**。 每10分钟更新一次。 |
| [!UICONTROL 记录跳过] 小组件 | 指示在选定的时间段内跳过了多少行（对于您选择的数据集和日期范围&#x200B;**）。**&#x200B;跳过记录的原因包括：缺少时间戳、缺少人员ID等 每10分钟更新一次。 |
| [!UICONTROL 记录删除] 小组件 | 指示在选定的时间段内删除了多少行，其中&#x200B;**对应于您选择的数据集和日期范围**。 例如，某人可能已在Experience Platform中删除了数据集。 每10分钟更新一次。 |
| 数据集搜索框 | 您可以按数据集名称或[!UICONTROL 数据集ID]进行搜索。 |
| [!UICONTROL 数据集] | 显示连接中的数据集。 您可以单击超链接以查看连接中的所有数据集。 |
| [!UICONTROL 数据集 ID] | 此ID由Adobe Experience Platform自动生成。 |
| [!UICONTROL 批次] | 指示已向此数据集添加了多少个数据批次。 |
| [!UICONTROL 上次添加] | 显示上次向此数据集添加批处理的时间戳。 |
| [!UICONTROL 数据集类型] | 此数据集的数据集类型可以是[!UICONTROL Event]、[!UICONTROL Lookup]或[!UICONTROL Profile]。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| 架构 | 此连接中数据集所基于的Adobe Experience Platform架构。 |
| **连接级别的右侧边栏** |  |
| [!UICONTROL 刷新] | 刷新连接以允许反映最近添加的记录。 |
| [!UICONTROL 删除] | 删除此连接。 |
| [!UICONTROL 创建数据视图] | 基于此连接创建新数据视图。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html?lang=en) |
| [!UICONTROL 连接名称] | 显示连接的友好名称。 |
| [!UICONTROL 连接描述] | 显示更详细的描述，以理想地描述此连接的用途。 |
| [!UICONTROL 人员 ID] | 显示在Experience Platform的数据集架构中定义的标识。 这是您在创建连接时选择的[!UICONTROL 人员ID]。 如果您创建的连接包含具有不同ID的数据集，报表将反映这一点。 要真正合并数据集，您需要使用相同的[!UICONTROL 人员ID]。 |
| [!UICONTROL 沙盒] | 此连接从中提取其数据集的[Adobe Experience Platform沙盒](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=en)。首次创建连接时，已选择此沙盒。 无法更改。 |
| [!UICONTROL 连接 ID] | 此ID是系统在Adobe Experience Platform中生成的。 |
| [!UICONTROL IMS 组织 ID] | 与您配置的Experience Cloud公司关联的[组织ID](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en)。 以前称为“登录公司”。 |
| [!UICONTROL 使用连接的数据视图] | 列出使用此连接的所有数据视图。 |
| [!UICONTROL 导入新数据] | 指示是否应将新批量数据添加到历史（回填）数据中。 |
| **数据集级别的右侧边栏** |  |
| [!UICONTROL 数据集描述] | 描述此连接中每个数据集的参数。 |
| [!UICONTROL 可用的记录数] | 表示在通过日历选择的特定时间段内为此数据集摄取的总行数。 添加数据后，在报表中不会出现延迟。 (例外情况是，在创建全新连接时，将出现[延迟](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=en#3. — 将数据导入customer-journey-analytics)。 |
| [!UICONTROL 添加的记录数] | 在选定的时间段内添加了多少行。 |
| [!UICONTROL 跳过的记录数] | 在选定的时间段内，在摄取期间跳过了多少行。 |
| [!UICONTROL 记录跳过的错误] | 此处说明了跳过记录的原因。 这些参数可能包括缺少时间戳、缺少人员ID等。 |
| [!UICONTROL 已提取批次] | 已向此数据集中添加了多少个数据批次。 |
| [!UICONTROL 上次添加] | 最后一个批次添加的时间。 |
| [!UICONTROL 数据集类型] | [!UICONTROL Event]、[!UICONTROL Lookup]或[!UICONTROL Profile]。 [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#configure-dataset) |
| [!UICONTROL 架构] | 此数据集所基于的Adobe Experience Platform架构。 |
| [!UICONTROL 数据集 ID] | 此ID是系统在Adobe Experience Platform中生成的。 |
| [!UICONTROL 回填数据] | 跟踪3种状态的回填（历史）数据：[!UICONTROL 在队列]中，[!UICONTROL 正在进行的]（指示进度百分比）和[!UICONTROL 完成]。 |

### 编辑连接

允许管理员编辑连接。 选择连接，然后单击[!UICONTROL 编辑连接]以转到此对话框。 在此，您可以执行以下操作：

* 开始和停止导入新数据。 此过程以前称为“数据流”。
* 重命名连接。
