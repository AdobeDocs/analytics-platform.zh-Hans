---
description: 管理现有导出
keywords: Analysis Workspace
title: 管理导出
feature: Components
exl-id: 0c21802a-c46f-41be-9356-d836c038b174
role: User
source-git-commit: 811fce4f056a6280081901e484c3af8209f87c06
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 3%

---

# 管理导出

导出完整的表后（如中所述） [将Customer Journey Analytics报表导出到云端](/help/analysis-workspace/export/export-cloud.md)，则导出内容位于 [!UICONTROL 导出] 选项卡 [!UICONTROL 导出] 页面。

您只能看到您创建的导出。

## 筛选和搜索导出

要查找所需的信息，可以筛选导出列表或搜索导出。

### 筛选导出列表

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **导出**] 选项卡。

1. 选择 **筛选** 图标。

   <!--add screenshot -->

   您可以按以下条件进行筛选：

   | 过滤器 | 描述 |
   |---------|----------|
   | [!UICONTROL **帐户类型**] | 与导出关联的帐户类型。 可以使用以下帐户类型： <ul><li>[!UICONTROL **AEP数据登陆区**]</li><li>[!UICONTROL **Amazon S3角色ARN**]</li><li>[!UICONTROL **Azure SAS**]</li><li>[!UICONTROL **Azure RBAC**]</li><li>[!UICONTROL **Google Cloud平台**]</li><li>[!UICONTROL **Snowflake**]</li></ul>。 |
   | [!UICONTROL **状态**] | 导出的状态。 可以使用以下状态： <ul><li>[!UICONTROL **活动**]：表示计划的导出尚未过期，或一次性导出尚未完成。 </li><li>[!UICONTROL **完成**]：表示导出已成功导出。 对于计划的导出，这表示计划已过期。</li><li>[!UICONTROL **失败**]<p>以下情况可能会导致导出失败。 将鼠标悬停在 [!UICONTROL **失败**] 状态，以查看有关失败的详细信息。 <ul><li>计划的导出过期</li><li>已达到计划导出的行限制 </li></ul> </p></li></ul> |
   | [!UICONTROL **频率**] | 导出的频率。 可以使用以下频率： <ul><li>[!UICONTROL **一次**]</li><li>[!UICONTROL **每日**]</li><li>[!UICONTROL **每周**]</li><li>[!UICONTROL **每月**]</li><li>[!UICONTROL **每年**]</li></ul> |

   {style="table-layout:auto"}

### 搜索导出

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 选择 [!UICONTROL **导出**] 选项卡。

1. 在搜索字段中，开始键入与要搜索的导出相关联的任何信息。 您可以从表中任何可用的列搜索数据。

## 编辑导出

您可以编辑导出的属性、格式、时间安排和位置信息。

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 在 [!UICONTROL **导出**] 选项卡，选中要编辑的导出旁边的复选框。

   在选择多个导出时，此选项不可用。

1. 选择 [!UICONTROL **编辑**].

   此 [!UICONTROL **导出完整表**] 对话框随即显示。

