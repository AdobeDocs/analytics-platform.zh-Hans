---
title: 如何在 Customer Journey Analytics 中管理连接
description: 描述如何管理与Customer Journey Analytics(Customer Journey Analytics)中的Experience Platform数据集的连接。
mini-toc-levels: 3
exl-id: 0a87518c-3608-44ad-b5e3-976f97560433
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: 71931b85de6b238c0c6c6fd7b72d06f25103b906
workflow-type: tm+mt
source-wordcount: '3188'
ht-degree: 14%

---

# 管理连接

一旦您拥有 [创建或编辑了一个或多个连接](/help/connections/create-connection.md)，则可以在中管理它们 **[!UICONTROL 连接]**. 通过连接，您可以：

* 直观查看所有连接，包括所有者、沙盒以及创建和修改连接的时间。
* 编辑连接。
* 删除连接。
* 从连接中创建一个数据视图。
* 查看一个连接中的全部数据集。
* 检查连接数据集的状态和摄取过程的状态。 例如，您的数据何时可用，以便可以从Analysis Workspace中的报表和分析开始。
* 识别因错误配置导致的数据差异。 您是否丢失了行？如果是这样，那么丢失了哪些行？为什么？ 您是否错误配置了连接并导致Customer Journey Analytics中数据丢失？
* 深入了解所有连接中摄取和可报告行的使用情况。

[!UICONTROL 连接] 有两个接口： [[!UICONTROL 列表]](#list) 和 [[!UICONTROL 使用情况]](#usage).


## 列表

此 [!UICONTROL 列表] interface是Connections的默认接口。 如果未选定，请选择 **[!UICONTROL 列表]** 选项卡访问该界面。

![列表视图](assets/list-view.png)

此 [!UICONTROL 列表] 接口显示所有可用连接的表。 您可以使用搜索快速搜索连接 ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) 盒子。

表格中提供了以下列或图标。

| 列或图标 | 描述 |
| --- | --- |
| [!UICONTROL 名称] | 好记的连接名称。要查看连接的详细信息，请选择超链接的名称。 请参阅 [连接详细信息](#connection-details). |
| ![信息](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) | 要查看有关以下内容的信息 [!UICONTROL 包含的数据集]， [!UICONTROL 沙盒]， [!UICONTROL 所有者]，等等，选择 ![信息](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) ，位于连接名称旁。<p>显示详细信息的弹出窗口。 <p><img src="./assets/conn-info.png" alt="查看连接信息" width="400"/> |
| ![数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) | 至 [创建数据视图](#create-a-data-view) 对于连接，选择 ![数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg). 仅当没有数据视图与该连接相关联时，此图标才会显示。 |
| ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) | 选择 ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 至： <p>![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [编辑](#edit-a-connection) 一个连接。<p>![删除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) [删除](#delete-a-connection) 一个连接。<p>![数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) [创建新数据视图](#create-a-data-view). 为连接创建其他数据视图。 |
| [!UICONTROL 数据集] | 显示一个或多个指向作为连接一部分的数据集的链接。 您可以选择数据集超链接以查看连接中的数据集。 如果所选连接中包含更多数据集，请选择 **[!UICONTROL +*x* 更多]** 以显示 **[!UICONTROL 包含的数据集]** 面板。 此面板会显示指向所有数据集的链接以及一个用于搜索属于连接的特定数据集的选项。<p><img src="./assets/datasets-included.png" alt="包含的数据资产" width="400"/><p>选择数据集名称会在Experience PlatformUI中的新选项卡中打开该数据集。 |
| [!UICONTROL 沙盒] | 显示 [Experience Platform沙盒](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) 此连接从中获取其数据集。 这是您在首次创建连接时选择的沙盒。不能更改。 |
| [!UICONTROL 所有者] | 创建连接的人员。 |
| [!UICONTROL 导入新数据] | 显示导入数据集新数据的状态： <p>![状态绿色](assets/status-green.svg))    **[!UICONTROL _x _开启]**针对配置为导入新数据的数据集，以及<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关_]** 用于未配置为导入新数据的数据集。 |
| [!UICONTROL 创建日期] | 创建连接时的时间戳。 |
| [!UICONTROL 上次修改时间] | 上次更新连接时的时间戳。 |
| [!UICONTROL 回填数据] | 显示跨数据集的回填数据的状态。<p>![状态红色](assets/status-red.svg)   **[!UICONTROL _x _回填失败]**要了解跨数据集的失败回填数，<p>![状态橙色](assets/status-orange.svg)   **[!UICONTROL _x _正在处理回填]**有关跨数据集处理回填的数量，<p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _回填已完成]**获取数据集的已完成回填数，并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _关闭_]** 如果未为连接中的数据集定义回填。 |

