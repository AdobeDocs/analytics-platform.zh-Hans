---
title: 配置对话分析配置
description: 了解如何配置对话分析配置。
solution: Customer Journey Analytics
feature: Content Analytics
role: Admin, User
hold: true
source-git-commit: 8e446c15e998e660b42a09681fe78b885711e41f
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 8%
---
# 配置对话分析配置


对话见解使您能够大规模分析对话(从大型语言模型(LLM)或人)，并在整个客户历程中提供这些对话的上下文。 通过对话分析，您可以了解代表对实际用户结果的影响。


## 创建或编辑配置

创建或编辑“对话分析”配置时，请指定沙盒以及包含提示、响应和反馈数据的事件数据集。 您还可以选择要将这些数据集添加到的Customer Journey Analytics连接。 以及要将对话分析量度和维度添加到其中的数据视图。

只有系统管理员才能创建或编辑对话分析配置。

您可以从[对话见解配置界面](./conversation-insights-manage.md)创建或编辑配置。

### 恢复缺少的混合数据集

如果编辑配置并且为该配置生成的混合数据集不再存在，请选择&#x200B;**[!UICONTROL 恢复]**&#x200B;以重新生成混合数据集。


### 配置步骤

对于每个配置：

1. 在&#x200B;**[!UICONTROL 详细信息]**&#x200B;部分中，指定以下信息：

   ![对话分析详细信息](assets/conversation-insights-configuration-details.png)

   | 字段 | 描述 |
   |---------|----------|
   | **[!UICONTROL 名称]** | 指定配置的名称。 |
   | **[!UICONTROL 沙盒]** | 选择包含要添加到连接的提示、响应和反馈事件数据集的Experience Platform沙盒。 |

1. 在&#x200B;**[!UICONTROL 数据集]**&#x200B;部分中，指定以下信息：

   ![对话分析数据集](assets/conversation-insights-configuration-datasets.png)

   | 字段 | 描述 |
   |---------|----------|
   | **[!UICONTROL 提示事件数据集]** | 选择包含提示事件数据的数据集。 |
   | **[!UICONTROL 响应事件数据集]** | 选择包含响应事件数据的数据集。 |
   | **[!UICONTROL 反馈事件数据集]** | 选择包含反馈事件数据的数据集。 |

1. 在&#x200B;**[!UICONTROL 连接]**&#x200B;部分中，如果尚未配置任何连接，请使用&#x200B;**[!UICONTROL 选择连接]**&#x200B;以选择连接。

   ![对话分析连接](assets/conversation-insights-configuration-connection.png)

   如果已配置连接，请选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑]**&#x200B;以选择其他连接。

   ![对话分析编辑连接](assets/conversation-insights-configuration-edit-connection.png)

   在&#x200B;**[!UICONTROL 选择连接]**&#x200B;对话框中：

   ![对话分析选择连接](assets/conversation-insights-configuration-select-connection.png)

   1. 选中要向其添加提示、响应和反馈事件数据集的连接旁边的复选框。
   1. 选择&#x200B;**[!UICONTROL 使用连接]**。

   * 若要在要从中进行选择的连接列表中搜索，请使用![搜索](/help/assets/icons/Search.svg)字段。
   * 要配置在表格中显示哪些列，请选择![列设置](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)。 在&#x200B;**[!UICONTROL 自定义表]**&#x200B;对话框中，选择要显示的列。 然后选择&#x200B;**[!UICONTROL 应用]**。

1. 在&#x200B;**[!UICONTROL 数据视图]**&#x200B;部分中，如果尚未配置任何数据视图，请选择&#x200B;**[!UICONTROL 选择数据视图]**&#x200B;以选择数据视图。

   如果数据视图已配置，请选择![编辑](/help/assets/icons/Edit.svg) **[!UICONTROL 编辑数据视图选择]**&#x200B;以重新配置数据视图选择。

   在&#x200B;**[!UICONTROL 选择多个数据视图]**&#x200B;对话框中：

   ![对话分析选择数据视图](assets/conversation-insights-configuration-select-data-views.png)

   1. 选择要用于对话分析配置的一个或多个数据视图。

   1. 选择&#x200B;**[!UICONTROL 使用数据视图]**&#x200B;以使用数据视图。 选择“取消”即可取消。

   * 若要在要从中进行选择的数据视图列表中搜索，请使用![搜索](/help/assets/icons/Search.svg)字段。
   * 要配置在表格中显示哪些列，请选择![列设置](https://spectrum.adobe.com/static/icons/workflow_18/Smock_ColumnSettings_18_N.svg)。 在&#x200B;**[!UICONTROL 自定义表]**&#x200B;对话框中，选择要显示的列。 然后选择&#x200B;**[!UICONTROL 应用]**。

1. 要完成配置，请执行以下操作：

   * 为尚未创建的新配置选择&#x200B;**[!UICONTROL 放弃]**。

   * 对于要保存但不想为其创建项目（例如数据视图的更新）的新配置，请选择&#x200B;**[!UICONTROL 保存以供以后使用]**。 因此，您可以稍后重新访问配置，并完成配置的实际创建。

   * 选择&#x200B;**[!UICONTROL 创建]**&#x200B;以创建新配置。

   * 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存修改的配置。

   * 选择&#x200B;**[!UICONTROL 还原]**&#x200B;以还原配置以重新生成配置的新混合数据集。

   * 选择&#x200B;**[!UICONTROL 退出]**&#x200B;以忽略对配置的任何更改。


## 数据视图验证

（解释您从相关数据集中看到的量度和维度）


<!--

1. In the Data views dialog, select the checkbox next to one or more data views that you want to use when analyzing Experience Platform audience data within Analysis Workspace. These data views are automatically configured with Experience Platform audience data for reporting.

1. Select **[!UICONTROL Use data views]**.

1. Select **[!UICONTROL Create]** to create the configuration.

   >[!IMPORTANT]
   >
   >Because the profile dataset is updated once per day, audiences are available in Customer Journey Analytics data views on the day after you create the audience analysis configuration.


1. After 24 hours, [view audience dimensions in the data view](#view-audience-dimensions-in-the-data-view) to verify that the audience dimensions are available in the data views that you selected. 


 
## View audience dimensions in the data view

After you [create an audience analysis configuration](#create-an-audience-analysis-configuration), you can verify that audience dimensions were added to the data views that you selected during the configuration.

To view audience dimensions in the data view, you must be a product profile administrator for the product profile that the data view is assigned to. For more information, see [Access control](/help/technotes/access-control.md).

To view the audience analysis dimensions in the data view:

1. In Customer Journey Analytics, select **[!UICONTROL Data Management]** > **[!UICONTROL Data views]**.

1. In the **[!UICONTROL Dimensions]** section, the following dimensions should now be available:

   * **[!UICONTROL Audience Name]**

   * **[!UICONTROL Audience Origin]**

   * **[!UICONTROL Exited Audience Origin]**

   * **[!UICONTROL Exited Audience Name]**

   Note that each of these dimensions was added to the profile dataset that is associated with the merge policy that you selected during the audience analysis configuration, and each was added to the new lookup dataset that was created.

   ![Audience dimensions available in the data view](assets/audience-analysis-dataview-dataset.png)

1. Use the audience analysis dimensions in Analysis Workspace. 

   Users who have access to use the data view in Analysis Workspace can now see the new dimensions and use them in their analyses. For information about how to use the audience analysis dimensions in Analysis Workspace, see [Analyze Experience Platform audiences in Customer Journey Analytics](/help/connections/audience-analysis/analyze-audiences.md).

-->