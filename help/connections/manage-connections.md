---
title: 如何在 Customer Journey Analytics 中管理连接
description: 描述如何管理与Customer Journey Analytics(Customer Journey Analytics)中的Experience Platform数据集的连接。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: bafe2bfdd62065b58ebe5ea6f54a892e0177bbce
workflow-type: tm+mt
source-wordcount: '3263'
ht-degree: 14%

---

# 管理连接

在您[创建或编辑一个或多个连接](/help/connections/create-connection.md)后，您可以在&#x200B;**[!UICONTROL 连接]**&#x200B;中管理它们。 通过连接，您可以：

* 直观查看所有连接，包括所有者、沙盒以及创建和修改连接的时间。
* 编辑连接。
* 删除连接。
* 从连接中创建一个数据视图。
* 查看一个连接中的全部数据集。
* 检查连接数据集的状态和摄取过程的状态。 例如，您的数据何时可用，以便可以从Analysis Workspace中的报表和分析开始。
* 识别因错误配置导致的数据差异。 您是否丢失了行？如果是这样，那么丢失了哪些行？为什么？ 您是否错误配置了连接并导致Customer Journey Analytics中数据丢失？
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
| [!UICONTROL 数据集] | 指向作为连接一部分的数据集的一个或多个链接。 您可以选择数据集超链接以查看连接中的数据集。 如果所选连接中包含更多数据集，请选择&#x200B;**[!UICONTROL +*x*更多]**&#x200B;以显示&#x200B;**[!UICONTROL 包含的数据集]**&#x200B;面板。 此面板会显示指向所有数据集的链接以及一个用于搜索属于连接的特定数据集的选项。<p><img src="./assets/datasets-included.png" alt="包含的数据资产" width="400"/><p>选择数据集名称会在Experience PlatformUI中的新选项卡中打开该数据集。 |
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
| 日期范围选择器 | 编辑开始日期、结束日期或选择![日历](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)以打开数据范围选择器。 在日期范围选择器中，使用某个预定义期间来选择日期范围（例如&#x200B;**[!UICONTROL 最近6个月]**），或使用日历选择开始和结束日期。 选择&#x200B;**[!UICONTROL 应用]**&#x200B;以应用新数据范围。 |
| [!UICONTROL 可用的事件数据记录数] | 可用于报告的事件数据集总行数，**表示整个连接**。 此数与任何日历设置无关。如果您从数据集选择器中选择了一个数据集，或者在表中选择了一个数据集，则计数会发生变化。 添加数据后，数据延迟1-2个小时后才会显示在报表中。 |
| [!UICONTROL 指标] | 汇总已添加、跳过和删除的事件、查找、配置文件和摘要数据集记录，以及添加的批次数。 这些量度基于&#x200B;**您选择的数据集和日期范围**。<p>选择&#x200B;**[!UICONTROL 检查详细信息]**&#x200B;以显示&#x200B;**[!UICONTROL 检查跳过的详细信息]**&#x200B;弹出窗口。 弹出窗口会列出跳过的记录数以及所有事件数据集或选定数据集的原因。<p><img src="./assets/skipped-records.png" width="500"/><p>选择包含详细信息的![信息](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg)弹出窗口。 由于某些跳过的原因（如[!UICONTROL 访客ID为空]），弹出窗口显示了EQS的示例PSQL(查询服务的Experience Platform)，您可以在[查询服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/query/home)中使用它来查询数据集中跳过的记录。 选择![复制](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL 复制EQS的示例PSQL]**&#x200B;以复制SQL。 |
| [!UICONTROL 添加的记录数] | 指示在选定时间段，**为您选择的数据集和日期范围**&#x200B;添加了多少行。每 10 分钟更新一次。 |
| [!UICONTROL 跳过的记录数] | 指示在选定的时间段内跳过了多少行（对于您选择的数据集和日期范围&#x200B;**）。**&#x200B;跳过记录的原因包括：缺少时间戳、缺少人员ID或人员ID无效等。 每 10 分钟更新一次。 <p>无效的个人ID（如`undefined`或`00000000`，或者[!UICONTROL 个人ID]中的任何数字和字母组合，在指定月份在某个事件中出现超过100万次）是无法归因到任何特定用户或个人的ID。 这些行无法引入到系统中，并将导致引入和报表容易出错。 要修复无效的人员 ID，您有 3 个选项：<ul><li>使用[拼接](/help/stitching/overview.md)以有效用户ID填充未定义或全零用户ID。</li><li>将用户ID留空，在引入期间这些用户ID会被跳过（这要优于无效或全零用户ID）。</li><li>先修复系统中的任意无效用户 ID，然后再提取数据。</li></ul> |
| [!UICONTROL 条记录]已删除 | 指示在选定时间段，**为您选择的数据集和日期范围**&#x200B;删除了多少行。例如，有人可能在[!DNL Experience Platform]中删除了一个数据集。 每 10 分钟更新一次。<p>在某些情况下，该值可能还包含替换的记录，例如拼接或某些查找数据集更新。 请看以下示例：</p><ul><li>您将一个记录上传到XDM个人资料数据集，该Customer Journey Analytics配置为摄取作为个人资料查找数据。 在连接详细信息中，此数据集将显示已添加1条记录。</li><li>将原始记录的副本上传到同一AEP数据集中，该数据集现在包含两个记录。 Customer Journey Analytics从配置文件查找数据集中摄取其他记录。 Customer Journey Analytics会看到它已经在连接中摄取了人员ID的配置文件记录，因此会删除其早期版本并添加新的配置文件数据。 在连接详细信息中，此操作将表示添加了1条记录并删除了1条记录，因为Customer Journey Analytics仅保留任何引入的人员ID的最新配置文件查找数据。</li><li>AEP数据集总共包含两个碰巧相同的记录。 另外，Customer Journey Analytics连接详细信息会显示其摄取数据的状态：此用户档案数据集添加了2条记录并删除了1条记录。 </li></ul> |
| ![搜索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _搜索数据集名称或ID_ | 数据集搜索字段。 您可以按数据集名称或[!UICONTROL 数据集ID]搜索数据集表。 |
| [!UICONTROL 数据集表] | 作为连接一部分的数据集。 |
| [!UICONTROL 数据集] | 作为连接一部分的数据集的名称。 您可以选择超链接在新选项卡的Experience PlatformUI中打开数据集。 您可以选择行或复选框以仅显示选定数据集的详细信息。 |
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
| [!UICONTROL 回填数据] | 数据集的回填数据的状态。<p>![状态为红色](assets/status-red.svg)   **[!UICONTROL _x _个回填失败]**，因为回填失败的数目有<p>![状态为红色](assets/status-orange.svg)   **[!UICONTROL _x _个回填正在处理]**个回填正在处理，<p>![状态为绿色](assets/status-green.svg)   已完成&#x200B;**[!UICONTROL _x _个回填]**的回填数，并且<p>![状态灰色](assets/status-gray.svg)   如果未配置回填，则返回&#x200B;**[!UICONTROL _关_]**。 |
| [!UICONTROL 导入新数据] | 为数据集导入新数据的状态： <p>![状态为绿色](assets/status-green.svg)   **[!UICONTROL _x _On]**（如果数据集配置为导入新数据），并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关闭_]**（如果数据集配置为不导入新数据）。 |
| [!UICONTROL 回填数据] | 数据集的回填数据的状态。<p>![状态为红色](assets/status-red.svg)   **[!UICONTROL _x _个回填失败]**，因为回填失败的数目有<p>![状态为红色](assets/status-orange.svg)   **[!UICONTROL _x _个回填正在处理]**个回填正在处理，<p>![状态为绿色](assets/status-green.svg)   已完成&#x200B;**[!UICONTROL _x _个回填]**的回填数，并且<p>![状态灰色](assets/status-gray.svg)   如果未配置任何回填，则&#x200B;**[!UICONTROL _关闭_]**。 |

