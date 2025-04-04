---
title: 如何在 Customer Journey Analytics 中管理连接
description: 介绍如何在Customer Journey Analytics (Customer Journey Analytics)中管理与Experience Platform数据集的连接。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 7f2f2fc92c188c4cdfba7d87b7b64458daf2f0a6
workflow-type: tm+mt
source-wordcount: '4143'
ht-degree: 25%

---

# 管理连接

在您[创建或编辑一个或多个连接](/help/connections/create-connection.md)后，您可以在&#x200B;**[!UICONTROL 连接]**&#x200B;中管理它们。 通过连接，您可以：

* 直观查看所有连接，包括所有者、沙盒以及创建和修改连接的时间。
* 编辑连接。
* 删除连接。
* 从连接中创建一个数据视图。
* 查看一个连接中的全部数据集。
* 检查连接数据集的状态和摄取过程的状态。 例如，您的数据何时可用，以便可以从Analysis Workspace中的报表和分析开始。
* 识别因错误配置导致的数据差异。 您是否丢失了行？如果是这样，那么丢失了哪些行？为什么？ 您是否错误配置了连接并因此导致Customer Journey Analytics中数据丢失？
* 深入了解所有连接中摄取和可报告行的使用情况。

[!UICONTROL 连接]有两个接口： [[!UICONTROL 列表]](#list)和[[!UICONTROL 用法]](#usage)。


## 列表

[!UICONTROL List]接口是Connections的默认接口。 如果未选中，请选择&#x200B;**[!UICONTROL 列表]**&#x200B;选项卡以访问该界面。

![列表视图](assets/list-view.png)

[!UICONTROL List]接口显示所有可用连接的表。 您可以使用搜索![搜索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg)框快速搜索连接。

表格中提供了以下列或图标。

| 列或图标 | 描述 |
| --- | --- |
| [!UICONTROL 名称] | 好记的连接名称。要查看连接的详细信息，请选择超链接的名称。 查看[连接详细信息](#connection-details)。 |
| ![信息](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 要查看有关[!UICONTROL 包含的数据集]、[!UICONTROL 沙盒]、[!UICONTROL 所有者]等的信息，请选择连接名称旁边的![信息](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)。<p>显示详细信息的弹出窗口。 <p><img src="./assets/conn-info.png" alt="查看连接信息" width="400"/> |
| ![数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 要[为连接](#create-a-data-view)创建数据视图，请选择![数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)。 仅当没有数据视图与该连接相关联时，此图标才会显示。 |
| ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 选择![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)以： <p>![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)[编辑](#edit-a-connection)连接。<p>![删除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [删除](#delete-a-connection)连接。<p>![数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [创建新数据视图](#create-a-data-view)。 为连接创建其他数据视图。 |
| [!UICONTROL 数据集] | 指向作为连接一部分的数据集的一个或多个链接。 您可以选择数据集超链接以查看连接中的数据集。 如果所选连接中包含更多数据集，请选择&#x200B;**[!UICONTROL +*x*更多]**&#x200B;以显示&#x200B;**[!UICONTROL 包含的数据集]**&#x200B;面板。 此面板会显示指向所有数据集的链接以及一个用于搜索属于连接的特定数据集的选项。<p><img src="./assets/datasets-included.png" alt="包含的数据资产" width="400"/><p>选择数据集名称会在Experience Platform UI中的新选项卡中打开该数据集。 |
| [!UICONTROL 沙盒] | 此连接从中获取其数据集的[Experience Platform沙盒](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sandbox/home)。 这是您在首次创建连接时选择的沙盒。不能更改。 |
| [!UICONTROL 所有者] | 创建连接的人员。 |
| [!UICONTROL 导入新数据] | 为数据集导入新数据的状态： <p>![状态为绿色](assets/status-green.svg))    **[!UICONTROL _x _On]**用于配置为导入新数据的数据集，并且<p>![状态灰色](assets/status-gray.svg)   未配置为导入新数据的数据集有&#x200B;**[!UICONTROL _x关闭_]**。 |
| [!UICONTROL 创建日期] | 创建连接时的时间戳。 |
| [!UICONTROL 上次修改时间] | 上次更新连接时的时间戳。 |
| [!UICONTROL 回填数据] | 跨数据集的回填数据的状态。<p>![状态为红色](assets/status-red.svg)   **[!UICONTROL _x _个回填失败]**，原因是数据集间回填的失败数，<p>![状态橙色](assets/status-orange.svg)   **[!UICONTROL _x _个回填正在处理]**跨数据集的处理回填数，<p>![状态为绿色](assets/status-green.svg)   针对数据集的已完成回填数，已完成&#x200B;**[!UICONTROL _x _个回填]**，并且<p>![状态灰色](assets/status-gray.svg)   如果未为连接中的数据集定义回填，则返回&#x200B;**[!UICONTROL _Off_]**。 |

要配置要显示的列，请选择![列设置](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)，这将显示&#x200B;**自定义表**&#x200B;对话框，该对话框允许您在表中打开或关闭列。

### 编辑连接

1. 选择连接名称旁边的![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)
1. 从上下文菜单中选择![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑]**。

或者，您可以：

1. 选择连接行。

1. 从蓝色栏中选择![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑]**。

编辑连接时，您可以：

* 开始和停止导入新数据。
* 重命名连接。
* 刷新数据集。
* 从连接中删除数据集。

有关详细信息，请参阅[创建或编辑连接](create-connection.md)。


### 删除连接 {#connections-delete}

1. 选择连接名称旁边的![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)。
1. 选择![删除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 删除]**。

或者，您可以：

1. 选择连接行。

1. 从蓝色条中选择![删除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 删除]**。

删除连接时，**[!UICONTROL 删除连接]**&#x200B;面板指示删除的数据视图以及受影响的工作区项目。

![删除连接](assets/delete-connection.png)

选择&#x200B;**[!UICONTROL 继续]**&#x200B;以删除连接。

有关删除连接的详细信息，请参阅[删除后果](/help/technotes/deletion.md)。


### 为连接创建数据视图

* 如果没有数据视图与连接相关联：

   1. 选择连接名称旁边的![添加数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg)。

* 如果已为连接创建了一个或多个数据视图：

   1. 选择连接名称旁边的![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg)。
   1. 选择![添加数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 创建新数据视图]**。

或者，您可以：

1. 选择连接行。

1. 从蓝色按钮栏中选择![添加数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 创建数据视图]**。

有关更多信息，请参阅[创建或编辑数据视图](/help/data-views/create-dataview.md)。

### 连接详细信息 {#connection-detail}

要转至连接的详细信息，请在连接表中选择一个连接名称。

![显示小部件和设置的所有数据集窗口](assets/conn-details.png)

“连接详细信息”界面提供连接状态的详细视图。 您可以：

* 检查连接的数据集的状态和摄取过程的状态。
* 确定可能导致跳过或删除记录的配置问题。
* 了解数据何时可用于报告。

| 用户界面 | 描述 |
| --- | --- |
| ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg)[!UICONTROL 编辑连接] | 要编辑连接的详细信息，请选择![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑连接]**。 有关详细信息，请参阅[创建或编辑连接](create-connection.md)。 |
| 数据集选择器 | 允许您选择连接中的一个或全部数据集。不能选择其他数量的数据集。默认为[!UICONTROL 全部数据集]。 |
| 日期范围选择器 | 编辑开始日期、结束日期或选择![日历](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)以打开日期范围选择器。 在日期范围选择器中，使用某个预定义期间来选择日期范围（例如&#x200B;**[!UICONTROL 最近6个月]**），或使用日历选择开始和结束日期。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用新的日期范围。 |
| [!UICONTROL 可用的事件数据记录数] | 可用于报告的事件数据集总行数，**表示整个连接**。 此数与任何日历设置无关。如果您从数据集选择器中选择了一个数据集，或者在表中选择了一个数据集，则计数会发生变化。 添加数据后，数据延迟1-2个小时后才会显示在报表中。 |
| [!UICONTROL 量度] | 汇总已添加、跳过和删除的事件、查找、配置文件和摘要数据集记录，以及添加的批次数。 这些量度基于&#x200B;**您选择的数据集和日期范围**。<p>选择&#x200B;**[!UICONTROL 检查详细信息]**&#x200B;以显示&#x200B;**[!UICONTROL 检查跳过的详细信息]**&#x200B;弹出窗口。 弹出窗口会列出跳过的记录数以及所有事件数据集或选定数据集的原因。<p><img src="./assets/skipped-records.png" width="500"/><p>选择包含详细信息的![信息](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)弹出窗口。 由于某些跳过的原因（如[!UICONTROL 访客ID为空]），弹出窗口显示了EQS示例PSQL (查询服务的Experience Platform)，您可以在[查询服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/query/home)中使用它来查询数据集中跳过的记录。 选择![复制](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL 复制EQS的示例PSQL]**&#x200B;以复制SQL。 |
| [!UICONTROL 添加的记录数] | 指示在选定时间段，**为您选择的数据集和日期范围**&#x200B;添加了多少行。每 10 分钟更新一次。 |
| [!UICONTROL 跳过的记录数] | 指示在选定的时间段内跳过了多少行（对于您选择的数据集和日期范围&#x200B;**）。**&#x200B;跳过记录的原因包括：缺少时间戳、缺少人员ID或人员ID无效等。 每 10 分钟更新一次。 <p>无效的个人ID（如`undefined`或`00000000`，或者[!UICONTROL 个人ID]中的任何数字和字母组合，在指定月份在某个事件中出现超过100万次）是无法归因到任何特定用户或个人的ID。 这些行无法引入到系统中，并将导致引入和报表容易出错。 要修复无效的人员 ID，您有 3 个选项：<ul><li>使用[拼接](/help/stitching/overview.md)以有效用户ID填充未定义或全零用户ID。</li><li>将用户ID留空，在引入期间这些用户ID会被跳过（这要优于无效或全零用户ID）。</li><li>先修复系统中的任意无效用户 ID，然后再提取数据。</li></ul> |
| [!UICONTROL 条记录]已删除 | 指示在选定时间段，**为您选择的数据集和日期范围**&#x200B;删除了多少行。例如，有人可能在[!DNL Experience Platform]中删除了一个数据集。 每 10 分钟更新一次。<p>在某些情况下，该值可能还包含替换的记录，例如拼接或某些查找数据集更新。 请看以下示例：</p><ul><li>您将一个记录上传到XDM个人资料数据集，Customer Journey Analytics会将其配置为摄取作为个人资料查找数据。 在连接详细信息中，此数据集将显示已添加1条记录。</li><li>将原始记录的副本上传到同一个AEP数据集中，该数据集现在包含两个记录。 Customer Journey Analytics从用户档案查找数据集中摄取其他记录。 Customer Journey Analytics会看到它已在连接中摄取该人员ID的配置文件记录，因此将删除其早期版本并添加新的配置文件数据。 在连接详细信息中，此操作将表示添加了1条记录并删除了1条记录，因为Customer Journey Analytics仅保留任何引入的人员ID的最新配置文件查找数据。</li><li>AEP数据集总共包含两个碰巧相同的记录。 另外，Customer Journey Analytics连接详细信息会显示其摄取数据的状态：此用户档案数据集添加了2条记录并删除了1条记录。 </li></ul> |
| ![搜索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _搜索数据集名称或ID_ | 数据集搜索字段。 您可以按数据集名称或[!UICONTROL 数据集ID]搜索数据集表。 |
| [!UICONTROL 数据集表] | 作为连接一部分的数据集。 |
| [!UICONTROL 数据集] | 作为连接一部分的数据集的名称。 您可以选择超链接，在新选项卡的Experience Platform UI中打开数据集。 您可以选择行或复选框以仅显示选定数据集的详细信息。 |
| [!UICONTROL 数据集 ID] | 由Experience Platform自动生成。 |
| [!UICONTROL 添加的记录数] | 在所选时间间隔内添加到连接的数据集记录（行）数。 |
| [!UICONTROL 跳过的记录数] | 在所选时间间隔内，某个连接的数据传输期间跳过的数据集记录（行）数。 |
| [!UICONTROL 删除的记录数] | 在所选时间间隔内从连接中删除的数据集记录（行）数。 |
| [!UICONTROL 添加的批次] | 已添加到连接的数据集批次数量。 |
| [!UICONTROL 上次添加时间] | 数据集中已添加到连接的最新批次的时间戳。 |
| [!UICONTROL 数据源类型] | 数据集的源类型。 在创建连接时定义源类型。 |
| [!UICONTROL 数据集类型] | 此数据集的数据集类型。 类型可以是[!UICONTROL Event]、[!UICONTROL Profile]、[!UICONTROL Lookup]或[!UICONTROL Summary]。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| 架构 | 数据集所基于的Experience Platform架构。 |
| [!UICONTROL 导入新数据] | 为数据集导入新数据的状态： <p>![状态为绿色](assets/status-green.svg)   **[!UICONTROL _x _On]**（如果数据集配置为导入新数据），并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关闭_]**（如果数据集配置为不导入新的数据导入）。 |
| [!UICONTROL 转换数据] | 适用的B2B查找数据集的转换状态。 参见 [转换数据集以进行 B2B 查找](transform-datasets-b2b-lookups.md) 了解更多信息。<p>![状态为绿色](assets/status-green.svg)   **[!UICONTROL _x _On]**用于启用转换的适用数据集， <p>![状态灰色](assets/status-gray.svg)   未启用转换的适用数据集的&#x200B;**[!UICONTROL _x关_]**，并且<p>所有其他数据集的&#x200B;**[!UICONTROL N/A]**，不适用于转换。 |
| [!UICONTROL 回填数据] | 数据集的回填数据的状态。<p>![状态为红色](assets/status-red.svg)   **[!UICONTROL _x _个回填失败]**，因为回填失败的数目有<p>![状态为红色](assets/status-orange.svg)   **[!UICONTROL _x _个回填正在处理]**个处理回填数，<p>![状态为绿色](assets/status-green.svg)   已完成&#x200B;**[!UICONTROL _x _个回填]**的回填数，并且<p>![状态灰色](assets/status-gray.svg)   如果未配置回填，则返回&#x200B;**[!UICONTROL _关_]**。 |
| [!UICONTROL 导入新数据] | 为数据集导入新数据的状态： <p>![状态为绿色](assets/status-green.svg)   **[!UICONTROL _x _On]**（如果数据集配置为导入新数据），并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关闭_]**（如果数据集配置为不导入新数据）。 |
| [!UICONTROL 回填数据] | 数据集的回填数据的状态。<p>![状态为红色](assets/status-red.svg)   **[!UICONTROL _x _个回填失败]**，因为回填失败的数目有<p>![状态为红色](assets/status-orange.svg)   **[!UICONTROL _x _个回填正在处理]**个处理回填数，<p>![状态为绿色](assets/status-green.svg)   已完成&#x200B;**[!UICONTROL _x _个回填]**的回填数，并且<p>![状态灰色](assets/status-gray.svg)   如果未配置任何回填，则&#x200B;**[!UICONTROL _关闭_]**。 |

>[!IMPORTANT]
>
>2021年8月13日之前摄取的任何数据都不会反映在[!UICONTROL 连接]接口中。

#### “连接”面板

在数据集表中未选择数据集时，“连接”界面右侧的面板会显示连接选项和详细信息。

| 选项 | 描述 |
| --- | --- |
| ![刷新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL 刷新] | 要刷新连接并允许反映最近添加的记录，请选择![刷新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 刷新]**。 |
| ![Delete](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 删除]** | [删除](#delete-a-connection)此连接。 |
| ![添加数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 创建数据视图]** | [基于此连接创建数据视图](#create-a-data-view)。 有关详细信息，请参阅[数据视图](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views)。 |
| [!UICONTROL 连接名称] | 连接的友好名称。 |
| [!UICONTROL 连接说明] | 描述此连接目的的更详细的描述。 |
| [!UICONTROL 沙盒] | 此连接从中获取其数据集的[Experience Platform沙盒](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sandbox/home)。这是您在首次创建连接时选择的沙盒。 不能更改。 |
| [!UICONTROL 连接 ID] | 此ID在Experience Platform中生成。 您可以使用![复制](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg)来复制ID。 |
| [!UICONTROL 使用连接的数据视图] | 列出使用此连接的所有数据视图。 |
| [!UICONTROL 导入新数据] | 为数据集导入新数据的状态： <p>![状态为绿色](assets/status-green.svg)   **[!UICONTROL _x _On]**，了解有多少数据集配置为导入新数据，以及<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关闭_]**&#x200B;已关闭多少个数据集的新数据导入。 |
| [!UICONTROL 回填数据] | 数据集的回填数据的状态。<p>![状态为红色](assets/status-red.svg)   **[!UICONTROL _x _个回填失败]**，原因是数据集间回填的失败数，<p>![状态为红色](assets/status-orange.svg)   **[!UICONTROL _x _个回填正在处理]**跨数据集的处理回填数，<p>![状态为绿色](assets/status-green.svg)   针对数据集的已完成回填数，已完成&#x200B;**[!UICONTROL _x _个回填]**，并且<p>![状态灰色](assets/status-gray.svg)   如果未为连接中的数据集定义回填，则返回&#x200B;**[!UICONTROL _Off_]**。 |
| 转换数据 | 适用的B2B查找数据集的转换状态。 参见 [转换数据集以进行 B2B 查找](transform-datasets-b2b-lookups.md) 了解更多信息。<p>![状态为绿色](assets/status-green.svg)   **[!UICONTROL _x _On]**用于启用转换的数据集数。 |
| [!UICONTROL 创建者] | 创建连接的人员的姓名。 |
| [!UICONTROL 上次修改时间] | 上次更改连接的时间戳。 |
| [!UICONTROL 上次修改人] | 上次修改连接的人员。 |

#### 数据集面板

在数据集表中选择某个数据集后，“连接”界面右侧的面板将显示选定数据集的详细信息。

| 详细信息 | 描述 |
| --- | --- |
| [!UICONTROL 人员 ID] | 在Experience Platform的数据集架构中定义的标识。 此身份是您在创建连接期间选择的人员ID。 如果您创建的连接包含具有不同ID的数据集，则报表会反映这一点。 要合并数据集，您需要跨数据集使用相同的人员ID。 |
| [!UICONTROL 键] | 您为查找数据集指定的键。 |
| [!UICONTROL 匹配键] | 您为查找数据集指定的匹配键。 |
| [!UICONTROL 时间戳] | 为事件数据集定义的时间戳。 |
| [!UICONTROL 可用的记录数] | 在通过日历选择的特定时间段内为此数据集摄取的总行数。 添加数据后，数据立刻在报告中显示，没有延迟。但是，创建全新连接时有[延迟](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq)。 |
| [!UICONTROL 添加的记录数] | 在选定的时间段中添加了多少行。 |
| [!UICONTROL 删除的记录数] | 在选定的时间段内删除了多少条记录。 |
| [!UICONTROL 添加的批次] | 有多少数据批次添加到此数据集。 |
| [!UICONTROL 跳过的记录数] | 摄取期间在选定的时间段中跳过了多少行。<p>跳过记录的原因包括：缺少时间戳、缺少人员ID或人员ID无效等。 每 10 分钟更新一次。<p>无效的个人ID（如`undefined`或`00000000`，或者[!UICONTROL 个人ID]中的任何数字和字母组合，在指定月份在某个事件中出现超过100万次）是无法归因到任何特定用户或个人的ID。 这些行无法引入到系统中，并将导致引入和报表容易出错。 要修复无效的人员 ID，您有 3 个选项：<ul><li>使用[拼接](/help/stitching/overview.md)以有效用户ID填充未定义或全零用户ID。</li><li>将用户ID留空，在摄取期间将跳过该用户ID（这要优于无效或全零用户ID）。</li><li>先修复系统中的任意无效用户 ID，然后再提取数据。</li></ul> |
| [!UICONTROL 上次添加时间] | 上次添加的批次的时间戳。 |
| [!UICONTROL 导入新数据] | 为数据集导入新数据的状态： <p>![状态为绿色](assets/status-green.svg)   **[!UICONTROL _x _On]**（如果数据集配置为导入新数据），并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关闭_]**（如果数据集配置为不导入新数据）。 |
| [!UICONTROL 回填数据] | 数据集的回填数据的状态。<p>![状态为红色](assets/status-red.svg)   **[!UICONTROL _x _个回填失败]**，因为回填失败的数目有<p>![状态为红色](assets/status-orange.svg)   **[!UICONTROL _x _个回填正在处理]**个处理回填数，<p>![状态为绿色](assets/status-green.svg)   已完成&#x200B;**[!UICONTROL _x _个回填]**的回填数，并且<p>![状态灰色](assets/status-gray.svg)   如果未配置任何回填，则&#x200B;**[!UICONTROL _关闭_]**。<p>要显示一个对话框，其中概述了数据集的过去回填，请选择 <img src="./assets/pastbackfill.svg" alt="过去的回填" width="15"/> **[!UICONTROL 过去的回填]**。 |
| [!UICONTROL 数据源类型] | 将数据集添加到连接时定义的数据源类型。 |
| [!UICONTROL 数据集类型] | [!UICONTROL 事件]、[!UICONTROL 配置文件]、[!UICONTROL 查找]或[!UICONTROL 摘要]。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| [!UICONTROL 架构] | 此数据集所基于的Experience Platform架构。 |
| [!UICONTROL 数据集 ID] | 此数据集ID是在Experience Platform中生成的。 |


## 使用情况 {#connections-usage}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_keyusagemetrics"
>title="关键使用量度"
>abstract="提供核心和历史可报告行数的月度和总计数据。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyingestedrows"
>title="每月引入行数"
>abstract="衡量每月添加到系统的记录总数，提供数据增长和引入率的洞察。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_monthlyreportablerows"
>title="每月可报告行数"
>abstract="跟踪可用于报告的行数。可报告行数是引入行数减去引入过程中跳过和删除的行数。可报告行数是计费和数据使用情况的关键量度。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_detailbreakdown"
>title="详细细分。"
>abstract="您可以按连接、数据集、沙盒和标记详细查看量度，也可以选择下载数据的 CSV 文件。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_otherdatasets"
>title="其他数据集"
>abstract="对于 2024 年 9 月之前的月份，数据是在数据集层面收集的，为了清楚起见，显示为&#x200B;*其他数据集*。从 2024 年 9 月起，数据将在细粒度的数据集层面进行收集，*其他数据集*&#x200B;将不再出现。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_unknowndatasetsorconnections"
>title="未知的数据集或连接"
>abstract="未知的数据集或连接使用其 ID 显示。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_usage_datanotavailable"
>title="数据不可用"
>abstract="由于系统限制，2024 年 9 月之前的历史数据不可用。从 2024 年 9 月开始收集和显示量度。该图表在时间线上显示了过去 18 个月的数据，并且未来的数据将在数据可用时显示。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_corereportablerows"
>title="核心可报告行数"
>abstract="显示过去 13 个月可用的总行数。例如，2024 年 2 月 1 日，该数字显示事件时间戳从 2023 年 1 月到 2024 年 1 月的可用行数总数。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_historicalreportablerows"
>title="历史可报告行数"
>abstract="显示超过 13 个月的时间段内可用的总行数。例如，2024 年 2 月 1 日，该数字显示事件时间戳早于 2023 年 1 月的可用行数总数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_keyusagemetrics"
>title="关键使用量度"
>abstract="提供核心和历史可报告行数的月度和总计数据。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyingestedrows"
>title="每月引入行数"
>abstract="衡量每月添加到系统的记录总数，提供数据增长和引入率的洞察。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_monthlyreportablerows"
>title="每月可报告行数"
>abstract="跟踪可用于报告的行数。可报告行数是引入行数减去引入过程中跳过和删除的行数。可报告行数是计费和数据使用情况的关键量度。"
<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_detailbreakdown"
>title="详细细分。"
>abstract="您可以按连接、数据集、沙盒和标记详细查看量度，也可以选择下载数据的 CSV 文件。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_otherdatasets"
>title="其他数据集"
>abstract="对于 2024 年 9 月之前的月份，数据是在数据集层面收集的，为了清楚起见，显示为&#x200B;*其他数据集*。从 2024 年 9 月起，数据将在细粒度的数据集层面进行收集，*其他数据集*&#x200B;将不再出现。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_unknowndatasetsorconnections"
>title="未知的数据集或连接"
>abstract="未知的数据集或连接使用其 ID 显示。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_usage_datanotavailable"
>title="数据不可用"
>abstract="由于系统限制，2024 年 9 月之前的历史数据不可用。从 2024 年 9 月开始收集和显示量度。该图表在时间线上显示了过去 18 个月的数据，并且未来的数据将在数据可用时显示。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_corereportablerows"
>title="核心可报告行数"
>abstract="显示过去 13 个月可用的总行数。例如，2024 年 2 月 1 日，该数字显示事件时间戳从 2023 年 1 月到 2024 年 1 月的可用行数总数。"
<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_historicalreportablerows"
>title="历史可报告行数"
>abstract="显示超过 13 个月的时间段内可用的总行数。例如，2024 年 2 月 1 日，该数字显示事件时间戳早于 2023 年 1 月的可用行数总数。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_breakdown_corereportablerows"
>title="核心可报告行数"
>abstract="核心可报告行是快照值，而不是聚合总计。 这些值会根据选定日期范围中的最后一个月动态更新。 如果客户选择“一月 — 三月”，则值将反映三月的快照。"

>[!CONTEXTUALHELP]
>id="connections_breakdown_historicalreportablerows"
>title="历史可报告行数"
>abstract="历史可报告行是快照值，而不是聚合总计。 这些值会根据选定日期范围中的最后一个月动态更新。 如果客户选择“一月 — 三月”，则值将反映三月的快照。"

>[!CONTEXTUALHELP]
>id="connections_breakdown_cumulativereportablerows"
>title="累计可报告行数"
>abstract="累积可报告行是快照值，而不是聚合总计。 这些值会根据选定日期范围中的最后一个月动态更新。 如果客户选择“一月 — 三月”，则值将反映三月的快照。"

<!-- markdownlint-enable MD034 -->



[!UICONTROL Usage]接口显示所有连接中摄取和可报告行的使用情况。 如果未选中，请选择&#x200B;**[!UICONTROL 用法]**&#x200B;选项卡以访问该界面。

此界面支持您确定您的Customer Journey Analytics使用是否符合合同约定的内容。 除了监控之外，您还可以使用“使用情况”界面来规划Customer Journey Analytics许可证的续订。

“使用情况”界面使用以下量度

| 量度名称 | 描述 |
|---|---|
| 历史可报告行数 | 超过13个月的时段的行数。 |
| 核心可报告行数 | 过去13个月的行数。 |
| 引入行数 | 在特定时段内摄取了多少行。 |
| 可报告行数 | 在特定时间段内，连接中您有多少行数据。 |
| 累计行 | 截至特定月份为止，摄取了多少行。 |

>[!NOTE]
>
>从2024年7月开始，收集核心、历史和总记录的数据。 请联系您的客户经理以了解早期历史数据。
>



“用法”界面由两个面板组成：

* **[!UICONTROL 密钥使用量度]**&#x200B;面板：提供可报告的核心和历史数据行。 该面板还会跟踪核心数据行和历史数据行与上月相比的百分比变化。

  该面板将显示在可视化中：

   * **[!UICONTROL 可报告的核心数据行]**。

     过去13个月您有多少可报告行。 概要数字是上个月（例如2024年12月）的核心可报告行数（例如741M）。

   * **[!UICONTROL 历史数据可报告行]**。

     在超过13个月的时期内，您有多少个可报告行。 概要数字是上个月（例如2024年12月）的历史可报告行数（例如1.27亿）。

  当您将鼠标悬停在可视化图表中任何栈叠的条形图上时，会显示一个弹出窗口，其中显示该条形图特定部分的行数（例如）。


  ![密钥使用情况量度](assets/usage-key-usage-metrics.png)

* 一个组合面板，其中显示以下三个子面板：

+++ 引入行数

  **[!UICONTROL 已摄取行]**&#x200B;子面板可测量每月添加到系统的记录总数，从而可深入了解数据增长和摄取率。 子面板汇总了本月的总摄取行数以及与上个月相比的变化。

  ![已摄取的行](assets/usage-ingested-rows.png)

  您可以将鼠标悬停在可视化图表中的数据点上，以显示包含更多详细信息的弹出窗口。

+++

+++ 可报告行数

  **[!UICONTROL 可报告行]**&#x200B;可视化图表通过从摄取的行中减去跳过和删除的行来跟踪可用于报告的行数，用作计费和数据使用的关键量度。 子面板提供了两个摘要：

   * **[!UICONTROL 上个月总计]**：截至本月的可报告行总数的摘要。
   * **[!UICONTROL 本月]**：本月可报告行总数以及与上个月相比的变化的摘要。

  ![可报告的行](assets/usage-reportable-rows.png)

  您可以将鼠标悬停在可视化图表中的数据点上，以显示包含更多详细信息的弹出窗口。

+++

+++ 详细细分

  您可以使用&#x200B;**[!UICONTROL 详细信息细分]**&#x200B;表按连接、数据集、沙盒和标记查看详细量度。 数据集是使用id而不是名称进行报告的，因为数据集名称可以在报告期间进行修改。 使用ID报告未知数据集或连接。

  对于 2024 年 9 月之前的月份，数据是在数据集层面收集的，为了清楚起见，显示为[!UICONTROL 其他数据集]。从2024年9月开始，在粒度数据集级别收集数据，并且[!UICONTROL 其他数据集]不再显示。

   * 要更改划分，请选择&#x200B;**[!UICONTROL 查看依据]**&#x200B;和&#x200B;**[!UICONTROL 划分依据]**&#x200B;的组合。

     | **[!UICONTROL 查看方式]**&#x200B;选项 | **[!UICONTROL 按]**&#x200B;选项划分 |
     |---|---|
     | **[!UICONTROL 连接]** | **[!UICONTROL -]**&#x200B;和&#x200B;**[!UICONTROL 数据集]** |
     | **[!UICONTROL 数据集]** | **[!UICONTROL -]** |
     | **[!UICONTROL 沙盒]** | **[!UICONTROL 连接]** |
     | **[!UICONTROL 标记]** | **[!UICONTROL 连接]** |

  ![详细信息细分](assets/usage-detail-breakdown.png)

+++

  您可以定义要报告的&#x200B;**[!UICONTROL 时间范围]**（以月为单位）。 使用![日历](/help/assets/icons/Calendar.svg)选择时间范围。

>[!MORELIKETHIS]
>
>[查看、排除和修改连接设置](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja)教程。