要配置要显示的列，请选择 ![列设置](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)，它显示 **自定义表** 允许您在表中打开或关闭列的对话框。

### 编辑连接

1. 选择 ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) 在连接名称旁边
1. 选择 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑]** 从上下文菜单中。

或者，您可以：

1. 选择连接行。

1. 选择 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑]** 蓝色的酒吧里。

编辑连接时，您可以：

* 开始和停止导入新数据。
* 重命名连接。
* 刷新数据集。
* 从连接中删除数据集。

请参阅 [创建或编辑连接](create-connection.md) 以了解更多信息。


### 删除连接 {#connections-delete}

1. 选择 ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ，位于连接名称旁。
1. 选择 ![删除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 删除]**.

或者，您可以：

1. 选择连接行。

1. 选择 ![删除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 删除]** 蓝色的酒吧里。

删除连接时， **[!UICONTROL 删除连接]** 面板指示删除的数据视图以及受影响的工作区项目。

![删除连接](assets/delete-connection.png)

选择 **[!UICONTROL 继续]** 以删除连接。

请参阅 [删除后果](/help/technotes/deletion.md) 有关删除连接的详细信息。


### 为连接创建数据视图

* 如果没有数据视图与连接相关联：

   1. 选择 ![添加数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) ，位于连接名称旁。

