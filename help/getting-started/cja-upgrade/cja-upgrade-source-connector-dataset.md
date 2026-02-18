---
title: 将 Analytics 源连接器数据集添加到连接
description: 了解如何将 Analytics 源连接器数据集添加到连接
role: Admin
solution: Customer Journey Analytics
feature: Basics
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: f03c82375a907821c8e3f40b32b4d4200a47323f
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 100%

---

# 将 Analytics 源连接器数据集添加到连接 {#upgrade-source-connector-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-dataset"
>title="将 Analytics 源连接器数据集添加到您的连接"
>abstract="现在，Analytics 报告包中的历史数据位于 Adobe Experience Platform 中，请将该数据集添加到您最初配置 Customer Journey Analytics 时创建的现有连接中。此步骤完成后，Customer Journey Analytics 中的历史数据即可使用。<br><br>在 Customer Journey Analytics 中将数据集添加到连接中非常简单，只需几分钟即可完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## 了解 Analytics 源连接器如何将历史数据带入 Customer Journey Analytics

您可以使用 Analytics 源连接器将 Adobe Analytics 报告套件数据导入到 Adobe Experience Platform。然后，这些数据可以用作 Customer Journey Analytics 中的历史数据。

此过程假设您希望[在更新至 Customer Journey Analytics 时创建一个 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)，因为您需要一个根据您的组织需求和您使用的特定 Platform 应用程序量身定制的精简架构。

要使用 Analytics 源连接器将历史数据引入 Customer Journey Analytics，您需要：

1. [为 Analytics 源连接器创建 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. 如果您尚未拥有 Analytics 源连接器，请[创建 Analytics 源连接器并将字段映射到您的 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   或

   如果您已拥有 Analytics 源连接器，[则将字段从源连接器映射到 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. 将 Analytics 源连接器数据集添加到连接，如下所述

## 将 Analytics 源连接器数据集添加到连接

在[为历史数据创建 Analytics 源连接器](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)后，会自动为 Analytics 数据创建一个数据集。

您需要将这个自动创建的数据集添加到为 Web SDK 实施创建的同一个连接中。这样做会将 Analytics 数据带入 Customer Journey Analytics 中的与 Web SDK 数据相同的数据视图中。

要将该自动创建的数据集添加到为 Web SDK 实施创建的同一个连接中：

1. 在 Customer Journey Analytics 的顶部菜单中选择&#x200B;**[!UICONTROL 连接]**，也可以从&#x200B;**[!UICONTROL 数据管理]**&#x200B;中选择。

1. 选择您[为您的 Web SDK 实施而创建](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)的连接。

1. 选择&#x200B;**[!UICONTROL 编辑]**。

   ![编辑连接](assets/connection-add-dataset.png)

1. 选择右上角的&#x200B;**[!UICONTROL 添加数据集]**。

   ![编辑连接](assets/connection-add-dateset2.png)

1. 滚动到或搜索创建 Analytics 源连接器时自动创建的数据集。

   此数据集的名称是您的报告包的名称，后跟 `midValues`。例如：`My report suite midValues`

1. 选中数据集名称旁边的复选框，然后选择&#x200B;**[!UICONTROL 下一步]**。

   ![编辑连接](assets/connection-add-dataset3.png)

1. 指定以下信息：

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | 设置 | 描述 |
   | --- | --- |
   | **[!UICONTROL 人员 ID]** | 仅适用于事件和轮廓数据集。从可用身份标识的下拉菜单中选择一个人员 ID。这些身份标识已在 Experience Platform 的数据集架构中定义。有关如何将身份标识映射用作人员 ID 的信息，请参见下文。<p>如果没有可供选择的人员 ID，则意味着架构中尚未定义一个或多个人员 ID。请参阅[在 UI 中定义身份标识字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity)以了解更多信息。 <p>所选人员 ID 的值区分大小写。例如，`abc123` 和 `ABC123` 是两个不同的值。 |
   | **[!UICONTROL 时间戳]** | 仅对事件和摘要数据集，此设置会自动设置为 Experience Platform 中基于事件的架构的默认时间戳字段。 |
   | **[!UICONTROL 时区]** | 仅适用于摘要数据。为时间序列摘要数据选择适当的时区。 |
   | **[!UICONTROL 数据源类型]** | 选择数据源类型。<br/>数据源的类型包括： <ul><li>[!UICONTROL Web 数据]</li><li>[!UICONTROL 移动应用程序数据]</li><li>[!UICONTROL POS 数据]</li><li>[!UICONTROL CRM 数据]</li><li>[!UICONTROL 调查数据]</li><li>[!UICONTROL 呼叫中心数据]</li><li>[!UICONTROL 产品数据]</li><li> [!UICONTROL 帐户数据]</li><li> [!UICONTROL 事务数据]</li><li>[!UICONTROL 客户反馈数据]</li><li> [!UICONTROL 其他]</li></ul>该字段用于调查正在使用的数据源的类型。 |

   {style="table-layout:auto"}

1. 在&#x200B;**[!UICONTROL 导入新数据]**&#x200B;部分，禁用&#x200B;**[!UICONTROL 导入所有新数据]**&#x200B;选项。

   由于您正在使用 Analytics 源连接器数据集来获取历史数据，因此您不希望将未来收集的数据也导入到此数据集中。

1. 在&#x200B;**[!UICONTROL 数据集回填]**&#x200B;部分，选择&#x200B;**[!UICONTROL 请求回填]**。

1. 通过输入开始日期和结束日期或选择日程表图标 ![日程表](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)，定义您希望连接回填到 Customer Journey Analytics 中的时间段。

   在指定您要求回填的日期时要明确。根据多种因素，您可能需要执行以下任一操作：

   * 选择的结束日期与您首次开始使用 Web SDK 实施收集数据的日期相同。

   * 选择一个在您首次开始使用 Web SDK 实施收集数据后不久的结束日期，然后使用数据视图区段将重叠的数据分段。

   * 选择一个能产生更大数据重叠的结束日期，然后使用数据视图区段来将重叠的数据分段。

     **注释：**&#x200B;该选项会导致成本增加，因为连接中的行会增加。

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the segment. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. 选择&#x200B;**[!UICONTROL 排列回填]**。

1. 选择&#x200B;**[!UICONTROL 添加数据集]**，然后选择&#x200B;**[!UICONTROL 保存]**&#x200B;来保存该连接。

1. （有条件）如果您正在使用查找数据集，则必须创建查找数据集并将其添加到您的连接中。有关详细信息，请参阅 [创建查找数据集，以对 Customer Journey Analytics 中的数据进行分类](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。

   仅当您在配置 Web SDK 实施时尚未执行此操作时才需要这样做。

{{upgrade-final-step}}
