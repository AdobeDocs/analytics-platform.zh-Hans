---
title: 将 Analytics 源连接器数据集添加到连接
description: 了解如何将Analytics源连接器数据集添加到连接
role: Admin
solution: Customer Journey Analytics
feature: Basics
hide: true
hidefromtoc: true
exl-id: 424485a3-a076-4656-83b6-733f16cc2326
source-git-commit: 4ba493ae40d417499a4ab584898ff533f17be755
workflow-type: tm+mt
source-wordcount: '881'
ht-degree: 36%

---

# 将 Analytics 源连接器数据集添加到连接 {#upgrade-source-connector-dataset}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-upgrade-source-connector-dataset"
>title="将 Analytics 源连接器数据集添加到您的连接"
>abstract="现在，Analytics 报告包中的历史数据位于 Adobe Experience Platform 中，请将该数据集添加到您最初配置 Customer Journey Analytics 时创建的现有连接中。此步骤完成后，Customer Journey Analytics 中的历史数据即可使用。<br><br>在 Customer Journey Analytics 中将数据集添加到连接中非常简单，只需几分钟即可完成。"

<!-- markdownlint-enable MD034 -->

{{upgrade-note-step}}

## 了解Analytics Source Connector如何将历史数据引入Customer Journey Analytics

您可以使用Analytics Source Connector将Adobe Analytics报表包数据引入Adobe Experience Platform。 然后，此数据可以用作Customer Journey Analytics中的历史数据。

