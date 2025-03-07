---
title: 创建或编辑连接
description: 描述如何在 Customer Journey Analytics 中创建或编辑与 Experience Platform 数据集的连接。
exl-id: b4ac37ca-213b-4118-85e1-8e8f98553c6c
solution: Customer Journey Analytics
feature: Connections
role: Admin
source-git-commit: baf0a1f1d0bdc0d3c60d9375e20c1de3f39f1702
workflow-type: tm+mt
source-wordcount: '4278'
ht-degree: 99%

---

# 创建或编辑连接 {#create-or-edit-a-connection}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsadded"
>title="添加的记录数"
>abstract="在所选数据集的所选时间间隔期间添加到连接的记录数（行数）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsskipped"
>title="跳过的记录数"
>abstract="在所选数据集的所选时间间隔期间为连接传输数据期间跳过的记录数（行数）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connections_recordsdeleted"
>title="删除的记录数"
>abstract="在所选数据集在所选时间间隔期间从连接删除的记录数（行数）"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_lastadded"
>title="上次添加"
>abstract="从任何数据集传输到连接的最新批次的时间戳。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_enablerollingdatawindow"
>title="启用滚动数据窗口"
>abstract="在连接级别将数据保留定义为以月为单位的滚动窗口。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_averagenumberofdailyuses"
>title="平均每日使用次数"
>abstract="选择整个连接的预期每日事件数的范围。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsadded"
>title="添加的记录数"
>abstract="在所选数据集的所选时间间隔期间添加到连接的记录数（行数）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsskipped"
>title="跳过的记录数"
>abstract="在所选数据集的所选时间间隔期间为连接传输数据期间跳过的记录数（行数）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connections_recordsdeleted"
>title="删除的记录数"
>abstract="在所选数据集在所选时间间隔期间从连接删除的记录数（行数）"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_lastadded"
>title="上次添加"
>abstract="从任何数据集传输到连接的最新批次的时间戳。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_enablerollingdatawindow"
>title="启用滚动数据窗口"
>abstract="在连接级别将数据保留定义为以月为单位的滚动窗口。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_averagenumberofdailyuses"
>title="平均每日使用次数"
>abstract="选择整个连接的预期每日事件数的范围。"

<!-- markdownlint-enable MD034 -->


连接创建和编辑工作流体验通过辅助工作流将所有数据集和连接配置设置引入屏幕中心。它提供详细的数据集选择、配置和审查体验。并允许您指定关键信息，如数据集类型、大小、架构、数据集 ID、批处理状态、回填状态、人员 ID 等，以降低错误连接配置的风险。以下是功能概述：

* 您可以在创建连接时启用滚动数据保留窗口。
* 您可以在连接中添加和删除数据集。（删除数据集会将其从连接中删除，并影响任何关联的数据视图和基础 Analysis Workspace 项目。）
* 您可以为每个数据集启用和请求回填数据。
* 您可以编辑数据集，例如请求另一个回填。
* 您可以按数据集导入现有数据。


>[!BEGINSHADEBOX]