* 如果已为连接创建了一个或多个数据视图：

   1. 选择 ![更多](https://spectrum.adobe.com/static/icons/workflow_18/Smock_More_18_N.svg) ，位于连接名称旁。
   1. 选择 ![添加数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 创建新数据视图]**.

或者，您可以：

1. 选择连接行。

1. 选择 ![添加数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 创建数据视图]** 蓝色按钮栏中的。

有关更多信息，请参阅[创建或编辑数据视图](/help/data-views/create-dataview.md)。

### 连接详细信息 {#connection-detail}

要转至连接的详细信息，请在连接表中选择一个连接名称。

![显示小部件和设置的“所有数据集”窗口](assets/conn-details.png)

“连接详细信息”界面提供连接状态的详细视图。 您可以：

* 检查连接的数据集的状态和摄取过程的状态。
* 确定可能导致跳过或删除记录的配置问题。
* 了解数据何时可用于报告。

| 用户界面 | 描述 |
| --- | --- |
| ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) [!UICONTROL 编辑连接] | 要编辑连接的详细信息，请选择 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) **[!UICONTROL 编辑连接]**. 请参阅 [创建或编辑连接](create-connection.md) 以了解更多信息。 |
| 数据集选择器 | 允许您选择连接中的一个或全部数据集。不能选择其他数量的数据集。默认为[!UICONTROL 全部数据集]。 |
| 日期范围选择器 | 编辑开始日期、结束日期或选择 ![日历](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) 以打开数据范围选择器。 在日期范围选择器中，通过使用某个预定义期间来选择日期范围(例如 **[!UICONTROL 过去6个月]**)，或使用日历选择开始日期和结束日期。 选择 **[!UICONTROL 应用]** 以应用新的数据范围。 |
| [!UICONTROL 可用的事件数据记录数] | 可用于报告的事件数据集总行数， **用于整个连接**. 此数与任何日历设置无关。如果您从数据集选择器中选择了一个数据集，或者在表中选择了一个数据集，则计数会发生变化。 添加数据后，数据延迟1-2个小时后才会显示在报表中。 |
| [!UICONTROL 指标] | 汇总已添加、跳过和删除的事件、查找和配置文件数据集记录，以及添加的批次数， **（对于您选择的数据集和日期范围）**.<p>选择 **[!UICONTROL 检查详细信息]** 以显示 **[!UICONTROL 检查跳过的详细信息]** 弹出窗口。 弹出窗口会列出跳过的记录数以及所有事件数据集或选定数据集的原因。<p><img src="./assets/skipped-records.png" width="500"/><p>选择 ![信息](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) 弹出窗口，其中包含更多信息。 由于某些跳过的原因，例如 [!UICONTROL 访客ID为空]，此时弹出窗口显示可在其中使用的EQS示例PSQL(查询服务的Experience Platform) [查询服务](https://experienceleague.adobe.com/cn/docs/experience-platform/query/home.html?lang=zh-Hans) 以查询数据集中跳过的记录。 选择 ![复制](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) **[!UICONTROL 复制EQS的示例PSQL]** 以复制SQL。 |
| [!UICONTROL 添加的记录数] | 指示在选定时间段，**为您选择的数据集和日期范围**&#x200B;添加了多少行。每 10 分钟更新一次。 |
| [!UICONTROL 跳过的记录数] | 指示在选定的时间段内跳过了多少行（对于您选择的数据集和日期范围&#x200B;**）。**&#x200B;跳过记录的原因包括：缺少时间戳、缺少人员ID或人员ID无效等。 每 10 分钟更新一次。 <p>人员ID无效(如 `undefined`，或 `00000000`，或数字和字母的任意组合 [!UICONTROL 人员ID] （例如，在给定的一个月内出现超过100万次的事件）是无法归因到任何特定用户或人员的ID。 这些行无法引入到系统中，并将导致引入和报表容易出错。 要修复无效的人员 ID，您有 3 个选项：<ul><li>使用 [拼接](/help/stitching/overview.md) 使用有效用户ID填充未定义或全零用户ID。</li><li>将用户ID留空，在引入期间这些用户ID会被跳过（这要优于无效或全零用户ID）。</li><li>先修复系统中的任意无效用户 ID，然后再提取数据。</li></ul> |
| [!UICONTROL 记录] 已删除 | 指示在选定时间段，**为您选择的数据集和日期范围**&#x200B;删除了多少行。有人可能删除了中的数据集 [!DNL Experience Platform]例如， 每 10 分钟更新一次。<p>在某些情况下，该值可能还包含替换的记录，例如拼接或某些查找数据集更新。 请看以下示例：</p><ul><li>您将一个记录上传到XDM个人资料数据集，CJA将其配置为摄取为个人资料查找数据。 在连接详细信息中，此数据集将显示已添加1条记录。</li><li>将原始记录的副本上传到同一AEP数据集中，该数据集现在包含两个记录。 CJA从用户档案查找数据集中摄取其他记录。 CJA看到它已经在该连接中摄取了人员ID的配置文件记录，会删除其早期版本并添加新的配置文件数据。 在连接详细信息中，此操作将表示添加了1条记录并删除了1条记录，因为CJA仅保留任何引入的人员ID的最新配置文件查找数据。</li><li>AEP数据集总共包含两个碰巧相同的记录。 另外，CJA连接详细信息会显示其摄取数据的状态：此用户档案数据集添加了2条记录并删除了1条记录。 </li></ul> |
| ![Search](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) _搜索数据集名称或ID_ | 数据集搜索字段。 您可以按数据集名称搜索数据集表，或者 [!UICONTROL 数据集Id]. |
| [!UICONTROL 数据集表] | 显示作为连接一部分的数据集。 |
| [!UICONTROL 数据集] | 显示作为连接一部分的数据集的名称。 您可以选择超链接在新选项卡的Experience PlatformUI中打开数据集。 您可以选择行或复选框以仅显示选定数据集的详细信息。 |
| [!UICONTROL 数据集 ID] | 由Experience Platform自动生成。 |
| [!UICONTROL 添加的记录数] | 在所选时间间隔内添加到连接的数据集记录（行）数。 |
| [!UICONTROL 跳过的记录数] | 在所选时间间隔内，某个连接的数据传输期间跳过的数据集记录（行）数。 |
| [!UICONTROL 删除的记录数] | 在所选时间间隔内从连接中删除的数据集记录（行）数。 |
| [!UICONTROL 添加的批次] | 已添加到连接的数据集批次数量。 |
| [!UICONTROL 上次添加时间] | 数据集中已添加到连接的最新批次的时间戳。 |
| [!UICONTROL 数据源类型] | 数据集的源类型。 在创建连接时定义源类型。 |
| [!UICONTROL 数据集类型] | 此数据集的数据集类型。 类型可以是 [!UICONTROL 事件]， [!UICONTROL 查找]，或 [!UICONTROL 个人资料]. [了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset) |
| 架构 | 数据集所基于的Experience Platform架构。 |
| [!UICONTROL 导入新数据] | 显示为数据集导入新数据的状态： <p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _开启]**如果数据集配置为导入新数据，并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关_]** 如果数据集配置为不导入新的数据导入。 |
| [!UICONTROL 转换数据] | 显示适用的B2B查找数据集的转换状态。 参见 [转换数据集以进行 B2B 查找](transform-datasets-b2b-lookups.md) 了解更多信息。<p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _开启]**对于启用转换的适用数据集， <p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关_]** 未启用转换的适用数据集，以及<p>**[!UICONTROL 不适用]** 适用于所有其他数据集，不适用于转换。 |
| [!UICONTROL 回填数据] | 显示数据集的回填数据状态。<p>![状态红色](assets/status-red.svg)   **[!UICONTROL _x _回填失败]**有关失败的回填数，<p>![状态红色](assets/status-orange.svg)   **[!UICONTROL _x _正在处理回填]**对于正在处理的回填数，<p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _回填已完成]**已完成回填的数量，以及<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _关闭_]** 如果未配置回填。 |
| [!UICONTROL 导入新数据] | 显示为数据集导入新数据的状态： <p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _开启]**如果数据集配置为导入新数据，并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关_]** 如果数据集配置为不导入新数据。 |
| [!UICONTROL 回填数据] | 显示数据集的回填数据状态。<p>![状态红色](assets/status-red.svg)   **[!UICONTROL _x _回填失败]**有关失败的回填数，<p>![状态红色](assets/status-orange.svg)   **[!UICONTROL _x _正在处理回填]**对于正在处理的回填数，<p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _回填已完成]**已完成回填的数量，以及<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _关闭_]** 如果未配置回填。 |