此过程假定您希望在升级到Customer Journey Analytics](/help/getting-started/cja-upgrade/cja-upgrade-schema-create.md)时[创建XDM架构，因为您需要一个根据您的组织和您使用的特定Platform应用程序的需求而定制的简化架构。

要使用Analytics Source Connector将历史数据引入Customer Journey Analytics，您需要：

1. [为 Analytics 源连接器创建 XDM 架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector-schema.md)

1. 如果您还没有Analytics源连接器，请[创建Analytics源连接器并将字段映射到XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)。

   或

   如果您已有Analytics源连接器，请将源连接器中的[字段映射到XDM架构](/help/getting-started/cja-upgrade/cja-upgrade-from-source-connector.md)。

1. 将Analytics Source Connector数据集添加到连接，如下所述。

## 将 Analytics 源连接器数据集添加到连接

在您[为历史数据创建Analytics Source Connector](/help/getting-started/cja-upgrade/cja-upgrade-source-connector.md)之后，将自动为Analytics数据创建数据集。

您需要将此自动创建的数据集添加到您为Web SDK实施创建的连接中。 这样做会将Analytics数据引入到Customer Journey Analytics中与Web SDK数据相同的数据视图中。

要将自动创建的数据集添加到您为Web SDK实施创建的相同连接，请执行以下操作：

1. 在 Customer Journey Analytics 中，选择&#x200B;**[!UICONTROL 连接]**&#x200B;选项卡。

1. 选择您[为Web SDK实施](/help/getting-started/cja-upgrade/cja-upgrade-connection.md)创建的连接。

1. 选择&#x200B;**[!UICONTROL 编辑]**。

   ![编辑连接](assets/connection-add-dataset.png)

1. 选择右上角的&#x200B;**[!UICONTROL 添加数据集]**。

   ![编辑连接](assets/connection-add-dateset2.png)

1. 滚动到或搜索在创建Analytics源连接器时自动创建的数据集。

   此数据集的名称是报表包的名称，后跟`midValues`。 例如：`My report suite midValues`

1. 选中数据集名称旁边的复选框，然后选择&#x200B;**[!UICONTROL 下一步]**。

   ![编辑连接](assets/connection-add-dataset3.png)

1. 指定以下信息：

   <!-- Copied from help/connections/create-connection.md. Should we single source? -->

   | 设置 | 描述 |
   | --- | --- |
   | **[!UICONTROL 人员 ID]** | 仅适用于事件和轮廓数据集。从可用身份标识的下拉列表中选择人员 ID。这些身份标识已在 Experience Platform 的数据集架构中定义。有关如何将身份标识映射用作人员 ID 的信息，请参见下文。<p>如果没有可供选择的人员 ID，则意味着架构中尚未定义一个或多个人员 ID。请参阅[在 UI 中定义身份标识字段](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/xdm/ui/fields/identity)以了解更多信息。 <p>所选人员 ID 的值区分大小写。例如，`abc123` 和 `ABC123` 是两个不同的值。 |
   | **[!UICONTROL 时间戳]** | 仅对事件和摘要数据集，此设置会自动设置为 Experience Platform 中基于事件的架构的默认时间戳字段。 |
   | **[!UICONTROL 时区]** | 仅适用于摘要数据。为时间序列摘要数据选择适当的时区。 |
   | **[!UICONTROL 数据源类型]** | 选择数据源类型。<br/>数据源的类型包括： <ul><li>[!UICONTROL Web 数据]</li><li>[!UICONTROL 移动应用程序数据]</li><li>[!UICONTROL POS 数据]</li><li>[!UICONTROL CRM 数据]</li><li>[!UICONTROL 调查数据]</li><li>[!UICONTROL 呼叫中心数据]</li><li>[!UICONTROL 产品数据]</li><li> [!UICONTROL 帐户数据]</li><li> [!UICONTROL 事务数据]</li><li>[!UICONTROL 客户反馈数据]</li><li> [!UICONTROL 其他]</li></ul>该字段用于调查正在使用的数据源的类型。 |

   {style="table-layout:auto"}

1. 在&#x200B;**[!UICONTROL 导入新数据]**&#x200B;部分中，将&#x200B;**[!UICONTROL 导入所有新数据]**&#x200B;选项保留为禁用状态。

   由于您正在将Analytics Source Connector数据集用于历史数据，因此您不希望将来将收集的数据带入此数据集。

1. 在&#x200B;**[!UICONTROL 数据集回填]**&#x200B;部分中，选择&#x200B;**[!UICONTROL 请求回填]**。

1. 通过输入开始和结束日期或选择日历图标![日历](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg)，定义您希望Customer Journey Analytics中的连接回填包括的期间。

   在指定请求回填的日期时务必明确。 根据多种因素，您可能需要执行以下任一操作：

   * 选择一个与首次开始使用Web SDK实施收集数据的日期相同的结束日期。

   * 选择一个结束日期，该日期紧跟您首次开始通过Web SDK实施收集数据的日期，然后使用数据视图区段过滤掉重叠数据。

   * 选择导致数据更大重叠的结束日期，然后使用数据视图区段过滤掉重叠数据。

     **注意：**&#x200B;此选项将导致成本增加，因为连接中会有更多的行。

   <!-- Include any of the following?  Make sure you're explicit as to the dates you request backfill to. You want to request it to the date that you start gathering data with your Web SDK implementation. Also possibly include segments for any overlapping date. So you could request everything and then use a segment to exclude data that you don't want. That way if you need to move up the date, then you could change the date in the filter. Downside would be that you might pay for double rows.  When they do that, they're going to see all schema fields from both their custom schema and their Analytics schema. So they'll need to be cognizant to select the right fields, and never select any Analytics fields, because they will be mapped as part of the source connector. Never select any Analytics field group fields because they'll be mapped.  -->

1. 选择&#x200B;**[!UICONTROL 队列回填]**。

1. 选择&#x200B;**[!UICONTROL 添加数据集]**，然后选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存连接。

1. （视情况而定）如果您使用的是查找数据集，则必须创建查找数据集并将其添加到连接中。 有关详细信息，请参阅[创建查找数据集以在Customer Journey Analytics中对数据进行分类](/help/getting-started/cja-upgrade/cja-upgrade-dataset-lookup.md)。

   只有在配置Web SDK实施时尚未这样做的情况下，才需要执行此操作。

{{upgrade-final-step}}