>[!IMPORTANT]
>
>2021年8月13日之前摄取的任何数据都不会反映在[!UICONTROL 连接]接口中。

#### “连接”面板

在数据集表中未选择数据集时，“连接”界面右侧的面板会显示连接选项和详细信息。

| 选项 | 描述 |
| --- | --- |
| ![刷新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL 刷新] | 要刷新连接并允许反映最近添加的记录，请选择![刷新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 刷新]**。 |
| ![删除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 删除]** | [删除](#delete-a-connection)此连接。 |
| ![添加数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 创建数据视图]** | [基于此连接创建数据视图](#create-a-data-view)。 有关详细信息，请参阅[数据视图](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views)。 |
| [!UICONTROL 连接名称] | 连接的友好名称。 |
| [!UICONTROL 连接说明] | 描述此连接目的的更详细的描述。 |
| [!UICONTROL 沙盒] | 此连接从中获取其数据集的[Experience Platform沙盒](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sandbox/home)。这是您在首次创建连接时选择的沙盒。 不能更改。 |
| [!UICONTROL 连接 ID] | 此ID以Experience Platform生成。 您可以使用![复制](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg)来复制ID。 |
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
| [!UICONTROL 上次添加] | 添加最后批次的时间。 |
| [!UICONTROL 导入新数据] | 为数据集导入新数据的状态： <p>![状态为绿色](assets/status-green.svg)   **[!UICONTROL _x _On]**（如果数据集配置为导入新数据），并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关闭_]**（如果数据集配置为不导入新数据）。 |
| [!UICONTROL 回填数据] | 数据集的回填数据的状态。<p>![状态为红色](assets/status-red.svg)   **[!UICONTROL _x _个回填失败]**，因为回填失败的数目有<p>![状态为红色](assets/status-orange.svg)   **[!UICONTROL _x _个回填正在处理]**个回填正在处理，<p>![状态为绿色](assets/status-green.svg)   已完成&#x200B;**[!UICONTROL _x _个回填]**的回填数，并且<p>![状态灰色](assets/status-gray.svg)   如果未配置任何回填，则&#x200B;**[!UICONTROL _关闭_]**。<p>要显示一个对话框，其中概述了数据集的过去回填，请选择 <img src="./assets/pastbackfill.svg" alt="过去的回填" width="15"/> **[!UICONTROL 过去的回填]**。 |
| [!UICONTROL 数据源类型] | 将数据集添加到连接时定义的数据源类型。 |
| [!UICONTROL 数据集类型] | [!UICONTROL 事件]、[!UICONTROL 配置文件]、[!UICONTROL 查找]或[!UICONTROL 摘要]。 [了解详情](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection) |
| [!UICONTROL 架构] | 此数据集所基于的Experience Platform架构。 |
| [!UICONTROL 数据集 ID] | 此数据集ID以Experience Platform生成。 |


## 使用情况

[!UICONTROL Usage]接口显示所有连接中摄取和可报告行的使用情况。 此界面支持您确定您的Customer Journey Analytics使用是否符合合同约定的内容。 除了监控之外，您还可以使用使用情况UI来规划Customer Journey Analytics许可证续订。

您可以选择时间范围（最近6个月、年初至今或最近2年之间）和间隔（每月或每季度之间）来监控Customer Journey Analytics使用情况。 该界面分为两个部分：

* 已摄取的行：从所有Customer Journey Analytics连接的事件数据集摄取/发送的总行数，包括摄取期间跳过的记录
* 可报告行：包含所有Customer Journey Analytics连接中所有事件数据的可报告行总数

![使用情况视图](assets/usage-view.png)

选择&#x200B;**[!UICONTROL 用法]**&#x200B;选项卡以访问该界面。

### 使用情况报表

1. 选择&#x200B;**[!UICONTROL 时间范围]**。 您可以选择介于&#x200B;**[!UICONTROL 最近6个月]**、**[!UICONTROL 年初至今]**&#x200B;或&#x200B;**[!UICONTROL 最近2年]**&#x200B;之间。
1. 选择&#x200B;**[!UICONTROL 间隔]**。 您可以选择介于&#x200B;**[!UICONTROL 每月]**&#x200B;或&#x200B;**[!UICONTROL 每季]**&#x200B;之间。

对于[!UICONTROL 摄取的行]：

* 一个面板可显示摄取的总行数，其中包含所有连接中每个月第2天更新的所有事件数据。 在面板中：
   * 此时将显示一个框，其中显示了上个月有多少行被摄取，以及上个月的%变化(由▲或▼表示)。
   * 折线图显示◼︎[!UICONTROL 每月摄取的行]。<br/>若要查看显示每月摄取行数的弹出窗口，请将鼠标悬停在折线图中的任何数据点上。


对于[!UICONTROL 可报告行]：

* 面板可显示总计可报告行，其中包括在每月第2天更新的所有连接中的所有事件数据。 在面板中：
   * 此时将显示一个框，其中显示了可报告行的累计总数。
   * 此时将显示一个框，其中显示了上个月的可报告行总数，以及上个月在%中的变化(由▲或▼表示)。
   * 折线图显示◼︎[!UICONTROL 每月可报告的行]。<br/>要查看显示特定月份累计可报告行数的弹出窗口，请将鼠标悬停在折线图中的任何数据点上。
   * 折线图显示◼︎的[!UICONTROL 可报告行]。<br/>若要查看显示每月可报告行数的弹出窗口，请将鼠标悬停在折线图中的任何数据点上。


>[!MORELIKETHIS]
>
>[查看、排除和修改连接设置](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja)教程。