>[!IMPORTANT]
>
>2021年8月13日之前摄取的任何数据均不反映在 [!UICONTROL 连接] 界面。

#### “连接”面板

在数据集表中未选择数据集时，“连接”界面右侧的面板会显示连接选项和详细信息。

| 选项/详细信息 | 描述 |
| --- | --- |
| ![刷新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) [!UICONTROL 刷新] | 要刷新连接并允许反映最近添加的记录，请选择 ![刷新](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) **[!UICONTROL 刷新]**. |
| ![删除](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Delete_18_N.svg) **[!UICONTROL 删除]** | [删除](#delete-a-connection) 此连接。 |
| ![添加数据视图](https://spectrum.adobe.com/static/icons/workflow_18/Smock_DataAdd_18_N.svg) **[!UICONTROL 创建数据视图]** | [创建数据视图](#create-a-data-view) 基于此连接。 请参阅 [数据视图](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/data-views.html) 以了解更多信息。 |
| [!UICONTROL 连接名称] | 显示好记的连接名称。 |
| [!UICONTROL 连接说明] | 显示描述此连接用途的更详细的说明。 |
| [!UICONTROL 沙盒] | 此 [Experience Platform沙盒](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) 此连接从中获取其数据集的。这是您在首次创建连接时选择的沙盒。 不能更改。 |
| [!UICONTROL 连接 ID] | 此ID以Experience Platform生成。 您可以使用 ![复制](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Copy_18_N.svg) 以复制ID。 |
| [!UICONTROL 使用连接的数据视图] | 列出使用此连接的所有数据视图。 |
| [!UICONTROL 导入新数据] | 显示导入数据集新数据的状态： <p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _开启]**了解有多少数据集配置为导入新数据，以及<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关_]** 关闭了多少个数据集的新数据导入。 |
| [!UICONTROL 回填数据] | 显示数据集的回填数据状态。<p>![状态红色](assets/status-red.svg)   **[!UICONTROL _x _回填失败]**要了解跨数据集的失败回填数，<p>![状态红色](assets/status-orange.svg)   **[!UICONTROL _x _正在处理回填]**有关跨数据集处理回填的数量，<p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _回填已完成]**获取数据集的已完成回填数，并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _关闭_]** 如果未为连接中的数据集定义回填。 |
| 转换数据 | 显示适用的B2B查找数据集的转换状态。 参见 [转换数据集以进行 B2B 查找](transform-datasets-b2b-lookups.md) 了解更多信息。<p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _开启]**用于启用转换的数据集数量。 |
| [!UICONTROL 创建者] | 显示创建连接的人员的姓名。 |
| [!UICONTROL 上次修改时间] | 显示上次更改连接的时间戳。 |
| [!UICONTROL 上次修改人] | 显示上次修改连接的人员。 |