1. 更新任何可用选项。 有关每个选项的信息，请参阅 [从Analysis Workspace导出完整表](/help/analysis-workspace/export/export-cloud.md#export-full-tables-from-analysis-workspace) 在 [将Customer Journey Analytics报表导出到云端](/help/analysis-workspace/export/export-cloud.md).

## 复制导出

您可以复制现有导出。

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 在 [!UICONTROL **导出**] 选项卡，选中要复制的导出旁边的复选框。

   在选择多个导出时，此选项不可用。

1. 选择 [!UICONTROL **复制**].

   将创建导出的副本。 新导出的名称与原始导出的名称匹配，其中 _[!UICONTROL — 复制]_ 附加到文件名之后。

1. （可选） [编辑新导出](#edit-an-export)，包括文件名和要更改的任何其他属性。

## 手动启动导出

您可以手动启动导出，用于计划导出或以前完成的一次性导出。

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 在 [!UICONTROL **导出**] 选项卡，选中要运行的导出旁边的复选框。

   在选择多个导出时，此选项不可用。

1. 选择 [!UICONTROL **立即导出**].

## 标记导出

将标记应用于导出时，可以在 [!UICONTROL 标记] 上的列 [!UICONTROL 导出] 页面。 请参阅 [配置列](#configure-columns) 以了解更多信息。

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 在 [!UICONTROL **导出**] 选项卡，选中要标记的一个或多个导出旁边的复选框。

1. 选择 [!UICONTROL **编辑标记**].

1. 在 [!UICONTROL **标记导出**] 对话框，键入标记名称以创建新标记，或从下拉菜单中选择现有标记。

   所选导出内容之间的任何常用标记都会显示在标记对话框中。 <!-- what happens if one export has a tag and another doesn't? Is the tag removed if you don't select it? I'm guessing not, but maybe check -->

1. 选择 [!UICONTROL **应用标记**].

## 删除导出

您可以从“导出”页面中删除导出。 已删除的计划导出将不再发送。

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 在 [!UICONTROL **导出**] 选项卡，选中要删除的一个或多个导出旁边的复选框。

1. 选择 [!UICONTROL **删除**]，然后选择 [!UICONTROL **删除**] 看到确认消息时。

## 在上配置列 [!UICONTROL 导出] 页面

您可以在 [!UICONTROL 导出] 选项卡以配置要显示的信息。

选择列标题以按该列对导出进行排序。 默认情况下，导出按上次修改导出的日期和时间排序。

1. 在Customer Journey Analytics中，选择 [!UICONTROL **组件**] > [!UICONTROL **导出**].

1. 在 [!UICONTROL **导出**] 选项卡，选择 **自定义表** 图标 ![自定义表](assets/customize-table-icon.png) 右上角的 [!UICONTROL 导出] 页面。

   以下列可供使用：

   | 可用列 | 描述 |
   |---------|----------|
   | 名称 | 导出的名称。 用户在创建导出时为其命名，如中所述 [将Customer Journey Analytics报表导出到云端](/help/analysis-workspace/export/export-cloud.md). |
   | ID | 创建导出时自动为其分配的ID。 <!-- True? --> |
   | 数据视图名称 | 与导出关联的数据视图的名称。 用户可以在创建导出时选择数据视图，如中所述 [将Customer Journey Analytics报表导出到云端](/help/analysis-workspace/export/export-cloud.md). |
   | 状态 | 导出的状态。 可用状态包括 [!UICONTROL 活动]， [!UICONTROL 完成]、和 [!UICONTROL 失败].<p> **注意：** 有关导出失败疑难解答的信息，请参阅 [导出失败疑难解答](/help/components/exports/troubleshoot-exports.md).</p> |
   | 标记 | 显示应用于导出的任何标记。 有关如何将标记应用于导出的信息，请参阅 [标记导出](#tag-an-export). |
   | 表大小（上次发送） | 上次发送导出的时间。 |
   | 创建者 | 创建导出的用户。 |
   | 已创建 | 创建导出的日期和时间。 <!-- true? --> |
   | 位置 | 帐户上导出数据的位置。 |
   | 帐户 | 从中导出数据的帐户。 |
   | 频率 | 发送导出的频率。 可用选项包括 [!UICONTROL 一次]， [!UICONTROL 每日]， [!UICONTROL 每周]， [!UICONTROL 按工作日的月度]， [!UICONTROL 按月份日期]， [!UICONTROL 按月份日期，每年]、和 [!UICONTROL 按特定日期按年]. |
   | 发送时间 | 发送导出的时间。 |
   | 上次发送 | 上次发送导出的时间。 |
   | 最近修改 | 上次修改导出的时间。 默认情况下，“导出”页面上的项目将按此列排序。 |
   | 帐户类型 | 从中导出数据的云帐户的类型。 可用的帐户类型包括 [!UICONTROL Amazon S3角色ARN]， [!UICONTROL Google Cloud平台]， [!UICONTROL Azure SAS]， [!UICONTROL Azure RBAC]， [!UICONTROL Snowflake]、和 [!UICONTROL Adobe Experience Platform]. |

   {style="table-layout:auto"}

1. 确保选定您要显示的任何列。 选定的列将显示在“导出”页上，并显示相关信息。