请参阅 ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [创建并编辑连接](https://video.tv.adobe.com/v/343044/?quality=12&learn=on){target="_blank"}以获取演示视频。

>[!ENDSHADEBOX]


## 先决条件

可添加到连接的数据集数量上限为 100。具体的混合方式取决于您公司购买的 Customer Journey Analytics 包。

如果您不确定您拥有的是哪个 Customer Journey Analytics 包，请联系您的管理员。

| **Select** 包 | **Foundation** 包 |
| --- | --- |
| 事件/轮廓/查找/摘要数据集（最多 100 个）的任意组合 | 每个连接一个事件数据集 |
|  | 每个连接最多 99 个轮廓、查看或摘要数据集 |

{style="table-layout:auto"}

## 创建和配置连接 {#create-connection}

1. 在Customer Journey Analytics中，从主菜单中选择&#x200B;**[!UICONTROL 连接]**。
1. 选择&#x200B;**[!UICONTROL 创建新连接]**。

   ![无标题连接设置](assets/create-conn1.png)

1. 配置连接设置。

   | 设置 | 描述 |
   | --- | --- |
   | **[!UICONTROL 连接名称]** | 输入连接的唯一名称。 |
   | **[!UICONTROL 连接说明]** | 描述这种连接的目的。 |
   | **[!UICONTROL 沙盒]** | 在 Experience Platform 中选择一个沙盒，其中包含要创建连接的数据集。<p>Adobe Experience Platform 提供了可将单个 Platform 实例划分为多个单独的虚拟环境的[沙盒](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/sandbox/home)，以帮助开发和改进数字体验应用程序。您可以将沙盒视为包含数据集的“数据孤岛”。沙盒可用于控制对数据集的访问。<p>选择沙盒后，左边栏会显示可从该沙盒中提取的所有数据集。 |
   | **[!UICONTROL 启用滚动数据窗口]** | 如果选中此复选框，那么您可以在连接级别将 Customer Journey Analytics 数据保留定义为以月计的时段（1 个月、3 个月、6 个月等）。<p>数据保留基于事件数据集时间戳并且仅适用于事件数据集。由于没有适用的时间戳，因此轮廓或查找数据集不存在滚动数据窗口设置。但是，如果您的连接包括任何轮廓或查找数据集（一个或多个事件数据集除外），则该数据会在相同的时段内进行保存。<p> 主要好处是，您只需存储或报告适用且有用的数据，并且可删除不再有用的旧数据。它可以帮助您保持在合同限制范围内，并减少超出预期成本的风险。<p>如果您保留默认值（未选中），Adobe Experience Platform 数据保留设置将取代保留期。如果您在 Experience Platform 中有 25 个月的数据，那么 Customer Journey Analytics 会通过回填获取 25 个月的数据。如果您在 Platform 中删除了其中的 10 个月，则 Customer Journey Analytics 将会保留剩余的 15 个月。 |
   | **[!UICONTROL 添加数据集]**（见下文） | 如果您的数据集列表中没有数据集，请添加数据集。 |
   | **[!UICONTROL 数据集名称]** | 选择您要提取到 Customer Journey Analytics 的一个或多个数据集，并选择&#x200B;**[!UICONTROL 添加。]**<p>（如果您有许多数据集可供选择，可以使用数据集列表上方的搜索数据集搜索栏搜索正确的数据集。） |
   | **[!UICONTROL 上次更新时间]** | 仅对于事件数据集，此设置会自动设置为 Experience Platform 中基于事件的架构的默认时间戳字段。“N/A”表示该数据集不包含数据。 |
   | **[!UICONTROL 记录数]** | Experience Platform 中数据集上个月的总记录数。 |
   | **[!UICONTROL 架构]** | 在 Adobe Experience Platform 中创建数据集所依据的[架构。](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/schema/composition) |
   | **[!UICONTROL 数据集类型]** | 对于您添加到此连接的每个数据集，Customer Journey Analytics 会根据传入的数据自动设置数据集类型。有 3 种不同的数据集类型：事件数据、轮廓数据和查找数据。有关数据集类型的说明，请参见下表。 |
   | **[!UICONTROL 粒度]** | 数据集中数据的粒度；仅适用于摘要数据集。 |
   | **[!UICONTROL 数据源类型]** | 数据集的数据源类型。不适用于摘要数据集。 |
   | **[!UICONTROL 人员 ID]** | 从可用身份标识的下拉列表中选择人员 ID。这些身份标识已在 Experience Platform 的数据集架构中定义。有关如何将身份标识映射用作人员 ID 的信息，请参见下文。<p>重要提示：如果没有可供选择的人员 ID，则意味着未在架构中定义一个或多个人员 ID。请查看[这个视频](https://www.youtube.com/watch?v=G_ttmGl_LRU)，以了解如何在 Experience Platform 中定义身份标识。 |
   | **[!UICONTROL 键]** | 仅用于查找数据集（例如 _id）。 |
   | **[!UICONTROL 匹配键]** | 仅用于查找数据集（例如 _id）。 |
   | **[!UICONTROL 导入新数据]** | 设置为开或关。 |
   | **[!UICONTROL 回填数据]** | 您可以请求补填数据集中的数据。例如，您可以请求补填过去 7 天的数据。配置正确的数据集并测试您的连接。如果一切看起来正常，您可以轻松回填所有剩余数据。<p>此外，您还可启用按数据集导入新数据。 |
   | **[!UICONTROL 回填状态]** | 状态指示是否正在处理任何回填数据。 |


## 添加和配置数据集 {#add-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_primaryid"
>title="主 ID"
>abstract="为您的连接选择正确的主要 ID：B2C 场景的人员。B2B 场景帐户。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_optionalcontainers"
>title="可选容器"
>abstract="选择其他容器。<br/><br/>**[!UICONTROL 全球帐户&#x200B;]**：启用连接中的全球帐户配置。<br/>**[!UICONTROL 机会]**：启用连接中的机会配置。<br/>**[!UICONTROL 购买群组&#x200B;]**：启用连接中的购买群组配置。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_personid"
>title="人员 ID"
>abstract="在 Experience Platform 中，从在数据集架构中定义的可用身份标识中选择人员 ID。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountid"
>title="帐户 ID"
>abstract="从 Experience Platform 的数据集架构中定义的可用身份标识中选择一个帐户 ID（帐户的唯一身份标识符）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_accountfield"
>title="帐户字段"
>abstract="选择代表帐户 ID（帐户的唯一标识符）的字段。"

<!-- markdownlint-enable MD034 -->


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_globalaccountid"
>title="全球帐户 ID"
>abstract="从 Experience Platform 的数据集架构中定义的可用身份标识中选择一个全球帐户 ID（全球帐户的唯一身份标识符）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_opportunityid"
>title="机会 ID"
>abstract="从 Experience Platform 的数据集架构中定义的可用身份标识中选择一个机会 ID（机会的唯一身份标识符）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_buyinggroupid"
>title="购买群组 ID"
>abstract="从 Experience Platform 的数据集架构中定义的可用身份标识中选择一个购买群组 ID（购买群组的唯一身份标识符）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_matchingkey"
>title="匹配键"
>abstract="选择如何加入：基于匹配的键或匹配的容器。<br/><br/>**[!UICONTROL 匹配的键&#x200B;]**：选择要与某个事件数据集连接的字段如果此列表为空，则可能尚未添加或配置事件数据集。<br/>**[!UICONTROL 匹配容器]**：选择一个容器来用于与其中一个事件数据集连接。如果此列表为空，则您可能尚未配置一个或多个容器。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_importnewdata"
>title="导入新数据"
>abstract="任何添加到 Experience Platform 数据集中的新批次都会自动被添加到此连接中，并可用于分析。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_datasetbackfill"
>title="数据集回填"
>abstract="此选项将从 Experience Platform 为连接中的此数据集回填现有（历史）数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_transformdataset"
>title="转换数据集"
>abstract="此选项将会转换数据集，使其可用于 B2B 场景中基于人员的查找。开启后，数据集的转换是不可逆的。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja_connection_connectionmap"
>title="连接图"
>abstract="连接图显示事件、人员、帐户和相关查找数据集（如机会、营销活动成员等）之间的关系。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_primaryid"
>title="主 ID"
>abstract="为您的连接选择正确的主要 ID：B2C 场景的人员。B2B 场景帐户。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_optionalcontainers"
>title="可选容器"
>abstract="选择其他容器。<br/><br/>**[!UICONTROL 全球帐户&#x200B;]**：启用连接中的全球帐户配置。<br/>**[!UICONTROL 机会]**：启用连接中的机会配置。<br/>**[!UICONTROL 购买群组&#x200B;]**：启用连接中的购买群组配置。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_personid"
>title="人员 ID"
>abstract="在 Experience Platform 中，从在数据集架构中定义的可用身份标识中选择人员 ID。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountid"
>title="帐户 ID"
>abstract="从 Experience Platform 的数据集架构中定义的可用身份标识中选择一个帐户 ID（帐户的唯一身份标识符）。"

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_accountfield"
>title="帐户字段"
>abstract="选择代表帐户 ID（帐户的唯一标识符）的字段。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_globalaccountid"
>title="全球帐户 ID"
>abstract="从 Experience Platform 的数据集架构中定义的可用身份标识中选择一个全球帐户 ID（全球帐户的唯一身份标识符）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_opportunityid"
>title="机会 ID"
>abstract="从 Experience Platform 的数据集架构中定义的可用身份标识中选择一个机会 ID（机会的唯一身份标识符）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_buyinggroupid"
>title="购买群组 ID"
>abstract="从 Experience Platform 的数据集架构中定义的可用身份标识中选择一个购买群组 ID（购买群组的唯一身份标识符）。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_matchingkey"
>title="匹配键"
>abstract="选择如何加入：基于匹配的键或匹配的容器。<br/><br/>**[!UICONTROL 匹配的键&#x200B;]**：选择要与某个事件数据集连接的字段如果此列表为空，则可能尚未添加或配置事件数据集。<br/>**[!UICONTROL 匹配容器]**：选择一个容器来用于与其中一个事件数据集连接。如果此列表为空，则您可能尚未配置一个或多个容器。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_importnewdata"
>title="导入新数据"
>abstract="任何添加到 Experience Platform 数据集中的新批次都会自动被添加到此连接中，并可用于分析。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_datasetbackfill"
>title="数据集回填"
>abstract="此选项将从 Experience Platform 为连接中的此数据集回填现有（历史）数据。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_transformdataset"
>title="转换数据集"
>abstract="此选项将会转换数据集，使其可用于 B2B 场景中基于人员的查找。开启后，数据集的转换是不可逆的。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="connection_connectionmap"
>title="连接图"
>abstract="连接图显示事件、人员、帐户和相关查找数据集（如机会、营销活动成员等）之间的关系。"

<!-- markdownlint-enable MD034 -->


新的工作流允许您在创建连接时添加 Experience Platform 数据集。

1. 在“连接设置”对话框中，选择&#x200B;**[!UICONTROL 添加数据集]**。

1. 在 [!UICONTROL 选择数据集] 步骤中，您会看到 Experience Platform 数据集的列表。

   ![选择数据集](assets/select-datasets.png)

   对于每个数据集，列表显示：

   | 列 | 描述 |
   |---|---|
   | 数据集 | 数据集的名称。选择名称即可将您定向到 Experience Platform 中的数据集。选择 ![信息](https://spectrum.adobe.com/static/icons/workflow_18/Smock_InfoOutline_18_N.svg) 以显示一个包含数据集更多详细信息的弹出窗口。您可以选择 **[!UICONTROL 在平台中编辑]** 以直接在 Experience Platform 中编辑数据集。 |
   | 数据集类型 | 数据集的类型：事件、轮廓、查找或摘要。 |
   | 记录数 | Experience Platform 中数据集上个月的总记录数。 |
   | 架构 | 数据集的架构。选择名称即可将您定向到 Experience Platform 中的架构。 |
   | 上一批次 | Experience Platform 中最后提取的批次的状态。查看 [批次状态](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/ingestion/batch/troubleshooting#batch-states) 更多信息。 |
   | 数据集 ID | 数据集 ID 的名称。 |
   | 上次更新时间 | 数据集的最后更新时间戳。 |


1. 选择一个或多个数据集并选择&#x200B;**[!UICONTROL 下一个]**。必须有至少一个事件数据集是该连接的一部分。
   * 要更改为数据集列表显示的列，请选择 ![列设置](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)，然后选择要在[!UICONTROL 自定义表]对话框中显示的列。
   * 要搜索特定数据集，请使用 ![搜索](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Search_18_N.svg) 搜索字段。
   * 要在显示或隐藏所选数据集之间切换，请选择 ![选择](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SelectBoxAll_18_N.svg) **[!UICONTROL 隐藏所选项]**&#x200B;或&#x200B;**[!UICONTROL 显示所选项]**。
   * 要从所选数据集的列表中删除数据集，请使用 ![关闭](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Close_18_N.svg)。要删除所有所选的数据集，请选择&#x200B;**[!UICONTROL 全部清除]**。




1. 现在，逐一配置数据集。

   ![配置数据集](assets/add-dataset.png)

   | 设置 | 描述 |
   | --- | --- |
   | **[!UICONTROL 人员 ID]** | 仅适用于事件和轮廓数据集。从可用身份标识的下拉列表中选择人员 ID。这些身份标识已在 Experience Platform 的数据集架构中定义。有关如何将身份标识映射用作人员 ID 的信息，请参见下文。<p>如果没有可供选择的人员 ID，则意味着架构中尚未定义一个或多个人员 ID。请参阅[在 UI 中定义身份标识字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity)以了解更多信息。 <p>所选人员 ID 的值区分大小写。例如，`abc123` 和 `ABC123` 是两个不同的值。 |
   | **[!UICONTROL 时间戳]** | 仅对事件和摘要数据集，此设置会自动设置为 Experience Platform 中基于事件的架构的默认时间戳字段。 |
   | **[!UICONTROL 键]** | 仅适用于查找数据集。用于查找数据集的键。 |
   | **[!UICONTROL 匹配键]** | 仅适用于查找数据集。某个事件数据集中要按其连接在一起的匹配键。如果此列表为空，则可能尚未添加或配置事件数据集。 |
   | **[!UICONTROL 时区]** | 仅适用于摘要数据。为时间序列摘要数据选择适当的时区。 |
   | **[!UICONTROL 数据源类型]** | 选择数据源类型。<br/>数据源的类型包括： <ul><li>[!UICONTROL Web 数据]</li><li>[!UICONTROL 移动应用程序数据]</li><li>[!UICONTROL POS 数据]</li><li>[!UICONTROL CRM 数据]</li><li>[!UICONTROL 调查数据]</li><li>[!UICONTROL 呼叫中心数据]</li><li>[!UICONTROL 产品数据]</li><li> [!UICONTROL 帐户数据]</li><li> [!UICONTROL 事务数据]</li><li>[!UICONTROL 客户反馈数据]</li><li> [!UICONTROL 其他]</li></ul>该字段用于调查正在使用的数据源的类型。 |
   | **[!UICONTROL 导入新数据]** | 如果您想建立持续连接，请启用此选项。通过持续的连接，添加到数据集的新数据批次会自动在 Workspace 中提供。 |
   | **[!UICONTROL 数据集回填]** | 启用 **[!UICONTROL 回填所有现有数据]** 以确保所有现有数据均已回填。<br/><br/>选择 **[!UICONTROL 请求补填]** 填充特定时期的历史数据。您最多可以定义 10 个数据集回填期。<ol><li>通过输入开始和结束数据或使用![日程表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)选择日期来定义期间。</li><li>选择 **[!UICONTROL 队列补填]** 将回填内容添加到列表中，或 **[!UICONTROL 取消]** 取消。</li></ol>对于每个条目，选择 ![编辑](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) 编辑时段，或选择 ![删除](https://spectrum.adobe.com/static/icons/ui_18/CrossSize500.svg) 删除该条目。<br/><br/>在回填上：<ul><li>您可以单独回填每个数据集。</li><li>您会优先处理新添加到此连接中数据集的新数据，因此这些新数据的滞后时间最短。</li><li>任何回填（历史）数据的导入速度都会比较慢。历史数据的数量会影响延迟。</li><li>Analytics Source Connector 会为生产沙盒导入最多 13 个月的数据（无论大小）。非生产沙盒的回填期限为 3 个月。</li></ul> |
   | **[!UICONTROL 转换数据集]** | 对于特定的 B2B 查找数据集，您可以启用数据集转换以适应适当的 B2B 基于人员的报告场景。 参见 [转换数据集以进行 B2B 查找](transform-datasets-b2b-lookups.md) 了解更多信息。 |
   | **[!UICONTROL 回填状态]** | 可能的状态指示符有：<ul><li>成功</li><li>X 回填处理</li><li>关</li></ul> |
   | **[!UICONTROL 数据集 ID]** | 此 ID 是自动生成的。 |
   | **[!UICONTROL 描述]** | 创建此数据集时给出的描述。 |
   | **[!UICONTROL 数据集大小]** | 数据集的大小。 |
   | **[!UICONTROL 架构]** | 在 Adobe Experience Platform 中创建数据集所依据的架构。 |
   | **[!UICONTROL 数据集]** | 数据集的名称。 |
   | **[!UICONTROL 预览：*数据集名称&#x200B;*]** | 使用日期、我的 ID 和标识符列预览数据集。 |
   | **[!UICONTROL 删除]** | 您可以删除或移除数据集并更改人员 ID 而不删除整个连接。删除或移除会降低数据引入以及重新创建整个连接和相关数据视图这一繁琐过程所涉及的成本。 |

   {style="table-layout:auto"}

## 连接预览 {#preview}

要预览您创建的连接，在连接设置对话框中选择&#x200B;**[!UICONTROL 连接预览]**。

![连接预览](assets/create-conn4.png)

此预览包含某些列，其中列出了连接配置。显示的列类型取决于您的个人数据集。

## 数据集类型 {#dataset-types}

对于您已添加到此连接的每个数据集，[!UICONTROL Customer Journey Analytics] 会根据传入的数据自动设置数据集类型。

>[!IMPORTANT]
>
>添加至少一个事件或摘要数据集作为连接的一部分。

有不同的数据集类型：[!UICONTROL 事件]数据、[!UICONTROL 轮廓]数据、[!UICONTROL 查找数据]和[!UICONTROL 摘要]数据。

| 数据集类型 | 描述 | 时间戳 | 架构 | 人员 ID |
|---|---|---|---|---|
| **[!UICONTROL 事件]** | 表示时间事件的数据。例如，网站访问量、互动量、交易量、POS 数据、调查数据、广告展示数据等等。该数据可能是典型的点击流数据，带有客户 ID 或 Cookie ID 以及时间戳。使用事件数据，您可以灵活地选择将哪个 ID 用作人员 ID。 | 自动设置为 [!UICONTROL Experience Platform] 中基于事件的架构的默认时间戳字段。 | 任何基于 XDM 类且具有“时间序列”行为的内置或自定义架构。示例包括“XDM 体验事件”或“XDM 决策事件”。 | 您可以选择想要包含的人员 ID。Experience Platform 中定义的每个数据集架构，可以拥有自己定义的一个或多个身份标识集，并与命名空间关联。其中任何身份标识都可用作人员 ID。示例包括 Cookie ID、拼接 ID、用户 ID、跟踪代码等。 |
| **[!UICONTROL 查询]** | 您可以将数据集添加为所有数据集类型中的字段查找：轮廓、查找和事件数据集（后者始终受支持）。此附加功能扩展了 Customer Journey Analytics 的能力，以支持包括 B2B 在内的复杂数据模型。此数据用于查找在“事件”、“轮廓”或“查找”数据中找到的值或键。您最多可以添加两级查找。（注意[派生字段](/help/data-views/derived-fields/derived-fields.md)不能用作”连接“内的查找的匹配键。）例如，您可以上传将事件数据中的数字 ID 映射到产品名称的查找数据。有关示例，请参阅 [B2B 示例](/help/use-cases/b2b/example.md)。 | 不适用 | 任何基于 XDM 类且具有“记录”行为的内置或自定义架构，“XDM 个人轮廓”类除外。 | 不适用 |
| **[!UICONTROL 轮廓]** | [!UICONTROL 事件]数据中应用于人员、用户或客户的数据。例如，允许您上传关于客户的 CRM 数据。 | 不适用 | 任何基于“XDM 个人轮廓”类的内置或自定义架构。 | 您可以选择想要包含的人员 ID。在 [!DNL Experience Platform] 中定义的每个数据集（摘要数据集除外）均定义了自己的一组或多组人员 ID。例如，Cookie ID、拼接 ID、用户 ID、跟踪代码等。<br>![人员 ID ](assets/person-id.png)**注意**：如果您创建的连接包含具有不同 ID 的数据集，报告会反映这一点。要合并数据集，您需要使用相同的个人 ID。 |
| **摘要** | 与个人 ID 无关的时间序列数据。摘要数据代表不同聚合级别的聚合数据，例如活动。您可以在 Customer Journey Analytics 中使用这些数据来支持各种用例。有关更多信息，请参阅[摘要数据](/help/data-views/summary-data.md)。 | 自动设置为 Experience Platform 中基于事件的摘要量度架构的默认时间戳字段。仅支持每小时或每天的粒度。 | 任何基于“XDM 摘要量度”类的内置或自定义架构。 | 不适用 |

>[!MORELIKETHIS]
>
>博客：[如何在Adobe Customer Journey Analytics中利用事件、查找和配置文件数据集](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-blogs/how-to-leverage-event-lookup-and-profile-datasets-in-adobe/ba-p/681478)

## 使用数字字段作为查找键和查找值 {#numeric}

如果要将数值字段（如成本或利润）添加到基于字符串的键字段，则此查找功能会非常有用。它允许数值以键或值的形式作为查找的一部分。在查找架构中，您可能有与产品名称、COG、营销活动成本或利润率等相关的数值。以下是 Adobe Experience Platform 中的查找架构示例：

![查找架构](assets/schema.png)

您现在支持将这些值作为量度或维度引入 Customer Journey Analytics 报告中。设置连接和拉入查找数据集时，可以编辑数据集以选择[!UICONTROL 键]和[!UICONTROL 匹配键]：

![编辑数据集](assets/lookup-dataset.png)

基于此连接设置数据视图时，可以将数值作为组件添加到数据视图中。基于此数据视图的任何项目都可以报告这些数值。

## 使用身份标识映射作为个人 ID {#id-map}

Customer Journey Analytics 支持将身份标识映射作为个人 ID。Identity Map 是一种地图数据结构，它允许您上载键 -> 值对。键是身份标识命名空间，值是包含身份标识值的结构。在上传的每一行/每个事件中，都存在身份标识映射，并且身份标识映射会相应地填充到每一行中。

身份标识映射适用于任何满足以下要求的数据集：使用基于 [ExperienceEvent XDM](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/home) 类的架构。当您要将此类数据集包含在 Customer Journey Analytics 连接中时，您既可以选择主要 ID，也可以选择身份标识映射来作为字段：

![](assets/idmap1.png)

如果选择身份标识映射，您会另外再获得两个配置选项：

| 选项 | 描述 |
|---|---|
| **[!UICONTROL 使用主要 ID 命名空间]** | 该选项会指示 Customer Journey Analytics 在“身份标识映射”中查找标记了`primary=true`属性的身份标识，并将该身份标识用作该行的人员 ID。该身份标识是 Experience Platform 中用于分区时使用的主密钥。此身份标识也是用作 Customer Journey Analytics 人员 ID 的主要候选项（取决于数据集在 Customer Journey Analytics 连接中的配置方式）。 |
| **[!UICONTROL 命名空间]** | （此选项仅适用于未使用主要 ID 命名空间的情况。）标识命名空间是 [Experience Platform 标识服务的](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/identity/features/namespaces)一个组件。命名空间充当与身份标识相关的上下文的指示器。如果指定了命名空间，Customer Journey Analytics 会在每行的“身份标识映射”中搜索此命名空间密钥，并将该命名空间下的身份标识用作该行的人员 ID。由于 Customer Journey Analytics 无法对所有行执行全方位数据集扫描以确定存在哪些命名空间，因此下拉列表中会显示所有可能的命名空间。必须知道数据中指定了哪些命名空间；系统不会自动检测这些命名空间。 |

{style="table-layout:auto"}

### 身份标识映射边缘情况 {#id-map-edge}

下表显示了当存在边缘情况时两种配置方案及其处理方式：

| 选项 | 身份标识映射中不存在 ID。 | 多个 ID，没有一个标记为主要 ID | 多个 ID 均标记为主要 ID | 单个 ID，是否标记为主要 ID | 一个 ID 标记为主要 ID 的无效命名空间 |
|---|---|---|---|---|---|
| **[!UICONTROL 使用主要 ID 命名空间]已选中** | Customer Journey Analytics 删除了该行。 | Customer Journey Analytics 删除了该行，因为未指定主要 ID。 | 所有命名空间下标记为主要 ID 的 ID 都将被提取到列表中，随后，这些 ID 会按字母顺序排序；根据这种新的排序方式，排在第一个命名空间中的首个 ID 将被用作人员 ID。 | 单个 ID 用作个人 ID。 | 即使命名空间可能无效（Adobe Experience Platform 中不存在），Customer Journey Analytics 也会使用该命名空间下的主要 ID 作为人员 ID。 |
| **[!UICONTROL 特定的身份标识映射命名空间]已选择** | Customer Journey Analytics 删除了该行。 | 选定命名空间下的所有 ID 都将被提取到列表中，并且首个 ID 将会用作人员 ID。 | 选定命名空间下的所有 ID 都将被提取到列表中，并且首个 ID 将会用作人员 ID。 | 选定命名空间下的所有 ID 都将被提取到列表中，并且首个 ID 将会用作人员 ID。 | 选定命名空间下的所有 ID 都将被提取到列表中，并且首个 ID 将会用作人员 ID。（由于在创建连接时，只能选择有效的命名空间，因此无效的命名空间/ID 不可能用作人员 ID） |

{style="table-layout:auto"}

## 计算平均每日事件数 {#average-number}

连接中的每个数据集都会进行此计算。

1. 转到 [Adobe Experience Platform 查询服务](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/query/home)，并创建一个查询。

   创建的查询将如下所示：

   ```
   Select AVG(A.total_events) from (Select DISTINCT COUNT (*) as total_events, date(TIMESTAMP) from analytics_demo_data GROUP BY 2 Having total_events>0) A;
   ```

   在此示例中，“analytics_demo_data”是数据集的名称。

2. 要显示 Adobe Experience Platform 中存在的所有数据集，请执行 `Show Tables` 查询。


## 对大型查找数据集进行算法修剪

创建连接时，您可以添加大型数据集以进行查找。例如，表示产品目录的数据集，以便在构建报告和可视化内容时可以查找描述性产品信息。如此大的查找数据集可能会超过目前作为护栏实现的最大 1000 万个唯一查找，从而导致跳过其他数据。

您可以请求对大型查找数据集进行算法修剪。此算法修剪仅保留查找数据集中与事件数据集中的键匹配的数据。这样，您不需要加载整个未修剪的查找数据集。旧的或不常用的项目被删除，这可能会对报告产生轻微影响，但会带来明显的好处。该算法回顾 90 天并每周更新。

请联系您的 Adobe 支持团队以获取更多信息并启用此功能。