#### 数据集面板

在数据集表中选择某个数据集后，“连接”界面右侧的面板将显示选定数据集的详细信息。

| 详细信息 | 描述 |
| --- | --- |
| [!UICONTROL 人员 ID] | 在 Experience Platform 中显示在数据集架构中定义的身份。此身份是您在创建连接期间选择的人员ID。 如果您创建的连接包含具有不同ID的数据集，则报表会反映这一点。 要合并数据集，您需要跨数据集使用相同的人员ID。 |
| [!UICONTROL 键] | 显示您为查找数据集指定的键。 |
| [!UICONTROL 匹配键] | 显示您为查找数据集指定的匹配键。 |
| [!UICONTROL 时间戳] | 显示为事件数据集定义的时间戳。 |
| [!UICONTROL 可用的记录数] | 显示在通过日历选择的特定时间段内为此数据集摄取的总行数。 添加数据后，数据立刻在报告中显示，没有延迟。但是，在创建全新连接时， [延迟](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#3.-getting-data-into-customer-journey-analytics). |
| [!UICONTROL 添加的记录数] | 显示在所选时段中添加了多少行。 |
| [!UICONTROL 删除的记录数] | 显示选定时间段内删除了多少条记录。 |
| [!UICONTROL 添加的批次] | 显示有多少数据批次添加到此数据集。 |
| [!UICONTROL 跳过的记录数] | 显示在所选时段内摄取期间跳过了多少行。<p>跳过记录的原因包括：缺少时间戳、缺少人员ID或人员ID无效等。 每 10 分钟更新一次。<p>人员ID无效(如 `undefined`，或 `00000000`，或数字和字母的任意组合 [!UICONTROL 人员ID] （例如，在给定的一个月内出现超过100万次的事件）是无法归因到任何特定用户或人员的ID。 这些行无法引入到系统中，并将导致引入和报表容易出错。 要修复无效的人员 ID，您有 3 个选项：<ul><li>使用 [拼接](/help/stitching/overview.md) 使用有效用户ID填充未定义或全零用户ID。</li><li>将用户ID留空，在摄取期间将跳过该用户ID（这要优于无效或全零用户ID）。</li><li>先修复系统中的任意无效用户 ID，然后再提取数据。</li></ul> |
| [!UICONTROL 上次添加时间] | 显示上次添加批次的时间。 |
| [!UICONTROL 导入新数据] | 显示为数据集导入新数据的状态： <p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _开启]**如果数据集配置为导入新数据，并且<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _x关_]** 如果数据集配置为不导入新数据。 |
| [!UICONTROL 回填数据] | 显示数据集的回填数据状态。<p>![状态红色](assets/status-red.svg)   **[!UICONTROL _x _回填失败]**有关失败的回填数，<p>![状态红色](assets/status-orange.svg)   **[!UICONTROL _x _正在处理回填]**对于正在处理的回填数，<p>![状态绿色](assets/status-green.svg)   **[!UICONTROL _x _回填已完成]**已完成回填的数量，以及<p>![状态灰色](assets/status-gray.svg)   **[!UICONTROL _关闭_]** 如果未配置回填。<p>要显示一个对话框，其中概述了数据集的过去回填，请选择 <img src="./assets/pastbackfill.svg" alt="过去的回填" width="15"/> **[!UICONTROL 过去的回填]**. |
| [!UICONTROL 数据源类型] | 将数据集添加到连接时定义的数据源类型。 |
| [!UICONTROL 数据集类型] | [!UICONTROL 事件]、[!UICONTROL 查找]或[!UICONTROL 档案]。[了解详情](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html#configure-dataset) |
| [!UICONTROL 架构] | 显示此数据集所基于的Experience Platform架构。 |
| [!UICONTROL 数据集 ID] | 此数据集ID以Experience Platform生成。 |


## 使用情况

此 [!UICONTROL 使用情况] 界面显示所有连接中摄取和可报告行的使用情况。 此界面支持您确定您的Customer Journey Analytics使用是否符合合同约定的内容。

![usage-view](assets/usage-view.png)

选择 **[!UICONTROL 使用情况]** 选项卡访问该界面。

### 使用情况报表

1. 选择 **[!UICONTROL 时间范围]**. 您可以选择 **[!UICONTROL 过去6个月]**， **[!UICONTROL 年初至今]**，或 **[!UICONTROL 过去2年]**.
1. 选择 **[!UICONTROL 间隔]**. 您可以选择 **[!UICONTROL 每月]** 或 **[!UICONTROL 每季度]**.

对象 [!UICONTROL 已摄取的行]：

* 一个面板可显示摄取的总行数，其中包含所有连接中每个月第2天更新的所有事件数据。 在面板中：
   * 此时将显示一个框，其中显示了上个月有多少行被摄取，以及上个月的%变化(由▲或▼表示)。
   * 折线图显示◼︎ [!UICONTROL 每月摄取的行].<br/>要查看显示每月摄取行数的弹出窗口，请将鼠标悬停在折线图中的任何数据点上。


对象 [!UICONTROL 可报告行]：

* 面板可显示总计可报告行，其中包括在每月第2天更新的所有连接中的所有事件数据。 在面板中：
   * 此时将显示一个框，其中显示了可报告行的累计总数。
   * 此时将显示一个框，其中显示了上个月的可报告行总数，以及上个月在%中的变化(由▲或▼表示)。
   * 折线图显示◼︎ [!UICONTROL 每月可报告行].<br/>要查看显示特定月份累计可报告行数的弹出窗口，请将鼠标悬停在折线图中的任何数据点上。
   * 折线图显示◼︎ [!UICONTROL 累积可报告行].<br/>要查看显示每月可报告行数的弹出窗口，请将鼠标悬停在折线图中的任何数据点上。


>[!MORELIKETHIS]
>
>[查看、排除和修改连接设置](https://experienceleague.adobe.com/docs/customer-journey-analytics-learn/tutorials/connections/connections-details-experience-in-cja.html) 教程。
